# MCP Server Setup Guide
Complete guide to configuring Model Context Protocol servers for your Claude Code general-purpose agent.

---

## 🎯 What are MCP Servers?

MCP (Model Context Protocol) servers are external integrations that give Claude real-time access to:
- Live data (Gmail, Calendar, Slack, Notion)
- External tools (search APIs, databases)
- File systems and services

Think of them as plugins that extend Claude's capabilities beyond the local workspace.

---

## 📋 Recommended MCP Servers for General-Purpose Agent

### Essential (Start Here)

| MCP Server | Purpose | Priority | Difficulty |
|------------|---------|----------|------------|
| **Google Calendar** | Manage events, check availability | HIGH | Easy |
| **Gmail** | Read/search/send emails | HIGH | Easy |
| **Slack** | Team communication | HIGH | Medium |
| **Filesystem** | Access files outside workspace | MEDIUM | Easy |

### Productivity Enhancers

| MCP Server | Purpose | Priority | Difficulty |
|------------|---------|----------|------------|
| **Notion** | Knowledge management | MEDIUM | Medium |
| **Brave Search** | Real-time web search | MEDIUM | Easy |
| **Perplexity** | AI-powered research | LOW | Easy |

### Advanced

| MCP Server | Purpose | Priority | Difficulty |
|------------|---------|----------|------------|
| **Composio** | 300+ app integrations | LOW | Hard |
| **Zapier** | 8000+ workflow automations | LOW | Hard |

---

## 🚀 Quick Start: Essential Setup

### Method 1: Using Claude CLI (Recommended)

```bash
# Check current MCP servers
claude mcp list

# Add Google Calendar MCP
claude mcp add --transport http google-calendar https://your-calendar-mcp-url

# Add Gmail MCP
claude mcp add --transport http gmail https://your-gmail-mcp-url

# Add Slack MCP
claude mcp add --transport http slack https://your-slack-mcp-url

# Verify installation
claude mcp list
```

### Method 2: Manual Configuration

Edit `~/.claude.json`:

```json
{
  "mcpServers": {
    "google-calendar": {
      "command": "node",
      "args": ["/path/to/google-calendar-mcp/server.js"],
      "env": {
        "GOOGLE_CALENDAR_API_KEY": "your-api-key"
      }
    },
    "gmail": {
      "command": "npx",
      "args": ["-y", "@gmail/mcp-server"],
      "env": {
        "GMAIL_API_KEY": "your-api-key"
      }
    },
    "slack": {
      "transport": "http",
      "url": "https://slack-mcp.example.com",
      "headers": {
        "Authorization": "Bearer your-slack-token"
      }
    }
  }
}
```

---

## 📝 Detailed Setup Instructions

### 1. Google Calendar MCP

**Installation**:
```bash
# Using existing MCP server
git clone https://github.com/nspady/google-calendar-mcp
cd google-calendar-mcp
npm install
npm run build

# Add to Claude
claude mcp add google-calendar \
  --command "node" \
  --args "/path/to/google-calendar-mcp/build/index.js"
```

**Configuration**:
1. Get Google Calendar API credentials:
   - Go to [Google Cloud Console](https://console.cloud.google.com)
   - Create new project or select existing
   - Enable Google Calendar API
   - Create OAuth 2.0 credentials
   - Download credentials JSON

2. Set environment variables:
```bash
export GOOGLE_CALENDAR_CREDENTIALS_PATH=/path/to/credentials.json
```

3. Test:
```bash
# In Claude Code
# Try: "Show me my calendar for tomorrow"
```

**Alternative: Composio (Easier)**:
```bash
# Install Composio CLI
npm install -g composio-core

# Authenticate with Google
composio auth google

# Add to Claude via Composio
claude mcp add composio --transport http https://mcp.composio.dev
```

---

### 2. Gmail MCP

**Option A: Direct Gmail MCP**

```bash
# Install Gmail MCP package
npm install -g @gmail/mcp-server

# Add to Claude
claude mcp add gmail \
  --command "npx" \
  --args "-y @gmail/mcp-server"
```

**Configuration**:
1. Enable Gmail API in Google Cloud Console (same as Calendar)
2. Create OAuth credentials
3. Set environment:
```bash
export GMAIL_CREDENTIALS_PATH=/path/to/gmail-credentials.json
export GMAIL_SCOPES="https://www.googleapis.com/auth/gmail.modify"
```

**Option B: Composio (Recommended for easier setup)**:
```bash
composio auth gmail
# Then use Composio MCP (already configured above)
```

---

### 3. Slack MCP

**Installation**:

Visit [PulseMCP Slack Servers](https://www.pulsemcp.com/servers?q=slack) to find available options.

**Recommended: Slack Official MCP**

```bash
# Install Slack MCP
npm install -g @slack/mcp-server

# Add to Claude
claude mcp add slack \
  --command "npx" \
  --args "-y @slack/mcp-server"
```

**Configuration**:
1. Create Slack App:
   - Go to [api.slack.com/apps](https://api.slack.com/apps)
   - Create New App → From scratch
   - Name it "Claude Code Integration"

2. Set Permissions (OAuth & Permissions):
   ```
   channels:history
   channels:read
   chat:write
   users:read
   ```

3. Install to Workspace and get OAuth token

4. Set environment:
```bash
export SLACK_BOT_TOKEN=xoxb-your-token-here
export SLACK_WORKSPACE_ID=your-workspace-id
```

**Test**:
```bash
# In Claude Code
# Try: "Show me unread Slack messages"
```

---

### 4. Notion MCP

**Installation**:

Visit [PulseMCP Notion Servers](https://www.pulsemcp.com/servers?q=notion)

**Recommended Setup**:

```bash
# Install Notion MCP
npm install -g @notionhq/mcp-server

# Add to Claude
claude mcp add notion \
  --command "npx" \
  --args "-y @notionhq/mcp-server"
```

**Configuration**:
1. Create Notion Integration:
   - Go to [notion.so/my-integrations](https://www.notion.so/my-integrations)
   - Create New Integration
   - Name: "Claude Code"
   - Capabilities: Read content, Update content, Insert content

2. Share pages/databases with integration:
   - Open Notion page → Share → Invite "Claude Code" integration

3. Get Integration Token and set:
```bash
export NOTION_API_KEY=secret_your_integration_token
```

---

### 5. Filesystem MCP (Local Files)

**Installation**:
```bash
# Usually comes with Claude Code
# Verify with:
claude mcp list
```

**Configuration**:
```json
{
  "filesystem": {
    "command": "npx",
    "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/allowed/directory"],
    "allowedPaths": [
      "/Users/you/Documents",
      "/Users/you/Downloads"
    ]
  }
}
```

**Security Note**: Only grant access to necessary directories!

---

### 6. Web Search MCPs

**Option A: Brave Search**

```bash
# Get API key from https://brave.com/search/api/
export BRAVE_API_KEY=your-key

# Add MCP
claude mcp add brave-search \
  --transport http \
  --url https://api.search.brave.com/mcp
```

**Option B: Perplexity**

```bash
# Get API key from https://www.perplexity.ai/settings/api
export PERPLEXITY_API_KEY=your-key

# Add MCP
claude mcp add perplexity \
  --transport http \
  --url https://api.perplexity.ai/mcp
```

**Note**: You already have internet-search skill that uses WebSearch built-in tool. These MCPs are optional for additional search capabilities.

---

## 🔐 Security Best Practices

### API Key Management

**DO**:
- Store keys in environment variables
- Use `.env` file (gitignored)
- Rotate keys regularly
- Use minimal required permissions

**DON'T**:
- Hardcode keys in config files
- Commit keys to git
- Share keys publicly
- Use overly permissive scopes

### Example `.env` file:
```bash
# Google Services
GOOGLE_CALENDAR_CREDENTIALS_PATH=/secure/path/calendar-creds.json
GMAIL_CREDENTIALS_PATH=/secure/path/gmail-creds.json

# Slack
SLACK_BOT_TOKEN=xoxb-your-token
SLACK_WORKSPACE_ID=T01234567

# Notion
NOTION_API_KEY=secret_your_integration_token

# Search APIs
BRAVE_API_KEY=your-brave-key
PERPLEXITY_API_KEY=your-perplexity-key

# Composio (if using)
COMPOSIO_API_KEY=your-composio-key
```

### Loading Environment Variables

Add to your shell profile (`~/.zshrc` or `~/.bashrc`):
```bash
# Load Claude Code MCP credentials
if [ -f ~/.claude-mcp.env ]; then
    export $(cat ~/.claude-mcp.env | xargs)
fi
```

---

## ✅ Testing Your Setup

### 1. Verify MCP Servers are Running

```bash
# List all configured MCPs
claude mcp list

# Should show:
# ✓ google-calendar (enabled)
# ✓ gmail (enabled)
# ✓ slack (enabled)
# ✓ notion (enabled)
```

### 2. Test Each Integration

**Google Calendar**:
```
# In Claude Code conversation:
User: "What's on my calendar tomorrow?"
Claude: [Should fetch and display calendar events]
```

**Gmail**:
```
User: "Show me my unread emails from the last 24 hours"
Claude: [Should list recent unread emails]
```

**Slack**:
```
User: "Summarize messages in #general channel from today"
Claude: [Should access and summarize Slack messages]
```

**Notion**:
```
User: "List pages in my Notion workspace"
Claude: [Should show Notion pages you've shared with integration]
```

### 3. Using /mcp Command

```bash
# In Claude Code
/mcp

# Interactive interface shows:
# - All configured MCP servers
# - Status (enabled/disabled)
# - Toggle servers on/off
```

---

## 🐛 Troubleshooting

### Common Issues

**"MCP server not found"**
- Check `claude mcp list`
- Verify installation: `npm list -g | grep mcp`
- Try reinstalling: `npm install -g [package-name]`

**"Authentication failed"**
- Verify API keys in environment variables: `echo $GMAIL_API_KEY`
- Check credentials file paths exist
- Ensure OAuth tokens haven't expired
- Re-authenticate: `composio auth [service]`

**"Permission denied"**
- Check API scopes (e.g., Gmail, Slack)
- Verify Notion pages are shared with integration
- Review filesystem allowed paths

**"Connection timeout"**
- Check internet connection
- Verify MCP server URL is correct
- Try HTTP instead of HTTPS or vice versa
- Check firewall/proxy settings

**"Rate limit exceeded"**
- Some APIs have limits (e.g., Gmail: 1000 req/day)
- Wait and retry
- Consider upgrading API plan
- Batch requests when possible

---

## 📊 MCP Server Status Dashboard

Create a quick check command:

```bash
# Add to .claude/commands/mcp-status.md

When user runs `/mcp-status`, check all MCP integrations:

## MCP Server Status

**Google Calendar**:
- [x] Test: Get tomorrow's events
- Status: [Working/Failed]

**Gmail**:
- [x] Test: Count unread messages
- Status: [Working/Failed]

**Slack**:
- [x] Test: List channels
- Status: [Working/Failed]

**Notion**:
- [x] Test: List workspace pages
- Status: [Working/Failed]

[Provide diagnostic info for any failures]
```

---

## 🔄 Maintenance

### Weekly Checklist
- [ ] Check MCP server logs for errors
- [ ] Verify API quotas not approaching limits
- [ ] Update MCP packages: `npm update -g`
- [ ] Review permissions (remove unused)
- [ ] Rotate API keys (monthly)

### Updating MCP Servers

```bash
# Update all global MCP packages
npm update -g

# Update specific MCP
npm update -g @gmail/mcp-server

# Restart Claude Code to reload MCPs
```

---

## 🚀 Advanced: Composio Platform (All-in-One Solution)

If you want a simpler setup with 300+ integrations:

### 1. Install Composio

```bash
npm install -g composio-core
composio login
```

### 2. Authenticate Services

```bash
composio auth gmail
composio auth google-calendar
composio auth slack
composio auth notion
# ... add more as needed
```

### 3. Add Composio MCP to Claude

```bash
claude mcp add composio \
  --transport http \
  --url https://mcp.composio.dev

# Set API key
export COMPOSIO_API_KEY=your-key
```

### 4. All integrations now available through one MCP!

**Pros**:
- One setup for many services
- Easier authentication
- Unified interface

**Cons**:
- Additional dependency
- Less control over individual MCPs
- Requires Composio account

---

## 📚 Resources

### Official Documentation
- [Claude Code MCP Docs](https://docs.anthropic.com/en/docs/claude-code/mcp)
- [MCP Specification](https://modelcontextprotocol.io)

### MCP Server Directories
- [PulseMCP](https://www.pulsemcp.com) - Searchable MCP directory
- [MCP Servers Repo](https://github.com/modelcontextprotocol/servers)

### Service-Specific Guides
- [Google Calendar MCP](https://github.com/nspady/google-calendar-mcp)
- [Composio MCP Platform](https://mcp.composio.dev)
- [Zapier MCP](https://zapier.com/mcp)

### Community
- [Awesome Claude Code](https://github.com/hesreallyhim/awesome-claude-code)
- [Claude Discord](https://discord.gg/anthropic)

---

## 🎯 Recommended Setup Path

### Phase 1: Essential (Week 1)
1. ✅ Google Calendar MCP
2. ✅ Gmail MCP
3. ✅ Test with `/daily-briefing` command

### Phase 2: Communication (Week 2)
1. ✅ Slack MCP
2. ✅ Test with `/slack-catchup` command

### Phase 3: Knowledge (Week 3)
1. ✅ Notion MCP
2. ✅ Filesystem MCP (if needed)

### Phase 4: Research (Week 4)
1. ✅ Brave Search or Perplexity MCP
2. ✅ Test with `/deep-research` command

### Optional: All-in-One
- OR use Composio for everything (simpler but less control)

---

## 🎓 Next Steps

1. **Choose your approach**: Individual MCPs or Composio
2. **Start with one**: Get Google Calendar working first
3. **Test thoroughly**: Use test commands before relying on it
4. **Add gradually**: One MCP per week
5. **Monitor usage**: Check quotas and adjust as needed

---

**Questions?** Check the troubleshooting section or Claude Code docs.

**Version**: 1.0
**Last Updated**: 2025-11-14
