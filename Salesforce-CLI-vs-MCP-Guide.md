# Salesforce CLI vs Salesforce MCP: Complete Guide

**Document Version:** 1.0  
**Last Updated:** June 11, 2026  
**Audience:** Development Team, Salesforce Administrators, Business Analysts

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [What is Salesforce CLI?](#what-is-salesforce-cli)
3. [What is Salesforce MCP?](#what-is-salesforce-mcp)
4. [Salesforce CLI: Detailed Analysis](#salesforce-cli-detailed-analysis)
5. [Salesforce MCP: Detailed Analysis](#salesforce-mcp-detailed-analysis)
6. [Comparison Matrix](#comparison-matrix)
7. [When to Use Each Tool](#when-to-use-each-tool)
8. [Real-World Scenarios](#real-world-scenarios)
9. [Best Practices](#best-practices)
10. [Getting Started](#getting-started)
11. [FAQ](#faq)
12. [Additional Resources](#additional-resources)

---

## Executive Summary

This guide compares two powerful tools for working with Salesforce:

- **Salesforce CLI**: Official command-line interface for automation, deployment, and development
- **Salesforce MCP**: AI-powered natural language interface for interactive data operations

**Key Recommendation:** Use both tools together for maximum productivity. Use MCP for learning and exploration, CLI for automation and deployment.

---

## What is Salesforce CLI?

### Overview

**Salesforce CLI** is an official command-line tool provided by Salesforce that enables developers and administrators to interact with Salesforce orgs directly from their terminal or command prompt.

### Core Capabilities

- **Org Management**: Authenticate and manage multiple Salesforce orgs (production, sandbox, scratch orgs)
- **Metadata Operations**: Deploy and retrieve Salesforce metadata (Apex, Lightning, objects, fields)
- **Data Operations**: Query, import, export, and manipulate Salesforce data
- **Development Workflow**: Create and manage Salesforce DX projects
- **Automation**: Script repetitive tasks and integrate with CI/CD pipelines
- **Package Development**: Create and manage first and second-generation packages

### Installation

```bash
# Install via npm (requires Node.js)
npm install -g @salesforce/cli

# Verify installation
sf --version
```

### Basic Usage Examples

```bash
# Authenticate to an org
sf org login web --alias myorg

# Query data
sf data query --query "SELECT Id, Name FROM Account LIMIT 10"

# Deploy metadata
sf project deploy start --source-dir force-app

# Run Apex tests
sf apex run test --test-level RunLocalTests

# Create scratch org
sf org create scratch --definition-file config/project-scratch-def.json
```

---

## What is Salesforce MCP?

### Overview

**Salesforce MCP (Model Context Protocol)** is an AI-powered integration that connects AI assistants with Salesforce through a standardized protocol, enabling natural language interaction with your Salesforce org.

### Core Capabilities

- **Natural Language Queries**: Ask questions in plain English
- **CRUD Operations**: Create, read, update, delete records conversationally
- **Metadata Discovery**: Automatically discover object structures and requirements
- **Field Validation**: Check data validity before creating records
- **Intelligent Assistance**: Get explanations, suggestions, and error interpretation
- **Relationship Navigation**: Understand and query related objects automatically

### How It Works

```
User: "Show me all opportunities closing this month worth over $100k"
AI Assistant: [Constructs SOQL query automatically]
              [Executes query]
              [Returns formatted results with context]

User: "Create a test opportunity"
AI Assistant: [Checks required fields]
              [Validates data]
              [Creates record]
              [Confirms success with details]
```

### Available Operations

- Query Salesforce data (SOQL)
- Create records
- Read/retrieve records
- Update records
- Delete records (with confirmation)
- Describe objects and fields
- Get mandatory fields
- Get picklist values
- Find record type IDs
- Validate record data
- Create complete quote structures

---

## Salesforce CLI: Detailed Analysis

### Advantages ✅

| Advantage | Description | Business Value |
|-----------|-------------|----------------|
| **Official Support** | Maintained by Salesforce with guaranteed compatibility | Reduced risk, reliable updates |
| **Comprehensive Coverage** | Supports 95%+ of Salesforce operations | One tool for all needs |
| **Automation-Friendly** | Perfect for scripts, CI/CD, batch jobs | Increased efficiency, reduced manual work |
| **Metadata Management** | Deploy Apex, Lightning, objects, fields, configs | Full development lifecycle support |
| **Scratch Org Support** | Create temporary development environments | Isolated testing, parallel development |
| **Version Control Integration** | Seamless Git workflows | Better collaboration, change tracking |
| **Bulk Operations** | Handle thousands of records efficiently | Scalable data operations |
| **Package Development** | Build and distribute AppExchange apps | ISV and enterprise modularization |
| **Cross-Platform** | Works on Windows, Mac, Linux | Team flexibility |
| **Extensive Documentation** | Rich official docs and community resources | Easier troubleshooting, learning |

### Disadvantages ❌

| Disadvantage | Description | Mitigation Strategy |
|--------------|-------------|---------------------|
| **Steep Learning Curve** | Complex syntax, 100+ commands | Invest in training, use documentation |
| **Installation Required** | Must install Node.js + CLI tools | One-time setup, document process |
| **Command Complexity** | Operations often require multiple steps | Create reusable scripts |
| **Cryptic Errors** | Error messages can be unclear | Build knowledge base of common errors |
| **Version Management** | Must keep CLI updated | Include in maintenance schedule |
| **Authentication Overhead** | Managing multiple org connections | Use aliases and config files |
| **No Interactivity** | Command-based only | Combine with MCP for exploration |
| **Manual Discovery** | Must look up schemas separately | Use MCP for discovery first |
| **No Intelligence** | Doesn't suggest next steps | Document common workflows |
| **JSON Parsing Required** | Output needs parsing for scripts | Use jq or similar tools |

### Limitations ⚠️

| Limitation | Impact | Workaround |
|------------|--------|------------|
| **API Rate Limits** | 15,000-200,000 calls/day depending on edition | Use Bulk API, monitor usage |
| **Deployment Time** | Large deployments can take 30+ minutes | Deploy incrementally, use quick deploy |
| **Metadata Coverage** | Some settings can't be deployed | Document manual steps |
| **Test Requirements** | Production deployments must run all tests | Maintain high test coverage |
| **File Size Limits** | Max 50 MB per deployment, 10,000 files | Split large deployments |
| **No Natural Language** | Must know exact syntax | Use MCP for exploration |
| **No Context Memory** | Each command is independent | Use scripts for multi-step operations |
| **Learning Barrier** | Requires Salesforce + CLI knowledge | Provide team training |

### Use Cases - When CLI is Essential

1. **CI/CD Pipelines**: Automated testing and deployment
2. **Metadata Deployment**: Deploying Apex, Lightning, custom objects
3. **Scratch Org Management**: Creating development environments
4. **Bulk Data Operations**: Processing 1000+ records
5. **Package Development**: Building AppExchange apps
6. **Scheduled Automation**: Cron jobs, scheduled scripts
7. **Version Control Workflows**: Git integration, pull requests
8. **Multi-Org Deployments**: Deploying to multiple environments

---

## Salesforce MCP: Detailed Analysis

### Advantages ✅

| Advantage | Description | Business Value |
|-----------|-------------|----------------|
| **Natural Language** | Talk normally, no syntax to memorize | Zero learning curve, immediate productivity |
| **Context-Aware** | Remembers conversation, chains operations | Faster workflows, less repetition |
| **Intelligent Assistance** | Explains results, suggests next steps | Better understanding, fewer errors |
| **Automatic Discovery** | Finds required fields, picklist values | Saves time, reduces errors |
| **Error Handling** | Interprets errors and suggests fixes | Faster troubleshooting |
| **No Installation** | Works through IDE, no separate tools | Instant access, no setup |
| **Minimal Learning Curve** | Just describe what you want | Accessible to non-technical users |
| **Validation Built-In** | Checks data validity before operations | Prevents errors before they happen |
| **Multi-Step Orchestration** | Handles complex workflows automatically | Simplifies complex tasks |
| **Documentation Included** | Explains Salesforce concepts as you work | Learning while doing |
| **Safety Features** | Confirmation required for destructive actions | Prevents accidental data loss |
| **Relationship Understanding** | Navigates object relationships intelligently | Easier complex queries |

### Disadvantages ❌

| Disadvantage | Description | Mitigation Strategy |
|--------------|-------------|---------------------|
| **Requires AI Assistant** | Only works in IDE environment | Use CLI for standalone needs |
| **Not Standalone** | Can't use outside of IDE context | Combine with CLI for automation |
| **Limited Automation** | Not designed for CI/CD or batch scripts | Use CLI for automation |
| **Interpretation Layer** | Adds abstraction | Be specific in requests |
| **Potential Ambiguity** | Natural language can be unclear | Provide clear, detailed requests |
| **No Direct CLI Access** | Can't drop to raw commands | Switch to CLI when needed |
| **Session-Based** | Context is conversation-specific | Document important findings |
| **Network Dependency** | Requires AI service + Salesforce connection | Ensure stable connectivity |
| **Less Low-Level Control** | Abstracts technical details | Use CLI for fine-grained control |
| **Not for Package Dev** | Doesn't support scratch orgs or packages | Use CLI for development |

### Limitations ⚠️

| Limitation | Impact | Workaround |
|------------|--------|------------|
| **No Metadata Deployment** | Can't deploy Apex, Lightning components | Use CLI for deployments |
| **No Scratch Org Management** | Can't create/manage dev orgs | Use CLI for org management |
| **No Version Control Ops** | Not integrated with Git | Use CLI for Git workflows |
| **No CI/CD Integration** | Not designed for pipelines | Use CLI for automation |
| **Limited Bulk Operations** | Better for <100 records | Use CLI for bulk operations |
| **No Package Management** | Can't create or install packages | Use CLI for packages |
| **Conversation Scope** | Works best for interactive tasks | Use for exploration, not automation |
| **No File Operations** | Can't retrieve/deploy metadata files | Use CLI for file operations |
| **Session Memory Only** | Doesn't remember across sessions | Document important information |

### Use Cases - When MCP is Ideal

1. **Learning Salesforce**: Understanding object structures and relationships
2. **Ad-Hoc Queries**: Quick data lookups and exploration
3. **Data Investigation**: Finding patterns and troubleshooting
4. **Small Data Changes**: Updating <100 records
5. **Field Discovery**: Understanding what fields exist and are required
6. **Validation**: Checking data before bulk operations
7. **Prototyping**: Testing ideas and approaches
8. **Training**: Teaching team members about Salesforce

---

## Comparison Matrix

### Feature Comparison

| Feature | Salesforce CLI | Salesforce MCP | Winner |
|---------|----------------|----------------|--------|
| **Natural Language Interface** | ❌ No | ✅ Yes | MCP |
| **Metadata Deployment** | ✅ Yes | ❌ No | CLI |
| **Data CRUD Operations** | ✅ Yes | ✅ Yes | Tie |
| **SOQL Queries** | ✅ Yes | ✅ Yes | Tie |
| **Scratch Org Management** | ✅ Yes | ❌ No | CLI |
| **CI/CD Integration** | ✅ Yes | ❌ No | CLI |
| **Learning Curve** | ❌ Steep | ✅ Easy | MCP |
| **Context Awareness** | ❌ No | ✅ Yes | MCP |
| **Installation Required** | ❌ Yes | ✅ No | MCP |
| **Automation/Scripting** | ✅ Excellent | ❌ Limited | CLI |
| **Interactive Help** | ❌ No | ✅ Yes | MCP |
| **Field Discovery** | ⚠️ Manual | ✅ Automatic | MCP |
| **Bulk Operations (1000+ records)** | ✅ Excellent | ❌ Poor | CLI |
| **Error Explanation** | ❌ No | ✅ Yes | MCP |
| **Data Validation** | ❌ Manual | ✅ Automatic | MCP |
| **Package Development** | ✅ Yes | ❌ No | CLI |
| **Version Control** | ✅ Yes | ❌ No | CLI |
| **Multi-Org Management** | ✅ Yes | ⚠️ Limited | CLI |
| **Relationship Queries** | ⚠️ Manual | ✅ Assisted | MCP |
| **Documentation** | ⚠️ External | ✅ Built-in | MCP |

### Performance Comparison

| Operation | CLI Performance | MCP Performance | Best Choice |
|-----------|----------------|-----------------|-------------|
| **Single Record Query** | Fast (< 1 sec) | Fast (< 2 sec) | Either |
| **Complex Query** | Fast (< 2 sec) | Fast (< 3 sec) | Either |
| **Create 1 Record** | Fast (< 1 sec) | Fast (< 2 sec) | Either |
| **Create 100 Records** | Fast (< 5 sec) | Slow (30+ sec) | CLI |
| **Create 10,000 Records** | Fast (1-5 min) | Not Recommended | CLI |
| **Metadata Deployment** | Medium (5-30 min) | Not Supported | CLI |
| **Field Discovery** | Manual (2-5 min) | Automatic (< 5 sec) | MCP |
| **Learning New Object** | Manual (10-30 min) | Guided (5-10 min) | MCP |

---

## When to Use Each Tool

### Decision Tree

```
Need to deploy code or metadata?
├─ YES → Use Salesforce CLI
└─ NO → Continue

Need to process 1000+ records?
├─ YES → Use Salesforce CLI
└─ NO → Continue

Need CI/CD integration?
├─ YES → Use Salesforce CLI
└─ NO → Continue

Need to create/manage scratch orgs?
├─ YES → Use Salesforce CLI
└─ NO → Continue

Learning or exploring Salesforce?
├─ YES → Use Salesforce MCP
└─ NO → Continue

Need to make small data changes (<100 records)?
├─ YES → Use Salesforce MCP
└─ NO → Continue

Need interactive help and guidance?
├─ YES → Use Salesforce MCP
└─ NO → Use Salesforce CLI
```

### Recommended Tool by Role

| Role | Primary Tool | Secondary Tool | Reason |
|------|-------------|----------------|--------|
| **Salesforce Developer** | CLI | MCP | Needs deployment, automation, scratch orgs |
| **Salesforce Admin** | MCP | CLI | Focuses on data, configuration, exploration |
| **Business Analyst** | MCP | - | Needs data exploration, no coding required |
| **DevOps Engineer** | CLI | - | Needs automation, CI/CD integration |
| **QA Tester** | MCP | CLI | Needs data setup, validation, exploration |
| **Data Analyst** | MCP | CLI | Needs queries, small updates, exploration |
| **Architect** | CLI | MCP | Needs full control, but MCP for exploration |
| **New Team Member** | MCP | CLI | Start with easy tool, graduate to CLI |

---

## Real-World Scenarios

### Scenario 1: New Feature Development

**Objective**: Develop a new Apex trigger and deploy to production

**Workflow**:
1. **MCP**: "What fields does the Opportunity object have?"
   - Understand object structure
   - Identify fields to use in trigger

2. **CLI**: Create scratch org
   ```bash
   sf org create scratch --definition-file config/project-scratch-def.json
   ```

3. **CLI**: Deploy trigger to scratch org
   ```bash
   sf project deploy start --source-dir force-app
   ```

4. **MCP**: "Create test opportunities to verify trigger"
   - Create test data interactively
   - Verify trigger behavior

5. **CLI**: Run tests and deploy to production
   ```bash
   sf apex run test --test-level RunLocalTests
   sf project deploy start --source-dir force-app --target-org production
   ```

**Tools Used**: Both (CLI for deployment, MCP for exploration and testing)

---

### Scenario 2: Data Cleanup

**Objective**: Fix 50 opportunity records with incorrect stage

**Workflow**:
1. **MCP**: "Show me all opportunities in 'Closed Lost' stage that were modified today"
   - Identify affected records
   - Verify the issue

2. **MCP**: "What are the valid values for StageName?"
   - Understand correct values
   - Decide on fix

3. **MCP**: "Update these opportunities to 'Prospecting' stage"
   - Fix records interactively
   - Get confirmation for each batch

4. **MCP**: "Verify the changes were applied correctly"
   - Confirm fix was successful

**Tools Used**: MCP only (small dataset, interactive verification needed)

---

### Scenario 3: Bulk Data Migration

**Objective**: Migrate 10,000 account records from legacy system

**Workflow**:
1. **MCP**: "What fields are required to create an Account?"
   - Understand requirements
   - Identify mandatory fields

2. **MCP**: "Show me an example Account record"
   - See data structure
   - Understand format

3. **Prepare CSV file** with 10,000 records based on learnings

4. **CLI**: Bulk import
   ```bash
   sf data import bulk --sobject Account --file accounts.csv --wait 10
   ```

5. **MCP**: "Show me accounts created in the last hour"
   - Verify import success
   - Check for errors

**Tools Used**: Both (MCP for learning, CLI for bulk operation)

---

### Scenario 4: CI/CD Pipeline Setup

**Objective**: Automate deployment from Git to Salesforce

**Workflow**:
1. **CLI**: Set up authentication
   ```bash
   sf org login jwt --client-id $CLIENT_ID --jwt-key-file key.pem
   ```

2. **CLI**: Create deployment script
   ```bash
   #!/bin/bash
   sf project deploy start --source-dir force-app --target-org production
   sf apex run test --test-level RunLocalTests --wait 10
   ```

3. **CLI**: Integrate with GitHub Actions
   ```yaml
   - name: Deploy to Salesforce
     run: |
       npm install -g @salesforce/cli
       sf org login jwt --client-id ${{ secrets.CLIENT_ID }}
       sf project deploy start --source-dir force-app
   ```

4. **MCP**: (After deployment) "Show me the latest deployments"
   - Verify deployment success
   - Check for any issues

**Tools Used**: Primarily CLI (automation required), MCP for verification

---

### Scenario 5: Troubleshooting Production Issue

**Objective**: Investigate why opportunities aren't being created

**Workflow**:
1. **MCP**: "Show me opportunities created in the last 24 hours"
   - Check if any were created
   - Identify pattern

2. **MCP**: "What validation rules exist on Opportunity?"
   - Understand business rules
   - Identify potential blockers

3. **MCP**: "What are the mandatory fields for Opportunity?"
   - Verify all required fields are being provided

4. **MCP**: "Try creating a test opportunity with these values"
   - Reproduce the issue
   - See actual error message

5. **CLI**: Check deployment history
   ```bash
   sf project deploy report --job-id <id>
   ```

6. **Fix identified issue** (validation rule, missing field, etc.)

**Tools Used**: Primarily MCP (investigation and testing), CLI for deployment history

---

## Best Practices

### General Recommendations

1. **Start with MCP for Learning**
   - Use MCP to understand Salesforce structure
   - Explore objects, fields, and relationships
   - Build mental model before automating

2. **Graduate to CLI for Automation**
   - Once you understand the operations, automate with CLI
   - Create reusable scripts
   - Integrate with CI/CD

3. **Use MCP for Verification**
   - After CLI operations, verify with MCP
   - Interactive confirmation of changes
   - Quick spot-checking

4. **Document Your Workflows**
   - Capture successful CLI commands
   - Note MCP queries that were helpful
   - Build team knowledge base

5. **Combine Tools in Workflows**
   - Don't treat them as either/or
   - Use each tool's strengths
   - Create hybrid workflows

### Team Collaboration

1. **Establish Tool Standards**
   - Define when to use each tool
   - Create team guidelines
   - Share best practices

2. **Create Shared Scripts**
   - Build library of CLI scripts
   - Document common MCP queries
   - Version control everything

3. **Cross-Train Team Members**
   - Ensure everyone knows both tools
   - Share knowledge and tips
   - Pair programming sessions

4. **Build Knowledge Base**
   - Document common errors and solutions
   - Create FAQ for each tool
   - Share successful workflows

### Security Best Practices

1. **CLI Authentication**
   - Use JWT for CI/CD (no passwords in code)
   - Rotate credentials regularly
   - Use separate service accounts
   - Never commit credentials to Git

2. **MCP Usage**
   - Be cautious with destructive operations
   - Always confirm before deleting
   - Verify changes after updates
   - Use in secure environments only

3. **Access Control**
   - Limit production access
   - Use least privilege principle
   - Audit tool usage
   - Monitor API usage

---

## Getting Started

### Setting Up Salesforce CLI

**Prerequisites**:
- Node.js 18 or later
- Git (for version control)
- Salesforce org access

**Installation Steps**:

```bash
# 1. Install Salesforce CLI
npm install -g @salesforce/cli

# 2. Verify installation
sf --version

# 3. Authenticate to your org
sf org login web --alias myorg

# 4. Verify authentication
sf org display --target-org myorg

# 5. Set default org (optional)
sf config set target-org=myorg
```

**First Commands to Try**:

```bash
# Query data
sf data query --query "SELECT Id, Name FROM Account LIMIT 5"

# Get org limits
sf org display limits

# List all orgs
sf org list

# Get help
sf --help
sf data --help
```

### Setting Up Salesforce MCP

**Prerequisites**:
- IDE with MCP support (Windsurf, Cursor, etc.)
- Salesforce org credentials configured in MCP server
- Active internet connection

**Getting Started**:

1. **Verify MCP Connection**:
   - Ask: "Can you connect to my Salesforce org?"
   - AI will confirm connection status

2. **First Queries to Try**:
   - "Show me all accounts"
   - "What fields does Opportunity have?"
   - "What's required to create a Contact?"

3. **Practice Operations**:
   - Create a test record
   - Query and update it
   - Delete it (with confirmation)

### Learning Resources

**Salesforce CLI**:
- Official Documentation: https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/
- Trailhead Module: "Salesforce DX"
- GitHub: https://github.com/salesforcecli/cli

**Salesforce MCP**:
- Model Context Protocol: https://modelcontextprotocol.io/
- Practice with AI assistant in your IDE
- This documentation!

**Salesforce General**:
- Trailhead: https://trailhead.salesforce.com/
- Developer Documentation: https://developer.salesforce.com/docs
- Community Forums: https://trailblazers.salesforce.com/

---

## FAQ

### General Questions

**Q: Do I need to choose between CLI and MCP?**  
A: No! Use both. They complement each other. Use MCP for learning and exploration, CLI for automation and deployment.

**Q: Which tool should I learn first?**  
A: Start with MCP if you're new to Salesforce. It's easier to learn and helps you understand Salesforce structure. Graduate to CLI for automation.

**Q: Can MCP replace CLI?**  
A: No. MCP cannot deploy metadata, manage scratch orgs, or integrate with CI/CD. CLI is essential for serious development.

**Q: Can CLI replace MCP?**  
A: Technically yes, but MCP makes learning and exploration much easier. CLI has a steep learning curve.

### Salesforce CLI Questions

**Q: How do I handle multiple orgs with CLI?**  
A: Use aliases:
```bash
sf org login web --alias dev
sf org login web --alias staging
sf org login web --alias production

# Use specific org
sf data query --query "SELECT Id FROM Account" --target-org dev
```

**Q: What if CLI deployment fails?**  
A: Check the deployment report:
```bash
sf project deploy report --job-id <id>
```
Review errors, fix issues, and redeploy.

**Q: How do I update Salesforce CLI?**  
A:
```bash
npm update -g @salesforce/cli
```

**Q: Can I use CLI without Node.js?**  
A: No, Salesforce CLI requires Node.js. Install it from https://nodejs.org/

### Salesforce MCP Questions

**Q: How do I know if MCP is connected to my org?**  
A: Ask the AI assistant: "Can you query my Salesforce org?" or "Show me an account record."

**Q: Can MCP deploy Apex code?**  
A: No, MCP focuses on data operations. Use CLI for metadata deployment.

**Q: Is MCP secure?**  
A: Yes, when used properly. MCP requires confirmation for destructive operations. Always verify changes.

**Q: Can I use MCP for bulk operations?**  
A: MCP works best for <100 records. For larger operations, use CLI.

### Technical Questions

**Q: What are API limits?**  
A: Salesforce limits API calls per day:
- Developer Edition: 15,000 calls/day
- Enterprise Edition: 100,000 calls/day
- Unlimited Edition: 200,000 calls/day

Both CLI and MCP consume API calls.

**Q: How do I check my API usage?**  
A: Using CLI:
```bash
sf org display limits --target-org myorg
```

Using MCP:
"Show me my org's API limits"

**Q: What's the difference between Metadata API and Data API?**  
A:
- **Metadata API**: Deploy code, objects, fields, configurations (CLI only)
- **Data API**: Query and manipulate records (both CLI and MCP)

**Q: Can I use both tools simultaneously?**  
A: Yes! They work independently. You can run CLI commands while using MCP.

---

## Additional Resources

### Official Documentation

- **Salesforce CLI Reference**: https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/
- **Salesforce DX Developer Guide**: https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/
- **Model Context Protocol**: https://modelcontextprotocol.io/
- **Salesforce APIs**: https://developer.salesforce.com/docs/apis

### Training & Certification

- **Trailhead**: https://trailhead.salesforce.com/
  - Salesforce DX Module
  - Apex Basics
  - Data Management

- **Salesforce Certifications**:
  - Platform Developer I
  - Administrator
  - Platform App Builder

### Community & Support

- **Salesforce Developer Forums**: https://developer.salesforce.com/forums
- **Trailblazer Community**: https://trailblazers.salesforce.com/
- **Stack Overflow**: Tag `salesforce` or `salesforce-cli`
- **GitHub Issues**: https://github.com/salesforcecli/cli/issues

### Tools & Extensions

- **VS Code Extensions**:
  - Salesforce Extension Pack
  - Salesforce CLI Integration

- **Browser Extensions**:
  - Salesforce Inspector
  - Salesforce Advanced Code Searcher

- **Third-Party Tools**:
  - Gearset (deployment)
  - Copado (DevOps)
  - Flosum (release management)

---

## Conclusion

Both Salesforce CLI and Salesforce MCP are powerful tools that serve different purposes:

- **Salesforce CLI** is your automation engine - essential for deployment, CI/CD, and bulk operations
- **Salesforce MCP** is your intelligent guide - perfect for learning, exploration, and interactive work

**The winning strategy**: Use both tools together. Learn with MCP, automate with CLI, and verify with MCP.

---

## Document Change Log

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | June 11, 2026 | Initial document creation | AI Assistant |

---

## Feedback & Contributions

This is a living document. If you have suggestions, corrections, or additional use cases, please:
1. Update this document
2. Share with the team
3. Version control your changes

---

**End of Document**
