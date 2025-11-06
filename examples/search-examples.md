# Internet Search Skill - Usage Examples

This document provides practical examples of using the Internet Search Skill with different search tools.

## Table of Contents

1. [Basic Web Search](#basic-web-search)
2. [Content Extraction with Firecrawl](#content-extraction-with-firecrawl)
3. [Privacy-Focused Search with Brave](#privacy-focused-search-with-brave)
4. [News Search with Serper](#news-search-with-serper)
5. [Advanced Scenarios](#advanced-scenarios)

## Basic Web Search

### Example 1: Quick Factual Lookup

**User Request:**
```
What is the latest stable version of Node.js?
```

**How Claude Handles It:**
- Selects: Built-in WebSearch
- Query: "Node.js latest stable version 2024"
- Returns: Current version with source links

---

### Example 2: Domain-Specific Search

**User Request:**
```
Search for TypeScript tutorials only on official Microsoft sites
```

**How Claude Handles It:**
- Selects: Built-in WebSearch
- Uses: `allowed_domains: ["microsoft.com"]`
- Query: "TypeScript tutorial"

---

## Content Extraction with Firecrawl

### Example 3: Scrape Documentation

**User Request:**
```
Extract all the authentication methods from the Auth0 documentation
```

**How Claude Handles It:**
- Selects: Firecrawl API
- Action: Scrapes auth0.com/docs/authentication
- Extracts: Structured list of auth methods with descriptions

**API Call Example:**
```bash
curl -X POST https://api.firecrawl.dev/v0/scrape \
  -H "Authorization: Bearer $FIRECRAWL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "url": "https://auth0.com/docs/authenticate",
    "formats": ["markdown", "html"],
    "onlyMainContent": true
  }'
```

---

### Example 4: Crawl Multiple Pages

**User Request:**
```
Crawl the Next.js documentation and get all routing examples
```

**How Claude Handles It:**
- Selects: Firecrawl API
- Action: Crawls nextjs.org/docs with focus on routing
- Extracts: Code examples and explanations

**API Call Example:**
```bash
curl -X POST https://api.firecrawl.dev/v0/crawl \
  -H "Authorization: Bearer $FIRECRAWL_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "url": "https://nextjs.org/docs/app/building-your-application/routing",
    "limit": 20,
    "scrapeOptions": {
      "formats": ["markdown"],
      "onlyMainContent": true
    }
  }'
```

---

## Privacy-Focused Search with Brave

### Example 5: Anonymous Research

**User Request:**
```
Search for VPN providers without any tracking
```

**How Claude Handles It:**
- Selects: Brave Search API
- Reason: Privacy-focused requirement
- Query: "best VPN providers 2024"

**API Call Example:**
```bash
curl -X GET "https://api.search.brave.com/res/v1/web/search?q=best%20VPN%20providers%202024&count=10" \
  -H "Accept: application/json" \
  -H "Accept-Encoding: gzip" \
  -H "X-Subscription-Token: $BRAVE_API_KEY"
```

---

### Example 6: Technical Developer Search

**User Request:**
```
Find recent discussions about React Server Components
```

**How Claude Handles It:**
- Selects: Brave Search API
- Reason: Good for technical content
- Filters: Recent results

**API Call Example:**
```bash
curl -X GET "https://api.search.brave.com/res/v1/web/search?q=React%20Server%20Components%20discussion&freshness=pw" \
  -H "Accept: application/json" \
  -H "X-Subscription-Token: $BRAVE_API_KEY"
```

Parameters:
- `freshness=pw`: Past week
- `freshness=pm`: Past month
- `freshness=py`: Past year

---

## News Search with Serper

### Example 7: Current Events

**User Request:**
```
What's the latest news about artificial intelligence regulation?
```

**How Claude Handles It:**
- Selects: Serper API (news mode)
- Query: "artificial intelligence regulation"
- Returns: Recent news articles

**API Call Example:**
```bash
curl -X POST "https://google.serper.dev/news" \
  -H "X-API-KEY: $SERPER_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "q": "artificial intelligence regulation",
    "num": 10
  }'
```

---

### Example 8: Image Search

**User Request:**
```
Find diagrams explaining how OAuth 2.0 works
```

**How Claude Handles It:**
- Selects: Serper API (images mode)
- Query: "OAuth 2.0 flow diagram"
- Returns: Image URLs with descriptions

**API Call Example:**
```bash
curl -X POST "https://google.serper.dev/images" \
  -H "X-API-KEY: $SERPER_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "q": "OAuth 2.0 flow diagram",
    "num": 20
  }'
```

---

## Advanced Scenarios

### Example 9: Multi-Tool Research

**User Request:**
```
Research the best practices for API rate limiting. Use multiple sources and extract specific implementation examples.
```

**How Claude Handles It:**
1. Phase 1: Broad search with WebSearch or Brave
   - Finds overview articles and documentation
2. Phase 2: Deep extraction with Firecrawl
   - Scrapes top 3 results for detailed content
   - Extracts code examples
3. Phase 3: Synthesis
   - Combines findings from multiple sources
   - Provides comprehensive answer with examples

---

### Example 10: Cross-Reference Verification

**User Request:**
```
Is Python 3.13 released? Verify from multiple sources.
```

**How Claude Handles It:**
1. Search with WebSearch: Python.org and official sources
2. Search with Brave: Community discussions and announcements
3. Cross-reference: Verify release date consistency
4. Present: Verified answer with multiple source citations

---

### Example 11: Structured Data Collection

**User Request:**
```
Create a comparison table of the top 5 cloud providers by collecting data from their pricing pages
```

**How Claude Handles It:**
1. Identify: URLs for AWS, Azure, GCP, DigitalOcean, Linode pricing
2. Use Firecrawl: Extract pricing information from each
3. Structure: Organize into comparison table
4. Present: Formatted markdown table with sources

---

## Command Reference

### WebSearch (Built-in)
```
No command needed - automatically available
Parameters:
- query: string (required)
- allowed_domains: string[] (optional)
- blocked_domains: string[] (optional)
```

### Firecrawl API
```bash
# Single page scrape
POST https://api.firecrawl.dev/v0/scrape
Headers: Authorization: Bearer $FIRECRAWL_API_KEY
Body: {"url": "...", "formats": ["markdown"]}

# Multi-page crawl
POST https://api.firecrawl.dev/v0/crawl
Body: {"url": "...", "limit": 10}
```

### Brave Search API
```bash
GET https://api.search.brave.com/res/v1/web/search?q=query
Headers: X-Subscription-Token: $BRAVE_API_KEY

Parameters:
- q: search query
- country: country code (us, uk, etc.)
- count: results count (max 20)
- offset: pagination offset
- freshness: pd (day), pw (week), pm (month), py (year)
```

### Serper API
```bash
# Web search
POST https://google.serper.dev/search
Headers: X-API-KEY: $SERPER_API_KEY
Body: {"q": "query", "num": 10}

# News search
POST https://google.serper.dev/news

# Image search
POST https://google.serper.dev/images
```

---

## Tips for Effective Searching

### 1. Be Specific
❌ Bad: "How to use React?"
✅ Good: "React hooks best practices for state management 2024"

### 2. Specify Requirements
❌ Bad: "Search for VPN info"
✅ Good: "Search for VPN comparisons with privacy focus, no tracking"

### 3. Indicate Depth Needed
❌ Bad: "What is GraphQL?"
✅ Good: "Explain GraphQL and extract implementation examples from Apollo docs"

### 4. Mention Tool Preferences
❌ Bad: "Search the web"
✅ Good: "Use Firecrawl to extract all API endpoints from the Stripe documentation"

### 5. Request Verification
❌ Bad: "Is React 19 out?"
✅ Good: "Check if React 19 is released, verify from multiple sources"

---

## Troubleshooting

### Issue: API Key Not Found
**Solution:** Ensure environment variables are set:
```bash
echo $FIRECRAWL_API_KEY  # Should show your key
export FIRECRAWL_API_KEY="your-key"  # If not set
```

### Issue: Rate Limit Exceeded
**Solution:** Claude will automatically switch to alternative tools:
- If Brave fails → Try WebSearch or DuckDuckGo
- If Firecrawl fails → Try direct WebFetch or WebSearch

### Issue: No Results Found
**Solution:** Claude will:
1. Refine the search query
2. Try broader terms
3. Switch to a different search tool
4. Ask for clarification if needed

---

## Integration Examples

### Using in Code Projects

```typescript
// Example: Search for library documentation
// User: "Search npm for the latest winston logging examples"
// Claude will:
// 1. Search npmjs.com for winston
// 2. Use Firecrawl to extract examples from docs
// 3. Present relevant code snippets
```

### Research Workflows

```markdown
// Example: Technology comparison research
// User: "Compare PostgreSQL vs MongoDB for a high-traffic app"
// Claude will:
// 1. Search for recent comparisons (WebSearch/Brave)
// 2. Extract official documentation (Firecrawl)
// 3. Find performance benchmarks (WebSearch)
// 4. Synthesize findings into comprehensive comparison
```

---

**Pro Tip:** You don't need to specify which tool to use - Claude will automatically select the best tool based on your request. However, you can always request a specific tool if you prefer!
