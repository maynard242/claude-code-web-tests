# Deep Research Command

Run this command when you need comprehensive, multi-source research on a complex topic.

## Instructions

When the user runs `/deep-research [topic]`, conduct thorough research following this methodology:

### 1. Research Planning (Phase 1)

**Understand the Request**:
- Clarify the research question if ambiguous
- Identify key aspects to investigate
- Determine success criteria (what would make this research complete?)
- Estimate scope and time needed

**Create Research Plan**:
```
## Research Plan: [Topic]

**Core Questions**:
1. [Primary question]
2. [Secondary question]
3. [Additional angles to explore]

**Research Strategy**:
- Sources to consult: [List 5-7 source types]
- Depth needed: [Surface-level / Standard / Comprehensive]
- Timeline: [How long research will take]

**Deliverables**:
- [ ] Executive summary
- [ ] Detailed findings by question
- [ ] Source citations
- [ ] Recommendations/next steps
```

### 2. Multi-Source Research (Phase 2)

Use a combination of research methods:

**A. Internet Search** (Use internet-search skill or web MCPs):
- Broad search for overview and recent information
- Scholarly sources for authoritative data
- News sources for current events
- Technical documentation for implementation details
- Community discussions for real-world experiences

**B. Document Analysis**:
- Read and summarize key documents/articles
- Extract relevant data and quotes
- Cross-reference claims across sources
- Note publication dates and author credibility

**C. Comparative Analysis**:
- Compare different perspectives/approaches
- Identify consensus vs. disagreement
- Evaluate strengths and limitations of each source

**D. Data Synthesis**:
- Combine findings from multiple sources
- Identify patterns and themes
- Surface contradictions or gaps
- Build coherent narrative

### 3. Quality Verification (Phase 3)

**Source Credibility**:
- ✓ Check author expertise
- ✓ Verify publication reputation
- ✓ Note publication date (recency)
- ✓ Look for conflicts of interest

**Fact Checking**:
- ✓ Cross-reference claims across 3+ sources
- ✓ Distinguish facts from opinions
- ✓ Note confidence level (high/medium/low)
- ✓ Flag unverified claims

**Completeness**:
- ✓ All core questions addressed
- ✓ Multiple perspectives included
- ✓ Gaps identified and acknowledged
- ✓ Sufficient depth for user's needs

### 4. Research Report (Phase 4)

Deliver findings in this format:

```
# Deep Research Report: [Topic]

**Research Date**: [Date]
**Researcher**: Claude
**Sources Consulted**: [N sources]
**Confidence Level**: [High/Medium/Low]

---

## Executive Summary (3-5 sentences)
[High-level findings, main conclusions, key recommendation]

---

## Research Questions & Findings

### 1. [Primary Question]

**Answer** (TL;DR):
[Direct answer in 2-3 sentences]

**Detailed Findings**:
[Comprehensive explanation with supporting evidence]

**Sources**:
- [Source 1]: [Key finding from this source]
- [Source 2]: [Key finding from this source]
- [Source 3]: [Key finding from this source]

**Confidence**: High/Medium/Low
**Reasoning**: [Why this confidence level]

---

### 2. [Secondary Question]
[Same format as above]

---

## Comparative Analysis

When multiple options/approaches exist:

| Aspect | Option A | Option B | Option C |
|--------|----------|----------|----------|
| [Criterion 1] | [Rating] | [Rating] | [Rating] |
| [Criterion 2] | [Rating] | [Rating] | [Rating] |
| Pros | [List] | [List] | [List] |
| Cons | [List] | [List] | [List] |

**Recommendation**: [Which option and why]

---

## Key Insights

🎯 **Main Findings**:
1. [Insight 1 - what you learned]
2. [Insight 2 - what surprised you]
3. [Insight 3 - what matters most]

⚠️ **Limitations & Caveats**:
- [What we couldn't verify]
- [Conflicting information found]
- [Gaps in available data]

📊 **Data Points**:
- [Important statistics/metrics discovered]

---

## Recommendations

**Immediate Actions**:
1. [What to do based on research]
2. [Next steps]

**Further Research Needed**:
- [ ] [Questions that emerged]
- [ ] [Areas needing deeper investigation]

**Resources to Explore**:
- [Useful links, tools, or contacts identified]

---

## Sources

**Primary Sources** ([N]):
1. [Title] - [Author/Publication] - [Date] - [URL]
   Relevance: [Why this source was valuable]

2. [Title] - [Author/Publication] - [Date] - [URL]
   Relevance: [...]

**Secondary Sources** ([N]):
[Additional sources consulted]

**Source Credibility Assessment**:
- High credibility: [N sources]
- Medium credibility: [N sources]
- Low credibility: [N sources] (used for context only)

---

## Appendix

### Research Methodology
[How research was conducted, tools used, time spent]

### Full Source List
[Complete bibliography]

### Raw Notes
[Key excerpts, quotes, data points]
```

---

## Research Best Practices

### Source Diversity
Use mix of:
- **Academic**: Research papers, peer-reviewed journals
- **Industry**: White papers, case studies, technical docs
- **News**: Reputable news outlets, trade publications
- **Community**: Reddit, Stack Overflow, forums (for practical insights)
- **Official**: Government data, organization websites
- **Expert**: Interviews, expert blogs, conference talks

### Depth Levels

**Surface-level** (15-30 min):
- 5-8 sources
- Basic understanding
- Quick facts and overview

**Standard** (1-2 hours):
- 10-15 sources
- Comprehensive understanding
- Multiple perspectives
- Actionable insights

**Deep-dive** (3+ hours):
- 20+ sources
- Expert-level understanding
- Original analysis
- Strategic recommendations

### Quality Indicators

**High-Quality Sources**:
- Recent (published within 2-3 years for tech topics)
- Authoritative (known experts/organizations)
- Well-cited (references other credible sources)
- Transparent (methodology/data disclosed)

**Red Flags**:
- No author or date
- Extreme bias or sensationalism
- No citations or sources
- Conflicts of interest undisclosed

---

## Example Usage

### Example 1: Technology Comparison
```
User: "/deep-research Compare Next.js vs. Remix for our new project"

# Deep Research Report: Next.js vs. Remix for Web Applications

**Research Date**: November 14, 2025
**Sources Consulted**: 18 sources
**Confidence Level**: High

## Executive Summary
Both Next.js and Remix are excellent React frameworks for 2025. Next.js (v15)
offers the largest ecosystem, mature tooling, and strong Vercel integration.
Remix excels in web standards adherence, nested routing, and data handling.
For your use case (e-commerce with complex data flows), Remix is recommended
due to superior data mutation patterns and progressive enhancement, though
Next.js is a safer choice if team experience is limited.

## Research Questions & Findings

### 1. What are the key technical differences?

**Answer**: Next.js uses file-based routing with React Server Components;
Remix uses nested routes with loader/action patterns based on web standards.

**Detailed Findings**:

**Architecture**:
- Next.js: App Router (RSC), Server Actions, streaming
- Remix: Nested routes, loaders/actions, optimistic UI

**Data Fetching**:
- Next.js: fetch() with cache, Server Components, mutations via Server Actions
- Remix: Route-based loaders (GET) and actions (POST), automatic revalidation

**Rendering**:
- Next.js: SSR, SSG, ISR, client-side, streaming
- Remix: SSR by default, streaming, progressive enhancement

[Sources listed with findings from each...]

**Confidence**: High
**Reasoning**: Extensive official docs + 10+ production case studies

---

### 2. Which has better performance?

**Answer**: Similar performance in benchmarks; differences are implementation-
dependent rather than framework-inherent.

[Detailed analysis with benchmarks from sources...]

---

## Comparative Analysis

| Aspect | Next.js 15 | Remix |
|--------|-----------|-------|
| Learning Curve | Medium | Medium-Hard |
| Documentation | Excellent | Good |
| Ecosystem | Very Large | Growing |
| Data Handling | Good | Excellent |
| SEO | Excellent | Excellent |
| DX (Dev Experience) | Excellent | Very Good |
| Deployment | Easy (Vercel) | Flexible |
| Bundle Size | Larger | Smaller |
| Type Safety | Very Good | Excellent |
| Community Size | Very Large | Large |

**Recommendation**: Remix for this project

**Reasoning**:
1. E-commerce needs complex mutations (Remix excels here)
2. Team has React experience (both are fine)
3. You value web standards (Remix advantage)
4. No vendor lock-in desired (Remix more portable)
5. Performance is critical (Remix smaller bundles)

---

## Key Insights

🎯 **Main Findings**:
1. Next.js has 3x larger community but Remix gaining fast (+140% growth 2024)
2. Remix's nested routing is better for complex apps like e-commerce
3. Next.js App Router still maturing (breaking changes in v14→v15)
4. Both have excellent performance when properly optimized

⚠️ **Limitations & Caveats**:
- Limited long-term production data for Remix (newer framework)
- Next.js ecosystem advantage may matter if you need many integrations
- Learning curve similar for both if coming from Create React App

📊 **Data Points**:
- Next.js: 120K+ GitHub stars, 5M+ weekly npm downloads
- Remix: 28K+ GitHub stars, 500K+ weekly npm downloads
- Both: <100ms TTFB possible, Lighthouse scores 95+

---

[Recommendations section...]
[Sources section with 18 sources listed...]
[Appendix...]
```

### Example 2: Market Research
```
User: "/deep-research What's the current state of the AI coding assistant market?"

[Similar comprehensive report on market size, key players, trends,
competitive landscape, future predictions, with 20+ sources from
market research firms, tech news, company announcements, etc.]
```

---

## Customization Options

User can add parameters:
- `/deep-research [topic] --depth=quick` - 15-30 min surface-level
- `/deep-research [topic] --depth=standard` - 1-2 hour comprehensive (default)
- `/deep-research [topic] --depth=expert` - 3+ hour deep-dive
- `/deep-research [topic] --format=presentation` - Output as slide outline
- `/deep-research [topic] --focus=technical` - Emphasize technical details
- `/deep-research [topic] --focus=business` - Emphasize business implications

## Integration with Other Tools

- Uses `internet-search` skill for web searches
- Uses `document-summarizer` skill for long articles
- Can integrate with Notion MCP to save research to workspace
- Can export to markdown files for later reference

## Notes
- Always cite sources with URLs
- Flag confidence levels for each finding
- Identify gaps and limitations honestly
- Provide actionable recommendations
- Can take 30 minutes to 3+ hours depending on depth
- Saves research notes for future reference

## Version
Created: 2025-11-14
