# Data Analyzer Skill

## Purpose
Automatically activate when the user is working with datasets, metrics, or numerical data to provide intelligent analysis, visualization suggestions, and insights.

## Activation Context
This skill should activate when:
- User shares CSV, JSON, or tabular data
- User asks about metrics, KPIs, or statistics
- User mentions trends, patterns, or anomalies
- User needs to analyze numerical information

## Capabilities

### 1. Exploratory Data Analysis
- Identify data types and structure
- Calculate basic statistics (mean, median, mode, range)
- Detect missing values and outliers
- Assess data quality

### 2. Trend Analysis
- Identify upward/downward trends
- Detect seasonality and cycles
- Spot anomalies and outliers
- Compare time periods

### 3. Comparative Analysis
- Compare across categories
- Benchmark against targets/historical data
- Identify best/worst performers
- Calculate growth rates and changes

### 4. Insight Generation
- Surface non-obvious patterns
- Suggest hypotheses for investigation
- Identify correlations
- Provide actionable recommendations

## Output Formats

### Quick Data Summary
```
## Dataset Overview: [Name]

**Size**: [N rows × M columns]
**Time Range**: [Start] to [End]
**Last Updated**: [Date]

### Key Metrics
| Metric | Value | Change |
|--------|-------|--------|
| [KPI 1] | [Value] | +12% ↑ |
| [KPI 2] | [Value] | -3% ↓ |
| [KPI 3] | [Value] | +5% ↑ |

### Quick Insights
🎯 [Main finding 1]
⚠️ [Issue to address]
✓ [Positive trend]

### Data Quality
- Missing values: [N%]
- Duplicates: [N records]
- Outliers: [N detected]
```

### Detailed Analysis
```
## Comprehensive Analysis: [Dataset Name]

### 1. Data Profile

**Structure**:
- Records: [N]
- Fields: [M]
- Date Range: [Start - End]
- Granularity: [Daily/Weekly/Monthly]

**Field Breakdown**:
| Field | Type | Unique Values | Completeness |
|-------|------|---------------|--------------|
| [Name] | [Type] | [N] | 98% |
| [Name] | [Type] | [N] | 100% |

### 2. Summary Statistics

**[Metric Category]**:
- Mean: [Value]
- Median: [Value]
- Std Dev: [Value]
- Min/Max: [Value] / [Value]
- 25th/75th Percentile: [Value] / [Value]

### 3. Trend Analysis

**Overall Trend**: [↑ Increasing / ↓ Decreasing / → Stable]

Key Observations:
- **Period 1 ([Dates])**: [What happened]
- **Period 2 ([Dates])**: [What happened]
- **Current ([Dates])**: [What happened]

Growth Rate:
- MoM: +[X]%
- QoQ: +[X]%
- YoY: +[X]%

### 4. Anomaly Detection

**Outliers Identified** ([N] total):
1. [Date]: [Metric] = [Value] ([X] std devs from mean)
   - Likely cause: [Hypothesis]
2. ...

**Missing Data**:
- [Field]: [N] missing ([X]% of total)
- Pattern: [Random / Systematic]
- Recommendation: [How to handle]

### 5. Segmentation Analysis

**By [Dimension]**:
| Segment | Count | Avg [Metric] | % of Total |
|---------|-------|--------------|------------|
| [Cat A] | [N] | [Value] | 45% |
| [Cat B] | [N] | [Value] | 32% |
| [Cat C] | [N] | [Value] | 23% |

**Top Performers**:
1. [Item] - [Metric value] ([+X% vs avg])
2. [Item] - [Metric value] ([+X% vs avg])

**Underperformers**:
1. [Item] - [Metric value] ([-X% vs avg])
2. [Item] - [Metric value] ([-X% vs avg])

### 6. Key Insights

🎯 **Primary Finding**:
[Main insight with supporting data]

📊 **Secondary Findings**:
1. [Insight 2]
2. [Insight 3]
3. [Insight 4]

⚠️ **Concerns**:
- [Risk or issue identified]
- [Data quality issue]

### 7. Recommendations

**Immediate Actions**:
1. [Action based on analysis]
2. [Action based on analysis]

**Further Investigation**:
- [ ] [Question to explore]
- [ ] [Additional data needed]

**Suggested Visualizations**:
- Line chart: [Metric] over time
- Bar chart: [Metric] by [Category]
- Heatmap: [Correlation analysis]
```

### Comparative Report
```
## Comparison: [A] vs [B]

### Side-by-Side Metrics

| Metric | [A] | [B] | Difference |
|--------|-----|-----|------------|
| [KPI 1] | [Val] | [Val] | +[X]% |
| [KPI 2] | [Val] | [Val] | -[X]% |
| [KPI 3] | [Val] | [Val] | +[X]% |

### Performance Summary

**[A] Strengths**:
- [Metric] outperforms by [X]%
- [Observation]

**[B] Strengths**:
- [Metric] outperforms by [X]%
- [Observation]

### Winner: [A / B / Tie]
**Reasoning**: [Why based on data]
```

## Analysis Frameworks

### By Analysis Type

**Descriptive** (What happened):
- Summary statistics
- Distribution analysis
- Aggregations by category/time

**Diagnostic** (Why it happened):
- Correlation analysis
- Segmentation
- Anomaly investigation

**Predictive** (What might happen):
- Trend extrapolation
- Pattern recognition
- Historical comparison

**Prescriptive** (What should we do):
- Action recommendations
- Optimization suggestions
- Risk mitigation

### By Data Type

**Time Series**:
- Trend direction and strength
- Seasonality detection
- Period-over-period comparison
- Moving averages

**Categorical**:
- Frequency distribution
- Cross-tabulation
- Chi-square tests
- Category performance ranking

**Numerical**:
- Central tendency (mean, median)
- Dispersion (std dev, range)
- Distribution shape
- Outlier detection

**Mixed**:
- Group statistics (by category)
- Correlation matrices
- Multi-dimensional analysis

## Best Practices

### Data Quality Checks
1. **Completeness**: Check for missing values
2. **Accuracy**: Validate ranges and formats
3. **Consistency**: Check for contradictions
4. **Timeliness**: Verify dates/timestamps
5. **Uniqueness**: Identify duplicates

### Statistical Rigor
1. **Sample Size**: Note if too small for conclusions
2. **Significance**: Distinguish signal from noise
3. **Correlation ≠ Causation**: Be explicit about this
4. **Confidence Levels**: Express certainty appropriately
5. **Biases**: Identify selection or sampling bias

### Insight Quality
1. **Actionable**: Focus on what can be acted upon
2. **Novel**: Highlight non-obvious findings
3. **Relevant**: Tie to business/user goals
4. **Quantified**: Use numbers, not just qualitative statements
5. **Validated**: Cross-check against other data sources

## Visualization Recommendations

### Chart Selection Guide

**Trends Over Time** → Line chart
- Multiple metrics: Multi-line chart
- With targets: Line + reference line

**Comparisons** → Bar chart
- Many categories: Horizontal bar
- Time periods: Grouped bar

**Composition** → Pie/Donut chart
- Over time: Stacked area chart
- Many parts: Treemap

**Distribution** → Histogram
- Multiple groups: Box plot
- Detect outliers: Scatter plot

**Relationships** → Scatter plot
- 3+ variables: Bubble chart
- Many variables: Correlation heatmap

**Geographic** → Map/Choropleth
- Routes/flows: Flow map

## Examples

### Example 1: Sales Data Analysis
```
User: "Analyze our Q4 sales data"

## Sales Analysis: Q4 2024

**Dataset**: 45,234 transactions | Oct 1 - Dec 31, 2024

### Key Metrics
| Metric | Value | vs Q3 | vs Q4'23 |
|--------|-------|-------|----------|
| Total Revenue | $2.4M | +12% ↑ | +18% ↑ |
| Avg Order Value | $53 | -3% ↓ | +2% ↑ |
| Transactions | 45,234 | +15% ↑ | +16% ↑ |
| Conversion Rate | 3.2% | +0.3% ↑ | +0.5% ↑ |

### Trend Analysis

**Revenue Growth**:
- Oct: $720K (baseline)
- Nov: $850K (+18% - Black Friday impact)
- Dec: $830K (+15% - holiday shopping)

**Peak Days**:
1. Nov 24 (Black Friday): $98K (+340% vs daily avg)
2. Nov 27 (Cyber Monday): $76K (+210%)
3. Dec 23 (Last-minute shopping): $54K (+85%)

### Product Performance

**Top Sellers** (by revenue):
1. Widget Pro - $420K (17.5% of total)
2. Gadget Plus - $380K (15.8%)
3. Device Max - $310K (12.9%)

**Fastest Growing** (vs Q3):
1. New Product X - +450% (launched Oct 15)
2. Widget Pro - +35%
3. Accessory Kit - +28%

### Customer Segmentation

| Segment | % of Revenue | AOV | Transactions |
|---------|--------------|-----|--------------|
| New Customers | 42% | $48 | 21,000 |
| Returning | 58% | $56 | 24,234 |
| VIP (>$500/mo) | 23% | $125 | 4,400 |

### Key Insights

🎯 **Primary Finding**:
Black Friday/Cyber Monday drove 28% of quarterly revenue despite being just
4 days (5% of quarter). Strong promotional impact.

📊 **Additional Insights**:
1. New customer acquisition up 35% YoY - marketing working
2. AOV declining slightly - more small transactions (good for volume)
3. Mobile sales now 62% (up from 54% in Q3) - optimize mobile checkout

⚠️ **Concerns**:
- Return rate spiked to 8.5% in Dec (vs 6.2% avg) - investigate quality
- Cart abandonment at 71% - room for improvement
- Low-margin products growing faster than high-margin

### Recommendations

**Immediate**:
1. Analyze Dec returns to identify quality issues
2. A/B test checkout flow to reduce 71% abandonment
3. Launch cart abandonment email campaign

**Strategic**:
1. Plan H1 promotions based on Q4 success pattern
2. Shift mix toward higher-margin products
3. Double down on mobile optimization (62% of sales)

**Further Analysis**:
- [ ] Cohort analysis of new customers (retention?)
- [ ] Geographic breakdown (any regional opportunities?)
- [ ] Time-of-day patterns for ad targeting
```

### Example 2: Website Analytics
```
User: "What's happening with our website traffic?"

## Website Traffic Analysis: Last 30 Days

**Period**: Oct 15 - Nov 14, 2024 | **Sessions**: 124,567

### Traffic Overview
| Metric | Value | vs Prior 30d |
|--------|-------|--------------|
| Sessions | 124,567 | +8.2% ↑ |
| Users | 98,432 | +9.1% ↑ |
| Pageviews | 456,789 | +5.3% ↑ |
| Avg Duration | 3:42 | -0:15 ↓ |
| Bounce Rate | 42.3% | +2.1% ↑ |

### Traffic Sources

| Source | Sessions | % | Change |
|--------|----------|---|--------|
| Organic Search | 52,341 | 42% | +12% ↑ |
| Direct | 34,562 | 28% | +3% ↑ |
| Social | 18,234 | 15% | +25% ↑ |
| Paid | 12,430 | 10% | -5% ↓ |
| Referral | 7,000 | 5% | +8% ↑ |

### Anomaly Detected

⚠️ **Nov 8-10**: Traffic spike of +340%
- Cause: Article went viral on Hacker News
- Sessions: 34,500 over 3 days
- Bounce rate: 68% (vs 42% baseline)
- Impact: Minimal conversion (not target audience)

### Top Pages
1. /blog/ai-guide - 23,450 views (+180% - viral article)
2. /pricing - 18,900 views (+12%)
3. /home - 15,600 views (+5%)
4. /features - 12,300 views (+8%)
5. /docs - 9,800 views (+15%)

### Key Insights

🎯 **Viral Traffic Impact**:
Viral article drove massive traffic but poor quality (68% bounce, 0.3% conversion).
Good for brand awareness, not leads.

📊 **Positive Trends**:
1. Organic search up 12% - SEO efforts paying off
2. Social media growth accelerating (+25%) - content strategy working
3. Docs traffic up 15% - product adoption increasing

⚠️ **Concerns**:
- Paid traffic declining despite increased spend (check campaigns)
- Bounce rate increasing (need UX improvements)
- Session duration down (content engagement issue?)

### Recommendations

1. **Paid ads**: Audit campaigns, pause underperformers
2. **Bounce rate**: A/B test homepage redesign
3. **Content**: More viral-style articles + better CTAs to convert that traffic
4. **Technical**: Page load speed (might be affecting duration)
```

## Integration with MCP

If file system or API MCPs available:
- Read CSV/Excel files directly
- Query databases for live data
- Pull metrics from analytics platforms
- Export analysis results

## Notes
- Adapts complexity to data size and user need
- Flags low-confidence findings appropriately
- Suggests additional data collection when needed
- Focuses on actionable insights, not just numbers

## Version
Created: 2025-11-14
Last Updated: 2025-11-14
