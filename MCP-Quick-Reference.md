# Salesforce MCP Quick Reference

**Quick guide for using Salesforce MCP with AI Assistant**

---

## What is Salesforce MCP?

Salesforce MCP (Model Context Protocol) allows you to interact with Salesforce using natural language through an AI assistant. No syntax to memorize - just describe what you want!

---

## Available Operations

### 1. Query Data (SOQL)

**Natural Language Examples**:
- "Show me all accounts"
- "Find opportunities closing this month"
- "Get contacts with email addresses"
- "Show me accounts created today with their opportunities"
- "Find all opportunities over $100,000"

**What the AI Does**:
- Constructs SOQL query automatically
- Executes query
- Returns formatted results
- Explains what was found

---

### 2. Create Records

**Natural Language Examples**:
- "Create a test account named Acme Corp"
- "Create an opportunity for Q1 2026"
- "Add a new contact named John Doe"
- "Create a test opportunity with amount $50,000"

**What the AI Does**:
- Checks required fields automatically
- Validates data before creating
- Creates the record
- Returns the new record ID
- Confirms success

---

### 3. Read/Retrieve Records

**Natural Language Examples**:
- "Show me account with ID 001xx000003DGb2"
- "Get details of opportunity 006xx000001T2gZ"
- "What's in this record: 003xx000004TgH1"

**What the AI Does**:
- Retrieves the specific record
- Shows all field values
- Explains the record type
- Highlights important fields

---

### 4. Update Records

**Natural Language Examples**:
- "Update opportunity 006xxx to Closed Won"
- "Change the amount to $75,000 for this opportunity"
- "Set the account's industry to Technology"
- "Update contact email to newemail@example.com"

**What the AI Does**:
- Validates the update
- Applies changes
- Confirms success
- Shows updated values

---

### 5. Delete Records

**Natural Language Examples**:
- "Delete this test opportunity"
- "Remove account 001xx000003DGb2"
- "Delete the contact I just created"

**What the AI Does**:
- Shows what will be deleted (safety feature)
- Asks for confirmation
- Deletes only after confirmation
- Confirms deletion

**Safety Feature**: Always requires confirmation before deleting!

---

### 6. Describe Objects

**Natural Language Examples**:
- "What fields does Opportunity have?"
- "Describe the Account object"
- "Show me all fields on Contact"
- "What's the structure of the Case object?"

**What the AI Does**:
- Retrieves complete object metadata
- Lists all fields with types
- Shows relationships
- Explains record types
- Identifies required fields

---

### 7. Get Mandatory Fields

**Natural Language Examples**:
- "What fields are required to create an Opportunity?"
- "What do I need to create a Contact?"
- "Show me mandatory fields for Account"

**What the AI Does**:
- Lists all required fields
- Shows field types
- Explains what each field is for
- Helps you prepare data

---

### 8. Get Picklist Values

**Natural Language Examples**:
- "What are valid values for Opportunity Stage?"
- "Show me picklist options for Account Industry"
- "What can I set for Lead Status?"

**What the AI Does**:
- Retrieves all active picklist values
- Shows labels and API values
- Explains what each option means
- Helps you choose correct value

---

### 9. Find Record Types

**Natural Language Examples**:
- "What record types exist for Opportunity?"
- "Show me Account record types"
- "Find the ID for 'New Business' record type"

**What the AI Does**:
- Lists all record types
- Shows which are active/available
- Finds specific record type IDs
- Explains differences between types

---

### 10. Validate Data

**Natural Language Examples**:
- "Can I create an Opportunity with just a Name?"
- "Validate this data before creating"
- "Check if these fields are enough"

**What the AI Does**:
- Checks against required fields
- Identifies missing fields
- Validates data types
- Prevents errors before they happen

---

## Example Conversations

### Example 1: Learning About Objects

```
You: "I need to create opportunities. What do I need to know?"

AI: Let me help you understand Opportunities:
    1. Checking required fields...
    2. Getting valid stage values...
    3. Showing example record...
    
    Required fields:
    - Name (text)
    - StageName (picklist - see valid values below)
    - CloseDate (date)
    
    Valid Stage values:
    - Prospecting
    - Qualification
    - Needs Analysis
    [etc.]
    
    Would you like me to create a test opportunity?
```

---

### Example 2: Data Exploration

```
You: "Show me our biggest opportunities this quarter"

AI: I'll query opportunities for this quarter sorted by amount...
    
    Found 15 opportunities:
    1. Acme Corp Deal - $500,000 - Closed Won
    2. Global Industries - $350,000 - Negotiation
    3. Tech Solutions - $275,000 - Proposal
    [etc.]
    
    Total value: $2,450,000
    
    Would you like to see details of any specific opportunity?
```

---

### Example 3: Data Cleanup

```
You: "Find all opportunities in 'Closed Lost' stage from today"

AI: Searching for opportunities...
    
    Found 3 opportunities closed lost today:
    1. Small Deal - $5,000
    2. Test Opportunity - $10,000
    3. Another Test - $1,000
    
You: "Change them all back to Prospecting"

AI: I'll update these 3 opportunities to Prospecting stage.
    Confirm? (yes/no)
    
You: "yes"

AI: Updating records...
    ✓ Updated Small Deal
    ✓ Updated Test Opportunity
    ✓ Updated Another Test
    
    All 3 opportunities updated successfully!
```

---

### Example 4: Creating Related Records

```
You: "Create an account called Tech Innovations, then create an opportunity for them"

AI: Creating account...
    ✓ Created Account: Tech Innovations (ID: 001xx000003DGb2)
    
    Now creating opportunity. What should I name it?
    
You: "Q2 2026 Deal"

AI: Creating opportunity...
    - Name: Q2 2026 Deal
    - Account: Tech Innovations
    - Stage: Prospecting (default)
    - Close Date: (need this - what date?)
    
You: "June 30, 2026"

AI: ✓ Created Opportunity: Q2 2026 Deal (ID: 006xx000001T2gZ)
    Linked to Account: Tech Innovations
    
    Would you like to add any other details?
```

---

## Tips for Effective Use

### 1. Be Specific

❌ **Vague**: "Show me some records"
✅ **Specific**: "Show me all accounts created this week"

❌ **Vague**: "Update that record"
✅ **Specific**: "Update opportunity 006xxx to Closed Won"

---

### 2. Ask for Help

If you're unsure, just ask:
- "How do I create an opportunity?"
- "What fields can I query on Account?"
- "Explain what StageName means"
- "What's the difference between Account and Contact?"

---

### 3. Verify Before Deleting

Always review what will be deleted:
- "Show me the record first"
- "What will be deleted?"
- AI will always show details before deleting

---

### 4. Use Natural Language

You don't need to know SOQL or API names:
- "Show me accounts" (AI translates to SOQL)
- "Find big opportunities" (AI interprets "big")
- "Get recent contacts" (AI understands "recent")

---

### 5. Chain Operations

You can do multiple things in one conversation:
```
You: "Create a test account, then create an opportunity for it, 
      then show me both records"

AI: [Does all three steps automatically]
```

---

### 6. Ask for Explanations

- "Why did that fail?"
- "What does this error mean?"
- "Explain this field to me"
- "What's the relationship between Account and Opportunity?"

---

## Common Patterns

### Pattern 1: Explore → Test → Implement

```
1. "What fields does X have?" (Explore)
2. "Create a test X record" (Test)
3. "Show me the record I created" (Verify)
4. Now use CLI for bulk operations (Implement)
```

---

### Pattern 2: Find → Filter → Fix

```
1. "Show me all opportunities" (Find)
2. "Filter to only closed lost" (Filter)
3. "Update these to prospecting" (Fix)
```

---

### Pattern 3: Understand → Validate → Create

```
1. "What's required to create a Contact?" (Understand)
2. "Validate this data: FirstName=John, LastName=Doe" (Validate)
3. "Create the contact" (Create)
```

---

## What MCP Can Do

✅ **Data Operations**:
- Query records (SOQL)
- Create records
- Read records
- Update records
- Delete records (with confirmation)

✅ **Metadata Discovery**:
- Describe objects
- List fields
- Get required fields
- Get picklist values
- Find record types

✅ **Validation**:
- Check required fields
- Validate data before creating
- Explain errors

✅ **Guidance**:
- Explain Salesforce concepts
- Suggest next steps
- Interpret errors
- Provide examples

---

## What MCP Cannot Do

❌ **Metadata Deployment**:
- Cannot deploy Apex code
- Cannot create custom fields
- Cannot modify page layouts
- Cannot deploy Lightning components

❌ **Org Management**:
- Cannot create scratch orgs
- Cannot manage sandboxes
- Cannot handle version control

❌ **Bulk Operations**:
- Not ideal for 1000+ records
- Use CLI for bulk imports
- Use CLI for mass updates

❌ **CI/CD**:
- Cannot integrate with pipelines
- Cannot automate deployments
- Not scriptable

**For these operations, use Salesforce CLI instead!**

---

## Best Practices

### 1. Start Small
- Create one test record first
- Verify it works
- Then scale up

### 2. Always Verify
- Check records after creating
- Confirm updates were applied
- Review before deleting

### 3. Document Your Findings
- Save successful queries
- Note required fields
- Keep track of record IDs

### 4. Combine with CLI
- Use MCP to learn
- Use CLI to automate
- Use MCP to verify

### 5. Ask Questions
- Don't guess - ask!
- Request explanations
- Seek clarification

---

## Comparison: MCP vs Direct SOQL

### Using MCP:
```
You: "Show me accounts created this month with more than 100 employees"

AI: [Automatically constructs and executes:]
    SELECT Id, Name, NumberOfEmployees, CreatedDate 
    FROM Account 
    WHERE CreatedDate = THIS_MONTH 
    AND NumberOfEmployees > 100
```

### Using CLI (manual SOQL):
```bash
sf data query --query "SELECT Id, Name, NumberOfEmployees, CreatedDate FROM Account WHERE CreatedDate = THIS_MONTH AND NumberOfEmployees > 100"
```

**MCP Advantage**: No syntax to remember, natural language, automatic formatting

---

## Error Handling

### MCP Handles Errors Intelligently

**Example**:
```
You: "Create an opportunity named Test"

AI: I need more information to create an opportunity:
    - ✓ Name: Test
    - ✗ StageName: Required (missing)
    - ✗ CloseDate: Required (missing)
    
    Valid StageName values:
    - Prospecting
    - Qualification
    - Closed Won
    [etc.]
    
    Please provide StageName and CloseDate.
```

**CLI Would Show**:
```
ERROR: Required fields are missing: [StageName, CloseDate]
```

**MCP Advantage**: Explains what's missing and shows valid options

---

## Integration with Development Workflow

### Recommended Workflow:

1. **Learn with MCP**:
   - "What fields does X have?"
   - "Show me example records"
   - "What's required?"

2. **Prototype with MCP**:
   - Create test records
   - Try different values
   - Verify behavior

3. **Automate with CLI**:
   - Write scripts based on learnings
   - Process bulk data
   - Deploy to multiple orgs

4. **Verify with MCP**:
   - "Show me what was created"
   - "Verify the updates"
   - "Check for errors"

---

## Sample Use Cases

### Use Case 1: New Team Member Onboarding
```
New team member: "I don't know Salesforce. Where do I start?"

AI: Let me show you the basics:
    1. Accounts = Companies
    2. Contacts = People at companies
    3. Opportunities = Potential sales
    
    Want to see examples of each?
```

### Use Case 2: Data Investigation
```
Admin: "Why aren't opportunities being created?"

AI: Let me help investigate:
    1. Checking recent opportunities... (found 0 today)
    2. Checking validation rules... (found 3 active rules)
    3. Checking required fields... (Name, Stage, CloseDate)
    
    Let's test creating one to see the error...
```

### Use Case 3: Quick Data Fix
```
User: "I need to update 20 opportunity amounts"

AI: I can help with that. Show me the opportunities:
    [Lists 20 opportunities]
    
    What should the new amounts be?
    [Updates each one]
    [Confirms all updates]
```

---

## Keyboard Shortcuts & Tips

### In Your IDE:
- **Ask follow-up questions**: Continue the conversation
- **Reference previous results**: "Update that record", "Show me more"
- **Request clarification**: "What does that mean?", "Explain"
- **Copy record IDs**: Easily copy from AI responses

### Conversation Tips:
- Use "that", "this", "it" to reference previous items
- Ask "why" to understand errors
- Request "examples" to see sample data
- Say "explain" for detailed information

---

## Troubleshooting

### "I can't connect to Salesforce"
- Check MCP server configuration
- Verify credentials
- Ask: "Can you access my Salesforce org?"

### "The query returned no results"
- Verify your filters
- Ask: "Show me all records" first
- Check if data exists: "How many X records exist?"

### "I got an error creating a record"
- Ask: "What went wrong?"
- Request: "Show me required fields"
- Validate: "Check this data before creating"

### "I'm not sure what to do next"
- Just ask: "What can I do with this?"
- Request: "Suggest next steps"
- Explore: "What else can I see?"

---

## Advanced Tips

### 1. Complex Queries
```
You: "Show me accounts with more than 5 opportunities, 
      where at least one opportunity is over $100k"

AI: [Constructs complex SOQL with subqueries automatically]
```

### 2. Relationship Navigation
```
You: "Show me this account's contacts and their opportunities"

AI: [Navigates relationships automatically]
```

### 3. Data Validation
```
You: "Before I import 1000 records, validate one record first"

AI: [Checks all requirements, suggests corrections]
```

### 4. Learning Patterns
```
You: "Show me 5 example opportunities so I understand the pattern"

AI: [Shows diverse examples with explanations]
```

---

## Quick Command Reference

| What You Want | What to Say |
|---------------|-------------|
| **See all records** | "Show me all [Object]" |
| **Filter records** | "Find [Object] where [condition]" |
| **Create record** | "Create a [Object] named [Name]" |
| **Update record** | "Update [ID] to [new value]" |
| **Delete record** | "Delete [ID]" (requires confirmation) |
| **Learn object** | "What fields does [Object] have?" |
| **Get requirements** | "What's required to create [Object]?" |
| **See options** | "What are valid values for [Field]?" |
| **Get help** | "How do I [task]?" |
| **Explain error** | "Why did that fail?" |

---

## Remember

- **MCP is conversational** - talk naturally!
- **MCP is intelligent** - it understands context
- **MCP is safe** - confirms before destructive actions
- **MCP is helpful** - explains and guides you
- **MCP is limited** - use CLI for deployment and bulk operations

---

## Additional Resources

- **Main Guide**: See "Salesforce-CLI-vs-MCP-Guide.md"
- **CLI Reference**: See "CLI-Quick-Reference.md"
- **Model Context Protocol**: https://modelcontextprotocol.io/

---

**Last Updated**: June 11, 2026

**Pro Tip**: The best way to learn MCP is to use it! Start with simple queries and build up to complex operations. Don't be afraid to ask questions - that's what it's designed for!
