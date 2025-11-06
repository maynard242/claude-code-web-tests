# Internet Search Skill

A comprehensive skill that enables Claude to search the internet using multiple tools and intelligently select the best tool for each use case.

## Installation

1. Ensure the skill file is in `.claude/skills/internet-search.md`
2. Configure API keys in your environment (optional, for external tools):
   ```bash
   export FIRECRAWL_API_KEY="your-firecrawl-api-key"
   export BRAVE_API_KEY="your-brave-api-key"
   export SERPER_API_KEY="your-serper-api-key"
   export GOOGLE_CSE_API_KEY="your-google-custom-search-key"
   export GOOGLE_CSE_ID="your-custom-search-engine-id"
   ```

## Usage

To activate the skill, simply invoke it in Claude Code:

```
/skill internet-search
```

Or just type:
```
internet-search
```

Once activated, the skill provides Claude with comprehensive knowledge about:
- Multiple internet search tools (WebSearch, Firecrawl, Brave, DuckDuckGo, Serper, Google CSE)
- Decision-making criteria for choosing the right tool
- Implementation guidelines for each tool
- Best practices for effective searching

## Supported Search Tools

### Built-in Tools
- **WebSearch**: Claude's native web search capability

### External APIs (require API keys)
- **Firecrawl**: Web scraping and content extraction
- **Brave Search**: Privacy-focused search with independent index
- **Serper**: Google search results via API
- **Google Custom Search**: Google's official search API
- **DuckDuckGo**: Anonymous search (can be used without API key)

## Example Interactions

### Quick Web Search
```
User: Search for the latest Python version
Claude: [Uses WebSearch tool automatically]
```

### Deep Content Extraction
```
User: Extract all the API methods from the OpenAI documentation
Claude: [Uses Firecrawl to scrape and structure the content]
```

### Privacy-Focused Search
```
User: Search for VPN comparisons without tracking
Claude: [Uses Brave Search API or DuckDuckGo]
```

### Current News
```
User: What's happening with AI regulation today?
Claude: [Uses WebSearch or Serper in news mode]
```

## How It Works

The skill provides Claude with:

1. **Tool Knowledge**: Detailed information about each search tool's capabilities
2. **Decision Framework**: A decision matrix to select the right tool
3. **Implementation Guides**: Step-by-step instructions for using each API
4. **Best Practices**: Query crafting, error handling, and result validation

Claude will automatically:
- Analyze your search request
- Choose the most appropriate tool
- Execute the search
- Present organized results
- Offer to refine or expand the search if needed

## Configuration

### Setting Up API Keys

#### Firecrawl
1. Sign up at https://firecrawl.dev
2. Get your API key from the dashboard
3. Set environment variable: `export FIRECRAWL_API_KEY="your-key"`

#### Brave Search
1. Sign up at https://brave.com/search/api/
2. Get your API key
3. Set environment variable: `export BRAVE_API_KEY="your-key"`

#### Serper
1. Sign up at https://serper.dev
2. Get your API key
3. Set environment variable: `export SERPER_API_KEY="your-key"`

#### Google Custom Search
1. Create a Custom Search Engine at https://programmablesearchengine.google.com/
2. Get API key from Google Cloud Console
3. Set environment variables:
   ```bash
   export GOOGLE_CSE_API_KEY="your-api-key"
   export GOOGLE_CSE_ID="your-search-engine-id"
   ```

### Environment Variables File

You can create a `.env` file in your project root:

```env
# Internet Search API Keys
FIRECRAWL_API_KEY=your-firecrawl-api-key
BRAVE_API_KEY=your-brave-api-key
SERPER_API_KEY=your-serper-api-key
GOOGLE_CSE_API_KEY=your-google-api-key
GOOGLE_CSE_ID=your-search-engine-id
```

## Advanced Usage

### Combining Multiple Tools

You can request Claude to use multiple search tools for comprehensive research:

```
User: Search for information about quantum computing using both Brave and WebSearch, then extract detailed content from the top result using Firecrawl
```

### Domain-Specific Searches

```
User: Search only within github.com for repositories about machine learning
Claude: [Uses WebSearch with allowed_domains parameter]
```

### Structured Data Extraction

```
User: Crawl the Next.js documentation and extract all API routes examples
Claude: [Uses Firecrawl with structured extraction]
```

## Troubleshooting

### API Key Issues
If you get authentication errors:
1. Verify API keys are set correctly in environment
2. Check if API keys are still valid
3. Ensure no extra spaces or quotes in the key value

### Rate Limits
If you hit rate limits:
1. Most APIs have free tier limits
2. Consider upgrading your API plan
3. Use built-in WebSearch as fallback

### No Results
If searches return no results:
1. Claude will automatically try refining the query
2. May switch to a different search tool
3. You can request a more specific or broader search

## Best Practices

1. **Start Simple**: Let Claude choose the tool automatically
2. **Be Specific**: Provide clear search requirements
3. **Privacy First**: Mention if privacy is important
4. **Verify Critical Info**: Claude will cross-check important facts
5. **API Keys**: Set up at least one external API for best results

## Skill Features

- ✅ Intelligent tool selection based on context
- ✅ Automatic fallback if primary tool fails
- ✅ Privacy-focused options available
- ✅ Deep content extraction capabilities
- ✅ Multiple search strategies (broad, deep, combined)
- ✅ Error handling and retry logic
- ✅ Result validation and cross-referencing
- ✅ Clear source attribution

## Contributing

To improve this skill:
1. Add new search tools in the skill markdown file
2. Update the decision matrix with new use cases
3. Add implementation guides for new APIs
4. Share example scenarios

## License

This skill is part of your Claude Code configuration and can be modified as needed.

## Support

For issues or questions:
- Check Claude Code documentation
- Review API provider documentation
- Verify environment configuration
- Try alternative search tools

---

**Happy Searching!** 🔍
