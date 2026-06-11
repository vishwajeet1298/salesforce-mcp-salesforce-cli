# Salesforce Tools Documentation

**Complete guide to Salesforce CLI and Salesforce MCP for your team**

---

## 📚 Documentation Overview

This repository contains comprehensive documentation for working with Salesforce using two powerful tools:

1. **Salesforce CLI** - Command-line interface for automation and deployment
2. **Salesforce MCP** - AI-powered natural language interface for interactive work

---

## 📖 Available Documents

### 1. [Salesforce CLI vs MCP Guide](./Salesforce-CLI-vs-MCP-Guide.md)
**Complete comprehensive guide covering everything**

**Contents**:
- What is Salesforce CLI?
- What is Salesforce MCP?
- Detailed advantages, disadvantages, and limitations
- Side-by-side comparison
- When to use each tool
- Real-world scenarios
- Best practices
- Getting started guides
- FAQ

**Who should read**: Everyone - this is the master document

**Time to read**: 30-45 minutes

---

### 2. [CLI Quick Reference](./CLI-Quick-Reference.md)
**Fast lookup guide for Salesforce CLI commands**

**Contents**:
- Authentication commands
- Data operations (query, create, update, delete)
- Metadata deployment and retrieval
- Apex operations and testing
- Package management
- Common workflows
- Troubleshooting tips

**Who should read**: Developers, DevOps engineers, admins using CLI

**Time to read**: 10-15 minutes (reference document)

---

### 3. [MCP Quick Reference](./MCP-Quick-Reference.md)
**Guide for using Salesforce MCP with AI Assistant**

**Contents**:
- Available operations
- Natural language examples
- Sample conversations
- Tips for effective use
- Common patterns
- What MCP can and cannot do
- Best practices

**Who should read**: Everyone, especially those new to Salesforce

**Time to read**: 10-15 minutes (reference document)

---

## 🚀 Quick Start

### For New Team Members

1. **Start here**: Read [Salesforce CLI vs MCP Guide](./Salesforce-CLI-vs-MCP-Guide.md) - Executive Summary
2. **Learn MCP first**: Read [MCP Quick Reference](./MCP-Quick-Reference.md)
3. **Try MCP**: Practice with AI assistant in your IDE
4. **Learn CLI**: Read [CLI Quick Reference](./CLI-Quick-Reference.md)
5. **Install CLI**: Follow installation guide in main document

**Recommended learning path**: MCP → CLI → Combined workflows

---

### For Developers

1. **Install Salesforce CLI**:
   ```bash
   npm install -g @salesforce/cli
   sf --version
   ```

2. **Authenticate**:
   ```bash
   sf org login web --alias myorg
   ```

3. **Bookmark**: [CLI Quick Reference](./CLI-Quick-Reference.md)

4. **Use MCP for**: Data exploration and learning

5. **Use CLI for**: Deployment, automation, bulk operations

---

### For Administrators

1. **Start with MCP**: Learn Salesforce structure naturally

2. **Practice queries**: Use MCP to explore data

3. **Learn CLI basics**: Focus on data operations from [CLI Quick Reference](./CLI-Quick-Reference.md)

4. **Combine both**: Use MCP for exploration, CLI for bulk operations

---

### For Business Analysts

1. **Use MCP primarily**: Natural language interface is perfect for you

2. **Read**: [MCP Quick Reference](./MCP-Quick-Reference.md)

3. **Practice**: Ask questions, explore data, learn by doing

4. **CLI optional**: Only if you need bulk data operations

---

## 🎯 Use Case Guide

### "I need to deploy code to production"
→ Use **Salesforce CLI**  
→ See: [CLI Quick Reference - Deployment](./CLI-Quick-Reference.md#deployment)

---

### "I want to learn about Salesforce objects"
→ Use **Salesforce MCP**  
→ See: [MCP Quick Reference - Describe Objects](./MCP-Quick-Reference.md#6-describe-objects)

---

### "I need to update 50 records"
→ Use **Salesforce MCP** (interactive, safe)  
→ See: [MCP Quick Reference - Update Records](./MCP-Quick-Reference.md#4-update-records)

---

### "I need to import 10,000 records"
→ Use **Salesforce CLI** (bulk operations)  
→ See: [CLI Quick Reference - Bulk Operations](./CLI-Quick-Reference.md#bulk-operations)

---

### "I want to set up CI/CD"
→ Use **Salesforce CLI**  
→ See: [Main Guide - CI/CD Integration](./Salesforce-CLI-vs-MCP-Guide.md#scenario-4-cicd-pipeline-setup)

---

### "I need to troubleshoot a data issue"
→ Use **Salesforce MCP** (interactive investigation)  
→ See: [Main Guide - Troubleshooting](./Salesforce-CLI-vs-MCP-Guide.md#scenario-5-troubleshooting-production-issue)

---

## 📊 Tool Comparison at a Glance

| Task | Best Tool | Why |
|------|-----------|-----|
| **Deploy Apex code** | CLI | Only CLI can deploy metadata |
| **Query 10 records** | Either | Both work well |
| **Query 10,000 records** | CLI | Better for bulk |
| **Learn object structure** | MCP | Natural language, automatic |
| **Create test data** | MCP | Interactive, guided |
| **Import CSV (1000+ rows)** | CLI | Bulk API support |
| **CI/CD pipeline** | CLI | Scriptable, automatable |
| **Explore relationships** | MCP | Intelligent navigation |
| **Scratch org management** | CLI | Only CLI supports this |
| **Ad-hoc data fixes** | MCP | Safe, interactive |

---

## 🛠️ Installation & Setup

### Salesforce CLI

**Prerequisites**:
- Node.js 18 or later
- Git (optional, for version control)

**Installation**:
```bash
# Install
npm install -g @salesforce/cli

# Verify
sf --version

# Authenticate
sf org login web --alias myorg
```

**Full guide**: See [Main Guide - Getting Started](./Salesforce-CLI-vs-MCP-Guide.md#setting-up-salesforce-cli)

---

### Salesforce MCP

**Prerequisites**:
- IDE with MCP support (Windsurf, Cursor, etc.)
- Salesforce org credentials configured

**Setup**:
1. Verify MCP is configured in your IDE
2. Ask AI: "Can you connect to my Salesforce org?"
3. Start using natural language!

**Full guide**: See [Main Guide - Getting Started](./Salesforce-CLI-vs-MCP-Guide.md#setting-up-salesforce-mcp)

---

## 💡 Best Practices

### 1. Use Both Tools Together
- **Learn** with MCP
- **Automate** with CLI
- **Verify** with MCP

### 2. Start with MCP
- Lower learning curve
- Understand Salesforce first
- Graduate to CLI for automation

### 3. Document Your Work
- Save successful CLI commands
- Note helpful MCP queries
- Build team knowledge base

### 4. Follow Security Best Practices
- Never commit credentials
- Use JWT for CI/CD
- Rotate tokens regularly
- Use least privilege

### 5. Test Before Production
- Validate deployments
- Test in sandbox first
- Use scratch orgs for development

**Full best practices**: See [Main Guide - Best Practices](./Salesforce-CLI-vs-MCP-Guide.md#best-practices)

---

## 🎓 Learning Path

### Week 1: Foundations
- [ ] Read Executive Summary in main guide
- [ ] Try MCP: Query some records
- [ ] Install Salesforce CLI
- [ ] Authenticate to your org with CLI

### Week 2: MCP Mastery
- [ ] Practice MCP queries daily
- [ ] Learn object structures with MCP
- [ ] Create and update test records
- [ ] Explore relationships

### Week 3: CLI Basics
- [ ] Learn basic CLI commands
- [ ] Practice data queries
- [ ] Try creating records
- [ ] Explore metadata operations

### Week 4: Advanced Usage
- [ ] Combine MCP and CLI in workflows
- [ ] Try bulk operations with CLI
- [ ] Practice deployment with CLI
- [ ] Build your first automation script

### Ongoing
- [ ] Bookmark quick reference guides
- [ ] Share learnings with team
- [ ] Build team knowledge base
- [ ] Contribute to documentation

---

## 🤝 Team Collaboration

### Share Knowledge
- Document successful workflows
- Share useful CLI commands
- Note helpful MCP queries
- Build team FAQ

### Code Review
- Review CLI scripts together
- Share deployment strategies
- Discuss best practices
- Learn from each other

### Pair Programming
- Junior + Senior: Learn together
- MCP + CLI: Combine strengths
- Explore + Automate: Full workflow

---

## 📞 Support & Resources

### Internal Resources
- This documentation repository
- Team Slack channel (if applicable)
- Internal wiki (if applicable)

### External Resources
- **Salesforce CLI Docs**: https://developer.salesforce.com/docs/atlas.en-us.sfdx_cli_reference.meta/sfdx_cli_reference/
- **Trailhead**: https://trailhead.salesforce.com/
- **Developer Forums**: https://developer.salesforce.com/forums
- **Stack Overflow**: Tag `salesforce` or `salesforce-cli`

### Getting Help
1. Check this documentation first
2. Ask AI assistant (for MCP questions)
3. Search official documentation
4. Ask team members
5. Post in community forums

---

## 🔄 Document Updates

### Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | June 11, 2026 | Initial documentation created |

### Contributing
To update this documentation:
1. Make your changes
2. Update version history
3. Commit to version control
4. Share with team

---

## 📋 Cheat Sheet

### Most Common CLI Commands
```bash
# Query data
sf data query --query "SELECT Id, Name FROM Account"

# Deploy code
sf project deploy start --source-dir force-app

# Run tests
sf apex run test --test-level RunLocalTests

# Create scratch org
sf org create scratch --definition-file config/project-scratch-def.json
```

### Most Common MCP Queries
- "Show me all accounts"
- "What fields does Opportunity have?"
- "Create a test opportunity"
- "What's required to create a Contact?"

---

## 🎯 Quick Decision Matrix

**Choose Salesforce CLI when you need**:
- ✅ Metadata deployment
- ✅ Bulk operations (1000+ records)
- ✅ CI/CD integration
- ✅ Scratch org management
- ✅ Automation and scripting

**Choose Salesforce MCP when you need**:
- ✅ To learn Salesforce
- ✅ Interactive data exploration
- ✅ Small data changes (<100 records)
- ✅ Field and object discovery
- ✅ Natural language interface

**Use both when**:
- ✅ Developing new features
- ✅ Troubleshooting issues
- ✅ Learning then automating
- ✅ Exploring then deploying

---

## 📝 Next Steps

1. **Read the main guide**: [Salesforce CLI vs MCP Guide](./Salesforce-CLI-vs-MCP-Guide.md)
2. **Try MCP**: Start with simple queries
3. **Install CLI**: Follow setup guide
4. **Practice daily**: Build muscle memory
5. **Share learnings**: Help your team

---

## 📧 Feedback

Have suggestions for improving this documentation?
- Update the documents directly
- Share with the team
- Keep documentation current

---

**Remember**: The best tool is the one that helps you get your work done efficiently. Don't be afraid to switch between CLI and MCP as needed!

---

**Last Updated**: June 11, 2026  
**Maintained by**: Development Team
