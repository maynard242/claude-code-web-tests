# Claude Code Internet Search Skill

A comprehensive skill for Claude Code that enables intelligent internet searching using multiple tools and APIs. Claude automatically selects the best search tool based on your needs.

## 🌟 Features

- **Multi-Tool Support**: Integrates with WebSearch, Firecrawl, Brave Search, Serper, DuckDuckGo, and Google Custom Search
- **Intelligent Selection**: Claude automatically chooses the best tool for each search task
- **Privacy Options**: Privacy-focused search tools available (Brave, DuckDuckGo)
- **Deep Extraction**: Web scraping and structured data extraction with Firecrawl
- **Comprehensive Coverage**: From quick lookups to in-depth research

## 🚀 Quick Start

### 1. Install the Skill

The skill is located in `.claude/skills/internet-search.md` and is automatically available when you use Claude Code in this directory.

### 2. Set Up API Keys (Optional)

For external search tools, create a `.env` file from the template:

```bash
cp .env.example .env
```

Then add your API keys:

```env
FIRECRAWL_API_KEY=your-api-key
BRAVE_API_KEY=your-api-key
SERPER_API_KEY=your-api-key
```

**Note:** The skill works with just the built-in WebSearch tool. External APIs are optional but provide additional capabilities.

### 3. Use the Skill

Simply ask Claude to search:

```
User: Search for the latest TypeScript best practices

User: Extract API documentation from stripe.com

User: Find privacy-focused VPN comparisons

User: What's the latest news on AI regulation?
```

Claude will automatically:
- Select the appropriate search tool
- Execute the search
- Present organized results
- Offer to refine or expand the search

## 📚 Documentation

- **[Skill Documentation](.claude/skills/internet-search.md)** - Complete skill guide with decision matrix and implementation details
- **[Setup Guide](.claude/skills/README.md)** - Installation and configuration instructions
- **[Usage Examples](examples/search-examples.md)** - Practical examples and use cases

## 🔧 Supported Search Tools

| Tool | Best For | API Key Required |
|------|----------|------------------|
| WebSearch (built-in) | Quick lookups, general searches | No |
| Firecrawl | Web scraping, content extraction | Yes |
| Brave Search | Privacy-focused, tech content | Yes |
| Serper | News, images, Google results | Yes |
| DuckDuckGo | Anonymous quick searches | No |
| Google CSE | Comprehensive, custom searches | Yes |

## 📖 Usage Examples

### Quick Web Search
```
User: What's the current LTS version of Node.js?
→ Claude uses WebSearch for quick factual lookup
```

### Deep Content Extraction
```
User: Extract all authentication methods from the Auth0 docs
→ Claude uses Firecrawl to scrape and structure the content
```

### Privacy-Focused Research
```
User: Search for security best practices without tracking
→ Claude uses Brave Search API for privacy-respecting results
```

### Multi-Tool Research
```
User: Research API rate limiting best practices with implementation examples
→ Claude combines WebSearch (overview) + Firecrawl (code extraction)
```

See [examples/search-examples.md](examples/search-examples.md) for more detailed examples.

## 🔑 API Keys Setup

### Firecrawl (Web Scraping)
1. Sign up at [firecrawl.dev](https://firecrawl.dev)
2. Get API key from dashboard
3. Add to `.env`: `FIRECRAWL_API_KEY=your-key`

### Brave Search (Privacy-Focused)
1. Sign up at [brave.com/search/api](https://brave.com/search/api/)
2. Get API key
3. Add to `.env`: `BRAVE_API_KEY=your-key`

### Serper (Google Results)
1. Sign up at [serper.dev](https://serper.dev)
2. Get API key
3. Add to `.env`: `SERPER_API_KEY=your-key`

### Google Custom Search (Optional)
1. Create search engine at [programmablesearchengine.google.com](https://programmablesearchengine.google.com/)
2. Get API key from Google Cloud Console
3. Add to `.env`:
   ```
   GOOGLE_CSE_API_KEY=your-api-key
   GOOGLE_CSE_ID=your-search-engine-id
   ```

## 🤖 How It Works

The skill provides Claude with:

1. **Tool Knowledge**: Detailed info about each search tool's capabilities
2. **Decision Framework**: Logic to select the right tool for each task
3. **Implementation Guides**: Step-by-step API usage instructions
4. **Best Practices**: Query optimization and result validation

When you make a search request, Claude:

1. **Analyzes** your requirements (quick lookup vs. deep research, privacy needs, etc.)
2. **Selects** the most appropriate tool using the decision matrix
3. **Executes** the search with optimized queries
4. **Processes** and validates results
5. **Presents** organized, actionable information

## 🎯 Use Cases

- **Quick Facts**: "What's the latest Python version?"
- **Documentation Research**: "Extract all REST API endpoints from docs"
- **Technology Comparison**: "Compare React vs Vue with recent benchmarks"
- **Current Events**: "Latest developments in quantum computing"
- **Privacy Research**: "VPN protocols comparison without tracking"
- **Code Examples**: "Find TypeScript error handling best practices"
- **Market Research**: "Cloud provider pricing comparison"

## 🛠️ Advanced Features

### Domain Filtering
```
Search only within official documentation sites
→ Uses allowed_domains parameter
```

### Multi-Source Verification
```
Verify this information from multiple sources
→ Cross-references results from different search tools
```

### Structured Extraction
```
Create a comparison table from pricing pages
→ Uses Firecrawl to extract and structure data
```

### Combined Strategies
```
Research topic broadly, then extract specific examples
→ Combines WebSearch + Firecrawl for comprehensive results
```

## 🔒 Privacy & Ethics

- Privacy-focused tools available (Brave, DuckDuckGo)
- Respects robots.txt and terms of service
- No tracking for sensitive searches
- Clear source attribution
- Ethical web scraping practices

## 📝 Project Structure

```
.
├── .claude/
│   └── skills/
│       ├── internet-search.md    # Main skill definition
│       └── README.md              # Skill setup guide
├── examples/
│   └── search-examples.md         # Usage examples
├── .env.example                   # API keys template
└── README.md                      # This file
```

## 🤝 Contributing

To improve this skill:

1. Add new search tools in `.claude/skills/internet-search.md`
2. Update the decision matrix for new use cases
3. Add implementation guides for new APIs
4. Share example scenarios in `examples/`

## 📄 License

This project is open source and available for use and modification.

## 🆘 Support

- Check the [skill documentation](.claude/skills/internet-search.md)
- Review [usage examples](examples/search-examples.md)
- Verify [API configuration](.claude/skills/README.md)
- Try alternative search tools if one fails

## ✨ Tips

1. **Let Claude Choose**: The skill works best when Claude selects the tool automatically
2. **Be Specific**: Clear requirements help Claude pick the right tool
3. **Start Simple**: Built-in WebSearch works great for most queries
4. **Add APIs Gradually**: Start with one or two external APIs, add more as needed
5. **Verify Important Info**: Claude can cross-check facts using multiple sources

---

**Happy Searching!** 🔍

For questions or issues, please refer to the documentation in `.claude/skills/` directory.
