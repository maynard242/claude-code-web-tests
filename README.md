# Claude Code General-Purpose Agent

Transform Claude Code into a powerful general-purpose AI agent for productivity, research, communication, and analysis.

## 🎯 Overview

This repository provides a comprehensive setup for Claude Code with:
- **26+ capabilities** spanning communication, research, planning, and analysis
- **MCP server integrations** for Gmail, Calendar, Slack, Notion, and more
- **Auto-activating skills** that provide contextual expertise
- **Slash commands** for on-demand workflows
- **Persistent memory** for consistent behavior

## ✨ What's Included

### 🧠 Skills (Auto-Activating Expertise)
- **Internet Search** - Multi-source web research
- **Email Analyzer** - Intelligent email triage and response drafting
- **Meeting Scheduler** - Smart calendar management
- **Document Summarizer** - Extract insights from long documents
- **Data Analyzer** - Metrics, trends, and statistical analysis

### ⚡ Slash Commands (Manual Workflows)
- `/daily-briefing` - Morning overview of calendar, emails, and priorities
- `/deep-research [topic]` - Comprehensive multi-source research
- `/weekly-review` - End-of-week reflection and planning
- `/meeting-prep [meeting]` - Prepare thoroughly for important meetings

### 🔌 MCP Integration Support
- Gmail (read, search, send emails)
- Google Calendar (manage events, check availability)
- Slack (team communication)
- Notion (knowledge management)
- File system access
- Web search APIs

### 📚 Memory & Context
- **CLAUDE.md** - Persistent preferences and project context
- Custom memory files for team standards and procedures

## 🚀 Quick Start

### 1. Clone and Setup

```bash
git clone https://github.com/yourusername/claude-code-web-tests.git
cd claude-code-web-tests
```

### 2. Configure API Keys (Optional)

Copy the example environment file:
```bash
cp .env.example .env
```

Add your API keys for external search services (optional - built-in tools work without them):
```env
FIRECRAWL_API_KEY=your-key
BRAVE_API_KEY=your-key
SERPER_API_KEY=your-key
```

### 3. Set Up MCP Servers (Recommended)

For full capabilities, configure MCP servers for external integrations:

```bash
# See detailed setup guide
cat MCP-SETUP-GUIDE.md
```

**Quick MCP setup:**
```bash
# Google Calendar
claude mcp add google-calendar --transport http <url>

# Gmail
claude mcp add gmail --transport http <url>

# Slack
claude mcp add slack --transport http <url>
```

See **[MCP-SETUP-GUIDE.md](MCP-SETUP-GUIDE.md)** for complete instructions.

### 4. Start Using

Open Claude Code in this directory and try:

```
# Use a skill (auto-activates)
"Analyze my inbox and prioritize emails"
"What's on my calendar tomorrow?"
"Summarize this research paper"

# Use a slash command
/daily-briefing
/deep-research AI coding assistants
/weekly-review
/meeting-prep tomorrow 10am
```

## 📋 Capabilities Overview

### Communication & Productivity

| Capability | Type | MCP Required | Description |
|------------|------|--------------|-------------|
| Email Analysis | Skill | Gmail | Categorize, prioritize, draft responses |
| Calendar Management | Skill | Google Calendar | Schedule meetings, find availability |
| Daily Briefing | Command | Gmail + Calendar | Morning overview of day ahead |
| Meeting Prep | Command | Calendar | Prepare for important meetings |
| Weekly Review | Command | Gmail + Calendar | End-of-week reflection |

### Research & Analysis

| Capability | Type | MCP Required | Description |
|------------|------|--------------|-------------|
| Internet Search | Skill | None* | Multi-source web research |
| Deep Research | Command | None* | Comprehensive topic investigation |
| Document Summarizer | Skill | None | Extract insights from long docs |
| Data Analyzer | Skill | None | Statistical analysis and trends |

*Built-in tools work; MCP enhances capabilities

### Collaboration

| Capability | Type | MCP Required | Description |
|------------|------|--------------|-------------|
| Slack Integration | Skill | Slack MCP | Team communication analysis |
| Notion Integration | Skill | Notion MCP | Knowledge base management |

## 📖 Documentation

### Getting Started
- **[CLAUDE-CAPABILITIES-PLAN.md](CLAUDE-CAPABILITIES-PLAN.md)** - Complete 26-capability roadmap
- **[MCP-SETUP-GUIDE.md](MCP-SETUP-GUIDE.md)** - Step-by-step MCP configuration
- **[CLAUDE.md](CLAUDE.md)** - Your agent's persistent memory and preferences

### Skills Documentation
- [Internet Search](.claude/skills/internet-search.md) - Multi-source web research
- [Email Analyzer](.claude/skills/email-analyzer.md) - Intelligent email management
- [Meeting Scheduler](.claude/skills/meeting-scheduler.md) - Smart scheduling
- [Document Summarizer](.claude/skills/document-summarizer.md) - Document analysis
- [Data Analyzer](.claude/skills/data-analyzer.md) - Metrics and trends

### Commands Documentation
- [Daily Briefing](.claude/commands/daily-briefing.md) - Morning routine
- [Deep Research](.claude/commands/deep-research.md) - Comprehensive research
- [Weekly Review](.claude/commands/weekly-review.md) - Weekly reflection
- [Meeting Prep](.claude/commands/meeting-prep.md) - Meeting preparation

## 🏗️ Project Structure

```
claude-code-web-tests/
├── .claude/
│   ├── skills/               # Auto-activating capabilities
│   │   ├── internet-search.md
│   │   ├── email-analyzer.md
│   │   ├── meeting-scheduler.md
│   │   ├── document-summarizer.md
│   │   └── data-analyzer.md
│   ├── commands/             # Manual workflows
│   │   ├── daily-briefing.md
│   │   ├── deep-research.md
│   │   ├── weekly-review.md
│   │   └── meeting-prep.md
│   └── memory/               # Additional context files
│
├── examples/                 # Usage examples
│   └── search-examples.md
│
├── CLAUDE.md                 # Persistent memory (loaded every session)
├── CLAUDE-CAPABILITIES-PLAN.md  # Complete roadmap
├── MCP-SETUP-GUIDE.md        # MCP integration guide
├── .env.example              # API keys template
├── .gitignore
└── README.md                 # This file
```

## 🔧 Configuration

### Skills vs Commands vs Memory

**Skills** (.claude/skills/):
- Auto-activate when relevant to conversation
- Provide contextual expertise
- ~5k tokens when active
- Example: Email analyzer activates when discussing emails

**Slash Commands** (.claude/commands/):
- Manually triggered with `/command-name`
- Explicit workflows you control
- On-demand execution
- Example: `/daily-briefing` for morning routine

**Memory** (CLAUDE.md, .claude/memory/):
- Always loaded in every session
- Persistent preferences and context
- Project guidelines and standards
- Example: Your communication style, work hours

See **[CLAUDE-CAPABILITIES-PLAN.md](CLAUDE-CAPABILITIES-PLAN.md)** for detailed architecture.

## 🎯 Use Cases

### Morning Routine
```
/daily-briefing

→ Calendar overview for the day
→ Priority emails requiring response
→ Suggested task prioritization
→ Quick wins to complete
```

### Email Management
```
"Analyze my inbox from the last 24 hours"

→ Categorized by priority
→ Action items extracted
→ Draft responses for key emails
→ Recommendations on what to defer
```

### Research Projects
```
/deep-research Comparison of Next.js vs Remix

→ Multi-source research (15+ sources)
→ Technical comparison table
→ Pros/cons analysis
→ Expert recommendations
→ Complete citations
```

### Weekly Planning
```
/weekly-review

→ Calendar analysis (meetings vs focus time)
→ Email activity summary
→ Accomplishments and challenges
→ Pattern analysis
→ Next week priorities
```

### Meeting Preparation
```
/meeting-prep Q4 Planning Review

→ Meeting context and background
→ Your role and objectives
→ Questions to ask
→ Potential challenges
→ Materials checklist
```

## 🔐 Security & Privacy

### API Key Management
- Store keys in `.env` (gitignored)
- Use environment variables
- Never commit credentials
- Rotate keys regularly

### MCP Permissions
- Minimal required scopes only
- Review permissions before granting
- Audit access regularly
- Use OAuth when available

### Data Privacy
- Skills analyze locally when possible
- MCP data fetched only when needed
- No logging of sensitive information
- Clear data handling policies

## 🌟 Features by Integration Level

### Level 1: No MCP (Works Immediately)
- Internet search (built-in WebSearch)
- Document summarization
- Data analysis (on provided data)
- Deep research command
- Code assistance

### Level 2: + Search APIs (Optional)
- Enhanced web research
- Privacy-focused searching
- Web content extraction
- Multi-source verification

### Level 3: + Core MCPs (Recommended)
**With Gmail + Google Calendar:**
- Daily briefing with real data
- Email analysis and drafting
- Meeting scheduling
- Calendar optimization
- Weekly reviews with metrics

### Level 4: + Full Suite (Maximum Power)
**With Gmail + Calendar + Slack + Notion:**
- Complete productivity automation
- Cross-platform insights
- Unified knowledge management
- Team collaboration analysis
- Comprehensive planning

## 📈 Roadmap

See **[CLAUDE-CAPABILITIES-PLAN.md](CLAUDE-CAPABILITIES-PLAN.md)** for:
- Complete 26-capability plan
- Phase-by-phase implementation guide
- Priority recommendations
- Update and maintenance process

## 🤝 Customization

### Adding New Skills

Create `.claude/skills/your-skill.md`:
```markdown
# Your Skill Name

## Purpose
What this skill does and when it activates

## Activation Context
Conditions that trigger this skill

## Capabilities
What the skill can do

[Implementation details...]
```

### Adding New Commands

Create `.claude/commands/your-command.md`:
```markdown
# Your Command

When user runs `/your-command`, do:

1. Step 1
2. Step 2
3. Step 3

[Detailed instructions...]
```

### Customizing Memory

Edit `CLAUDE.md` to add:
- Your work preferences
- Communication style
- Team standards
- Project context
- Recurring instructions

## 🛠️ Troubleshooting

### Skills Not Activating
- Check file is in `.claude/skills/`
- Verify markdown formatting
- Make description clear for when to activate
- Try explicitly mentioning the skill's domain

### Commands Not Available
- Ensure file is in `.claude/commands/`
- Check filename matches command name
- Restart Claude Code
- Verify no syntax errors in markdown

### MCP Issues
- Run `claude mcp list` to verify servers
- Check API keys in environment variables
- Review [MCP-SETUP-GUIDE.md](MCP-SETUP-GUIDE.md)
- Test with `/mcp` command

## 📚 Resources

### Official Documentation
- [Claude Code Docs](https://docs.claude.com/en/docs/claude-code)
- [Skills Documentation](https://docs.claude.com/en/docs/claude-code/skills)
- [Slash Commands](https://docs.claude.com/en/docs/claude-code/slash-commands)
- [MCP Documentation](https://docs.anthropic.com/en/docs/claude-code/mcp)

### Community Resources
- [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code)
- [Awesome Claude Skills](https://github.com/ComposioHQ/awesome-claude-skills)
- [Production Commands](https://github.com/wshobson/commands)
- [Claude Code Guide](https://github.com/Cranot/claude-code-guide)

### MCP Resources
- [PulseMCP Directory](https://www.pulsemcp.com)
- [MCP Servers Repo](https://github.com/modelcontextprotocol/servers)
- [Composio MCP Platform](https://mcp.composio.dev)

## 🙏 Acknowledgments

Built on best practices from:
- Anthropic's Claude Code team
- Claude Code community contributors
- Model Context Protocol developers
- Open source MCP server maintainers

## 📄 License

This project is open source and available for use and modification.

## 🆘 Support

1. Check relevant documentation file
2. Review troubleshooting section
3. Verify MCP server status
4. Test with minimal configuration
5. Check community resources

## ✨ Tips for Success

1. **Start Simple** - Use built-in capabilities first, add MCPs gradually
2. **Customize Memory** - Update CLAUDE.md with your preferences
3. **Test Incrementally** - Verify each capability works before adding more
4. **Review Weekly** - Use `/weekly-review` to refine your setup
5. **Share Learnings** - Contribute improvements back to community

---

**Transform Claude Code into your personal AI assistant.** 🚀

For questions or improvements, see the documentation in `.claude/` directories or consult the guides listed above.
