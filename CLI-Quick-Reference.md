# Salesforce CLI Quick Reference

**Quick access guide for common Salesforce CLI commands**

---

## Authentication & Org Management

```bash
# Login to org (web-based)
sf org login web --alias myorg

# Login with JWT (for CI/CD)
sf org login jwt --client-id <consumer_key> --jwt-key-file server.key --username user@example.com --alias myorg

# List all authenticated orgs
sf org list

# Display org information
sf org display --target-org myorg

# Display org limits (API usage, storage, etc.)
sf org display limits --target-org myorg

# Set default org
sf config set target-org=myorg

# Logout from org
sf org logout --target-org myorg

# Create scratch org
sf org create scratch --definition-file config/project-scratch-def.json --alias myscratch --duration-days 30

# Delete scratch org
sf org delete scratch --target-org myscratch
```

---

## Data Operations

### Querying Data

```bash
# Basic query
sf data query --query "SELECT Id, Name FROM Account LIMIT 10"

# Query with specific org
sf data query --query "SELECT Id, Name FROM Account" --target-org myorg

# Export query results to CSV
sf data query --query "SELECT Id, Name, Email FROM Contact" --result-format csv > contacts.csv

# Query with relationships
sf data query --query "SELECT Id, Name, (SELECT FirstName, LastName FROM Contacts) FROM Account"
```

### Creating Records

```bash
# Create single record
sf data create record --sobject Account --values "Name='Acme Corp' Industry='Technology'"

# Create with specific org
sf data create record --sobject Contact --values "FirstName='John' LastName='Doe' Email='john@example.com'" --target-org myorg
```

### Updating Records

```bash
# Update record by ID
sf data update record --sobject Account --record-id 001xx000003DGb2AAG --values "Name='New Name' Industry='Finance'"

# Update multiple fields
sf data update record --sobject Opportunity --record-id 006xx000001T2gZAAS --values "StageName='Closed Won' Amount=50000"
```

### Deleting Records

```bash
# Delete record by ID
sf data delete record --sobject Account --record-id 001xx000003DGb2AAG

# Delete with confirmation
sf data delete record --sobject Contact --record-id 003xx000004TgH1AAK --target-org myorg
```

### Bulk Operations

```bash
# Import data from CSV
sf data import bulk --sobject Account --file accounts.csv --wait 10

# Export data
sf data export tree --query "SELECT Id, Name FROM Account" --output-dir ./data

# Import from exported data
sf data import tree --plan ./data/Account-plan.json

# Upsert (insert or update based on external ID)
sf data upsert bulk --sobject Account --file accounts.csv --external-id External_Id__c
```

---

## Metadata Operations

### Deployment

```bash
# Deploy all source
sf project deploy start --source-dir force-app

# Deploy specific metadata
sf project deploy start --metadata ApexClass:MyClass,ApexTrigger:MyTrigger

# Deploy with tests
sf project deploy start --source-dir force-app --test-level RunLocalTests

# Validate deployment (no actual deployment)
sf project deploy start --source-dir force-app --dry-run

# Quick deploy (after validation)
sf project deploy quick --job-id <validation_job_id>

# Deploy to specific org
sf project deploy start --source-dir force-app --target-org production

# Check deployment status
sf project deploy report --job-id <job_id>

# Cancel deployment
sf project deploy cancel --job-id <job_id>
```

### Retrieval

```bash
# Retrieve all source
sf project retrieve start --source-dir force-app

# Retrieve specific metadata
sf project retrieve start --metadata ApexClass:MyClass

# Retrieve by package.xml
sf project retrieve start --manifest package.xml

# Preview what would be retrieved
sf project retrieve preview --target-org myorg

# Check retrieval status
sf project retrieve report --job-id <job_id>
```

---

## Apex Operations

### Running Apex

```bash
# Execute anonymous Apex from file
sf apex run --file script.apex

# Execute anonymous Apex inline
sf apex run --apex-code-file <(echo "System.debug('Hello World');")

# Execute with specific org
sf apex run --file script.apex --target-org myorg
```

### Testing

```bash
# Run all tests
sf apex run test --test-level RunAllTestsInOrg

# Run specific test class
sf apex run test --class-names MyTestClass

# Run multiple test classes
sf apex run test --class-names MyTestClass,AnotherTestClass

# Run tests with code coverage
sf apex run test --test-level RunLocalTests --code-coverage

# Run tests and wait for completion
sf apex run test --test-level RunLocalTests --wait 10

# Get test results
sf apex get test --test-run-id <test_run_id>

# Get code coverage
sf apex get test --test-run-id <test_run_id> --code-coverage
```

### Logs

```bash
# Get debug logs
sf apex log get --number 5

# Tail logs (watch in real-time)
sf apex log tail

# Get specific log
sf apex log get --log-id <log_id>
```

---

## Package Operations

### First-Generation Packages (1GP)

```bash
# Create package version
sf package1 version create --package-id 033xx0000000001 --name "My Package v1.0"

# List package versions
sf package1 version list --package-id 033xx0000000001

# Install package
sf package install --package "04txx0000000001"
```

### Second-Generation Packages (2GP)

```bash
# Create package
sf package create --name "My Package" --package-type Unlocked --path force-app

# Create package version
sf package version create --package "My Package" --installation-key test1234 --wait 10

# List packages
sf package list

# List package versions
sf package version list --package "My Package"

# Install package
sf package install --package "04txx0000000001AAA" --wait 10

# Uninstall package
sf package uninstall --package "04txx0000000001AAA"
```

---

## Project Operations

```bash
# Create new Salesforce DX project
sf project generate --name my-project

# Create manifest (package.xml)
sf project generate manifest --source-dir force-app --name package

# Convert source to metadata format
sf project convert source --source-dir force-app --output-dir metadata

# Convert metadata to source format
sf project convert mdapi --root-dir metadata --output-dir force-app
```

---

## Useful Flags

### Common Flags (work with most commands)

```bash
--target-org <alias>     # Specify which org to use
--json                   # Output in JSON format
--help                   # Show help for command
--api-version <version>  # Specify API version (e.g., 59.0)
```

### Deployment Flags

```bash
--dry-run               # Validate without deploying
--test-level <level>    # NoTestRun, RunSpecifiedTests, RunLocalTests, RunAllTestsInOrg
--wait <minutes>        # Wait for command to complete (default: 33)
--ignore-warnings       # Deploy even if warnings
--ignore-errors         # Continue on errors
```

### Query Flags

```bash
--result-format <format>  # human, csv, json (default: human)
--use-tooling-api        # Use Tooling API instead of REST API
```

---

## Environment Variables

```bash
# Set default org
export SF_TARGET_ORG=myorg

# Set default API version
export SF_API_VERSION=59.0

# Set log level
export SF_LOG_LEVEL=debug

# Disable telemetry
export SF_DISABLE_TELEMETRY=true
```

---

## Troubleshooting

### Check CLI Version

```bash
sf --version
sf plugins --core
```

### Update CLI

```bash
npm update -g @salesforce/cli
```

### Clear Cache

```bash
sf plugins:reset
```

### Enable Debug Mode

```bash
sf data query --query "SELECT Id FROM Account" --json --loglevel debug
```

### Check for Updates

```bash
sf update
```

---

## Common Workflows

### Deploy to Production

```bash
# 1. Validate with tests
sf project deploy start --source-dir force-app --target-org production --test-level RunLocalTests --dry-run

# 2. Note the job ID from validation

# 3. Quick deploy using validation ID
sf project deploy quick --job-id <validation_job_id> --target-org production
```

### Refresh Sandbox

```bash
# 1. Retrieve from production
sf project retrieve start --source-dir force-app --target-org production

# 2. Deploy to sandbox
sf project deploy start --source-dir force-app --target-org sandbox
```

### Create and Test in Scratch Org

```bash
# 1. Create scratch org
sf org create scratch --definition-file config/project-scratch-def.json --alias feature-test

# 2. Push source
sf project deploy start --source-dir force-app --target-org feature-test

# 3. Import test data
sf data import tree --plan ./data/sample-data-plan.json --target-org feature-test

# 4. Open org
sf org open --target-org feature-test

# 5. Run tests
sf apex run test --test-level RunLocalTests --target-org feature-test

# 6. Delete when done
sf org delete scratch --target-org feature-test
```

---

## Tips & Tricks

1. **Use Aliases**: Always use meaningful aliases for orgs
   ```bash
   sf org login web --alias prod-us
   sf org login web --alias sandbox-qa
   ```

2. **Set Default Org**: Avoid typing `--target-org` every time
   ```bash
   sf config set target-org=myorg
   ```

3. **Use JSON Output for Scripting**: Parse results programmatically
   ```bash
   sf data query --query "SELECT Id FROM Account" --json | jq '.result.records'
   ```

4. **Save Complex Queries**: Store in files for reuse
   ```bash
   echo "SELECT Id, Name FROM Account WHERE CreatedDate = TODAY" > query.soql
   sf data query --file query.soql
   ```

5. **Check Before Deploying**: Always validate first
   ```bash
   sf project deploy start --source-dir force-app --dry-run
   ```

6. **Monitor API Usage**: Keep track of limits
   ```bash
   sf org display limits | grep "DailyApiRequests"
   ```

---

## Additional Resources

- **Official CLI Reference**: https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/
- **Salesforce DX Guide**: https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/
- **GitHub Repository**: https://github.com/salesforcecli/cli

---

**Last Updated**: June 11, 2026
