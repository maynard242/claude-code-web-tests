# Document Summarizer Skill

## Purpose
Automatically activate when the user needs to understand, analyze, or summarize long documents, articles, reports, or multi-page content.

## Activation Context
This skill should activate when:
- User shares long documents (>1000 words)
- User asks to summarize articles, reports, or papers
- User mentions "TL;DR", "summary", "key points"
- User needs to extract insights from dense content

## Capabilities

### 1. Executive Summary
- Capture main thesis/purpose in 2-3 sentences
- Highlight key findings or conclusions
- Note author's recommendations
- Identify intended audience

### 2. Structured Analysis
- Break down by sections/chapters
- Extract key points per section
- Identify supporting evidence
- Note counterarguments if present

### 3. Multi-Format Support
- Research papers (academic)
- Business reports
- Technical documentation
- News articles
- Legal documents
- Meeting notes
- Book chapters

### 4. Actionable Insights
- Extract action items
- Identify decisions made
- Note open questions
- Highlight deadlines/dates

## Output Formats

### Standard Summary (Short Doc <5 pages)
```
## Document Summary: [Title]

**Source**: [Author/Publication] | **Date**: [Date] | **Length**: [Pages/Words]

### Executive Summary (3 sentences)
[Core message and key takeaways]

### Key Points
1. [Main point 1]
2. [Main point 2]
3. [Main point 3]
...

### Notable Quotes
> "[Significant quote that captures essence]"

### Takeaways
- ✓ [What this means for you]
- ✓ [Action you should consider]
```

### Detailed Analysis (Long Doc >5 pages)
```
## Comprehensive Analysis: [Title]

**Document Info**:
- Author: [Name]
- Type: [Report/Paper/Article]
- Date: [Publication date]
- Length: [N pages]
- Audience: [Target readers]

### Executive Summary
[3-5 sentences covering main thesis, methodology if research, and conclusions]

### Section Breakdown

#### 1. [Section Name]
**Summary**: [2-3 sentences]
**Key Points**:
- Point 1
- Point 2

**Data/Evidence**: [Notable statistics or findings]

#### 2. [Next Section]
...

### Critical Analysis
**Strengths**:
- [What works well]

**Limitations**:
- [Gaps or weaknesses]

**Questions Raised**:
- [What's unclear or needs follow-up]

### Action Items
- [ ] [What to do based on this]
- [ ] [Follow-up research needed]

### Related Resources
- [Mentioned references worth checking]
```

### Comparative Summary (Multiple Docs)
```
## Comparative Analysis: [Topic]

**Documents Reviewed**: [N sources]

### Consensus Points (All Agree)
1. [Shared finding 1]
2. [Shared finding 2]

### Divergent Views
| Aspect | Doc A | Doc B | Doc C |
|--------|-------|-------|-------|
| [Topic] | [View] | [View] | [View] |

### Unique Insights
**From [Doc A]**: [What only this source mentioned]
**From [Doc B]**: [Unique contribution]

### Synthesis
[Your integrated understanding combining all sources]

### Recommendation
[Which source is most credible/useful for what purpose]
```

## Summarization Strategies

### By Document Type

**Academic Papers**:
- Abstract + Introduction = Core thesis
- Methodology = How they studied it
- Results = What they found
- Discussion/Conclusion = What it means

**Business Reports**:
- Executive summary first
- Financial/metrics data
- Strategic recommendations
- Risk factors

**Technical Docs**:
- Purpose and use cases
- Key features/capabilities
- Implementation details (high-level)
- Best practices

**News Articles**:
- 5 W's (Who, What, When, Where, Why)
- Key stakeholders
- Impact/implications
- Next developments

### By User Need

**Quick Scan** (30 seconds):
- 2-sentence summary
- 3 bullet points
- One action item

**Standard Review** (2-3 minutes):
- Executive summary
- 5-7 key points
- Notable data/quotes
- Takeaways

**Deep Analysis** (10+ minutes):
- Full structured breakdown
- Critical analysis
- Comparative context
- Action plan

## Quality Checks

### Accuracy
- ✓ Verify summary reflects document's actual content
- ✓ Don't add interpretations not supported by text
- ✓ Preserve author's intent and nuance
- ✓ Quote directly for critical claims

### Completeness
- ✓ Cover all major sections
- ✓ Include key supporting evidence
- ✓ Note important caveats or limitations
- ✓ Capture conclusions/recommendations

### Clarity
- ✓ Use plain language (unless technical terms necessary)
- ✓ Define acronyms on first use
- ✓ Structure logically
- ✓ Highlight most important info first

## Best Practices

### When Summarizing
1. **Read fully first** - Don't summarize while reading
2. **Identify structure** - Understand how document is organized
3. **Extract hierarchy** - Main points vs. supporting details
4. **Preserve context** - Don't distort meaning by omitting nuance
5. **Add value** - Highlight connections user might miss

### Length Guidelines
- **Tweet-length** (280 chars): For very quick updates
- **Paragraph** (100-150 words): Standard executive summary
- **One page** (300-500 words): Detailed summary
- **Multi-page** (1000+ words): Comprehensive analysis

### Attribution
Always include:
- Source/author
- Publication date
- Link/reference if available
- Page numbers for quotes

## Examples

### Example 1: Research Paper
```
User: "Summarize this AI safety research paper"

## Document Summary: Alignment of Large Language Models

**Source**: Anthropic Research Team | **Date**: Dec 2024 | **Length**: 42 pages

### Executive Summary
This paper presents Constitutional AI (CAI), a method for training AI systems
to be helpful, harmless, and honest without extensive human feedback. The
approach uses AI-generated critiques based on constitutional principles,
achieving comparable safety to RLHF with 90% less human labeling.

### Key Findings
1. **CAI reduces harmful outputs by 78%** compared to baseline models
2. **Scales efficiently** - works better with larger models (10B+ parameters)
3. **Human preference alignment** - 89% agreement with human raters
4. **Trade-off management** - Maintains helpfulness while improving safety

### Methodology
- Two-phase training: supervised learning + RL from AI feedback
- 16 constitutional principles covering harm, privacy, fairness
- Tested on models from 2.7B to 52B parameters

### Limitations
- Requires base model with some instruction-following capability
- Constitutional principles need careful design
- May be overly cautious in edge cases

### Takeaways
✓ Promising approach for scaling AI safety work
✓ Reduces human labeling burden significantly
✓ Could be combined with RLHF for best results

**Action**: Consider CAI principles for our model training pipeline
```

### Example 2: Business Report
```
User: "Give me the key points from this quarterly earnings report"

## Summary: Q4 2024 Earnings Report - TechCorp

**Quick Take**: Beat expectations on revenue (+12% YoY) but missed on profit
margins due to increased R&D spending. Stock +3% after-hours.

### Financial Highlights
- Revenue: $2.4B (↑12% YoY, beat by $80M)
- Operating Margin: 18.2% (↓2.1% YoY, missed by 1.5%)
- EPS: $1.45 (↑8%, beat by $0.05)
- Cash: $8.2B (↑$400M from Q3)

### Strategic Updates
1. **AI Platform Launch**: New product revenue of $120M in first quarter
2. **Cost Optimization**: Targeting 20% margin by Q3 2025
3. **Acquisitions**: Completed DataCo purchase for $340M

### Guidance (Q1 2025)
- Revenue: $2.5-2.6B (↑8-12%)
- Operating Margin: 19-20%
- Cautious on macro headwinds in Europe

### Market Reaction
Stock up 3.2% after-hours. Analysts positive on AI platform traction but
concerned about margin pressure.

**What to Watch**: Q1 numbers on AI platform retention and margin recovery.
```

## Integration with MCP

If file system or web MCP available:
- Read PDF documents directly
- Fetch URLs and summarize web articles
- Access Notion pages for summarization
- Export summaries to preferred format

## Notes
- Adapts depth based on document length and complexity
- Can summarize in different languages
- Maintains objectivity - separates facts from analysis
- Designed for speed - focuses on what matters most

## Version
Created: 2025-11-14
Last Updated: 2025-11-14
