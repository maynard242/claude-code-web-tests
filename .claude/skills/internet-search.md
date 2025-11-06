# Internet Search Skill

This skill enables Claude to search the internet using various search tools, intelligently selecting the most appropriate tool based on user needs and context.

## Overview

You have access to multiple internet search tools, each with different strengths and use cases. Your role is to:
1. Understand the user's search requirements
2. Select the most appropriate search tool(s)
3. Execute the search effectively
4. Present results in a clear, organized manner

## Available Search Tools

### 1. **Built-in WebSearch Tool**
- **Best for**: Quick factual lookups, current events, general web searches
- **Strengths**: Fast, integrated, good for US-based searches
- **Limitations**: Only available in the US, may have limited customization
- **When to use**: Default choice for most general search queries

### 2. **Firecrawl API**
- **Best for**: Deep web scraping, structured data extraction, content crawling
- **Strengths**: Advanced scraping capabilities, can extract structured data, follows links
- **Limitations**: Requires API key, may be slower, focused on content extraction
- **When to use**:
  - Need to extract structured data from websites
  - Crawling multiple pages on a site
  - Need clean, parsed content from web pages
  - Documentation or article research

### 3. **Brave Search API**
- **Best for**: Privacy-focused searches, independent search index, developer-friendly
- **Strengths**: Privacy-respecting, good API, fresh independent index
- **Limitations**: Requires API key
- **When to use**:
  - Privacy is a concern
  - Need unfiltered search results
  - Geographic-specific searches
  - Technical or developer content

### 4. **DuckDuckGo**
- **Best for**: Quick anonymous searches, instant answers
- **Strengths**: No tracking, instant answers, easy to use
- **Limitations**: May have fewer results than major search engines
- **When to use**:
  - Quick lookups
  - Privacy-focused searches
  - Instant answer queries

### 5. **Google Custom Search API**
- **Best for**: Comprehensive searches, high-quality results
- **Strengths**: Most comprehensive index, high-quality ranking
- **Limitations**: Requires API key and setup
- **When to use**:
  - Need the most comprehensive results
  - Domain-specific searches
  - Custom search configurations

### 6. **Serper API**
- **Best for**: Google results via API, real-time data
- **Strengths**: Access to Google results, multiple search types (web, images, news)
- **Limitations**: Requires API key
- **When to use**:
  - Need Google-quality results programmatically
  - News searches, image searches
  - Real-time search results

## Decision Matrix

Use this decision tree to select the appropriate tool:

```
User needs internet search?
│
├─ Quick factual lookup / general query?
│  └─ Use: Built-in WebSearch (if available) or DuckDuckGo
│
├─ Need to scrape/extract website content?
│  └─ Use: Firecrawl API
│
├─ Privacy-focused or unfiltered results?
│  └─ Use: Brave Search API or DuckDuckGo
│
├─ Need comprehensive, high-quality results?
│  └─ Use: Google Custom Search API or Serper API
│
├─ Technical/developer documentation?
│  └─ Use: Brave Search API or Firecrawl
│
└─ News or current events?
   └─ Use: Built-in WebSearch or Serper API (news mode)
```

## Implementation Guidelines

### Using Built-in WebSearch Tool

```markdown
Use the WebSearch tool with a clear query:
- query: "your search query here"
- allowed_domains: ["example.com"] (optional, to filter results)
- blocked_domains: ["spam.com"] (optional, to exclude domains)
```

### Using Firecrawl API

```markdown
When using Firecrawl, you need:
1. Check if FIRECRAWL_API_KEY is set in environment
2. Use curl or http client to make requests:

# Scrape a single page
curl -X POST https://api.firecrawl.dev/v0/scrape \
  -H "Authorization: Bearer $FIRECRAWL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com"}'

# Crawl a website
curl -X POST https://api.firecrawl.dev/v0/crawl \
  -H "Authorization: Bearer $FIRECRAWL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com", "limit": 10}'
```

### Using Brave Search API

```markdown
When using Brave Search, you need:
1. Check if BRAVE_API_KEY is set in environment
2. Make GET request to Brave Search API:

curl -X GET "https://api.search.brave.com/res/v1/web/search?q=your+query" \
  -H "Accept: application/json" \
  -H "X-Subscription-Token: $BRAVE_API_KEY"

Parameters:
- q: search query
- country: country code (e.g., "us", "uk")
- search_lang: language code (e.g., "en")
- count: number of results (default 10, max 20)
- offset: pagination offset
```

### Using Serper API

```markdown
When using Serper API, you need:
1. Check if SERPER_API_KEY is set in environment
2. Make POST request:

curl -X POST "https://google.serper.dev/search" \
  -H "X-API-KEY: $SERPER_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"q": "your query"}'

Search types: /search, /images, /news, /places, /shopping
```

## Workflow Steps

When a user requests an internet search:

1. **Understand the Request**
   - What is the user looking for?
   - What type of information do they need?
   - Are there any specific requirements (privacy, depth, format)?

2. **Select the Tool**
   - Apply the decision matrix above
   - If multiple tools could work, prefer the built-in WebSearch for simplicity
   - Consider if API keys are available for external tools

3. **Execute the Search**
   - Craft an effective search query
   - Use appropriate parameters for the chosen tool
   - Handle API keys securely (check environment variables)

4. **Process Results**
   - Parse and understand the results
   - Extract relevant information
   - If results are insufficient, consider:
     - Refining the query
     - Trying a different search tool
     - Performing multiple searches

5. **Present Results**
   - Summarize key findings
   - Provide source URLs
   - Organize information logically
   - Offer to search further if needed

## Best Practices

1. **Query Crafting**
   - Be specific and use relevant keywords
   - Include context words (e.g., "2024", "documentation", "tutorial")
   - Use quotes for exact phrases
   - Use site: operator when appropriate

2. **API Key Management**
   - Always check if API keys are available before using external tools
   - Use environment variables: FIRECRAWL_API_KEY, BRAVE_API_KEY, SERPER_API_KEY, etc.
   - Inform user if required API keys are missing

3. **Error Handling**
   - If one search tool fails, try another
   - Provide clear error messages
   - Suggest alternatives if primary method doesn't work

4. **Privacy Consideration**
   - Use privacy-focused tools (Brave, DuckDuckGo) when user expresses privacy concerns
   - Avoid logging sensitive search queries

5. **Result Validation**
   - Verify information from multiple sources when accuracy is critical
   - Check publication dates for time-sensitive information
   - Cross-reference important facts

## Example Usage Scenarios

### Scenario 1: Quick Fact Lookup
```
User: "What's the current version of Python?"
Tool: WebSearch (built-in)
Query: "Python latest version 2024"
```

### Scenario 2: Deep Content Extraction
```
User: "Extract all API endpoints from the Stripe documentation"
Tool: Firecrawl API
Action: Crawl stripe.com/docs/api with structured extraction
```

### Scenario 3: Privacy-Focused Research
```
User: "Search for information about VPN protocols without tracking"
Tool: Brave Search API or DuckDuckGo
Query: "VPN protocols comparison WireGuard OpenVPN"
```

### Scenario 4: Current News
```
User: "Latest developments in AI regulation"
Tool: WebSearch or Serper API (news)
Query: "AI regulation news 2024"
```

## Combining Multiple Tools

Sometimes it's beneficial to use multiple tools:

1. **Broad + Deep**: Use WebSearch for overview, then Firecrawl to extract detailed content
2. **Comparison**: Use multiple search engines to compare results and find consensus
3. **Verification**: Cross-check facts using different search tools

## Troubleshooting

If searches aren't working:

1. **Check API Keys**: Verify environment variables are set
2. **Try Alternative Tool**: Switch to a different search method
3. **Refine Query**: Make the search more specific or broader
4. **Check Rate Limits**: Some APIs have usage limits
5. **Verify Network**: Ensure internet connectivity

## Notes

- Always respect robots.txt and website terms of service
- Be mindful of API rate limits and costs
- Provide attribution and source URLs
- Keep user privacy in mind when selecting tools
- Stay within ethical and legal boundaries for web scraping

---

**Remember**: The goal is to help users find accurate, relevant information efficiently. Choose the right tool for the job, and don't hesitate to try different approaches if the first attempt doesn't yield good results.
