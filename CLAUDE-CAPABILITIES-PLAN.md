# Claude Code General-Purpose Agent Setup
## Comprehensive Capability Plan

This document outlines the complete setup for transforming Claude Code into a general-purpose agent for productivity, research, and analysis.

---

## 🏗️ Architecture Overview

```
Four-Layer Capability System:
├── MCP Servers (Live External Data)
├── Skills (Auto-Activating Expertise)
├── Slash Commands (Manual Workflows)
└── Memory (Persistent Context)
```

---

## 📋 20+ Capabilities to Implement

### Layer 1: MCP Servers (External Integrations)

| # | Capability | MCP Server | Purpose |
|---|------------|------------|---------|
| 1 | **Gmail Integration** | gmail-mcp / composio | Read, search, draft, send emails |
| 2 | **Google Calendar** | google-calendar-mcp | Manage events, check availability, schedule |
| 3 | **Slack Integration** | slack-mcp | Read channels, send messages, search history |
| 4 | **Notion Workspace** | notion-mcp | Query databases, create/update pages |
| 5 | **Web Search** | brave-search-mcp / perplexity | Real-time internet searches |
| 6 | **File System Access** | filesystem-mcp | Read/write local files beyond workspace |

**Total MCP Servers: 6**

---

### Layer 2: Skills (Auto-Activating)

| # | Capability | Skill Name | Triggers When |
|---|------------|------------|---------------|
| 7 | **Internet Research** ✅ | internet-search.md | Any search/research request |
| 8 | **Email Analysis** | email-analyzer.md | Working with email content |
| 9 | **Meeting Scheduler** | meeting-scheduler.md | Scheduling discussions detected |
| 10 | **Document Summarizer** | document-summarizer.md | Long documents to summarize |
| 11 | **Data Analyzer** | data-analyzer.md | Analyzing datasets/metrics |
| 12 | **Code Reviewer** | code-reviewer.md | Code review requests |
| 13 | **Project Planner** | project-planner.md | Planning new initiatives |

**Total Skills: 7 (1 existing + 6 new)**

---

### Layer 3: Slash Commands (Manual Workflows)

| # | Capability | Command | Use Case |
|---|------------|---------|----------|
| 14 | **Daily Briefing** | /daily-briefing | Morning summary: emails, calendar, tasks |
| 15 | **Email Digest** | /email-digest | Summarize recent important emails |
| 16 | **Schedule Analysis** | /calendar-review | Review upcoming week/conflicts |
| 17 | **Slack Catchup** | /slack-catchup | Summarize missed Slack messages |
| 18 | **Research Deep Dive** | /deep-research | Multi-source research project |
| 19 | **Meeting Prep** | /meeting-prep | Prepare for specific meeting |
| 20 | **Weekly Review** | /weekly-review | Complete week summary & planning |
| 21 | **Task Prioritizer** | /prioritize-tasks | Analyze and prioritize todos |
| 22 | **Competitive Intel** | /competitive-analysis | Research competitors |
| 23 | **Content Creator** | /create-content | Draft blog/social posts |

**Total Slash Commands: 10**

---

### Layer 4: Memory Files (Persistent Context)

| # | Capability | File | Content |
|---|------------|------|---------|
| 24 | **Personal Preferences** | CLAUDE.md | Your work style, preferences, context |
| 25 | **Tool Credentials** | .env | API keys (gitignored) |
| 26 | **Standard Operating Procedures** | .claude/memory/sops.md | How you like things done |

**Total Memory Files: 3**

---

## 🎯 Total Capability Count: 26

- **MCP Servers**: 6
- **Skills**: 7 (1 existing)
- **Slash Commands**: 10
- **Memory Files**: 3

---

## 📊 Priority Implementation Order

### Phase 1: Core Foundation (Week 1)
1. Set up directory structure
2. Configure Gmail MCP
3. Configure Google Calendar MCP
4. Create CLAUDE.md memory file
5. Create 2-3 most useful commands

### Phase 2: Communication Layer (Week 2)
1. Add Slack MCP
2. Add Notion MCP
3. Create email/meeting skills
4. Add /daily-briefing command

### Phase 3: Intelligence Layer (Week 3)
1. Add remaining skills
2. Add research/analysis commands
3. Configure web search MCPs
4. Test and refine workflows

### Phase 4: Optimization (Week 4)
1. Add remaining commands
2. Tune memory files
3. Document usage patterns
4. Create maintenance procedures

---

## 🔄 Update & Maintenance Process

### Monthly Review Checklist
- [ ] Review command usage (which are used/unused?)
- [ ] Update API keys if expired
- [ ] Test MCP server connections
- [ ] Refine skill triggers based on experience
- [ ] Archive unused capabilities

### Adding New Capabilities
```bash
# For MCP Servers
claude mcp add --transport http <name> <url>

# For Skills
# Create .claude/skills/new-skill.md

# For Commands
# Create .claude/commands/new-command.md

# For Memory
# Edit CLAUDE.md or create .claude/memory/*.md
```

### Removing Capabilities
```bash
# MCP Servers
claude mcp remove <name>

# Skills/Commands
# Delete the .md file

# Memory
# Remove section from CLAUDE.md
```

### Version Control
```bash
# Track all configurations in git
git add .claude/
git commit -m "Update: <what changed and why>"
```

---

## 🛠️ Next Steps

1. **Review this plan** - Adjust priorities based on your needs
2. **Start with Phase 1** - Foundation first
3. **Iterate** - Add capabilities as you need them
4. **Document** - Keep notes on what works
5. **Share** - Contribute useful patterns back to community

---

## 📚 Resources

- [Claude Code MCP Docs](https://docs.anthropic.com/en/docs/claude-code/mcp)
- [MCP Server Directory](https://github.com/modelcontextprotocol/servers)
- [Composio MCP Platform](https://mcp.composio.dev/)
- [Community Commands Repo](https://github.com/wshobson/commands)
- [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code)

---

**Last Updated**: 2025-11-14
**Version**: 1.0
