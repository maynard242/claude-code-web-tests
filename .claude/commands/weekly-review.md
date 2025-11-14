# Weekly Review Command

Run this command at the end of each week to reflect on accomplishments, analyze patterns, and plan ahead.

## Instructions

When the user runs `/weekly-review`, conduct a comprehensive week-in-review following this structure:

### 1. Time Period Confirmation
- Confirm date range (default: last Monday-Friday or last 7 days)
- Allow user to specify custom range if needed

### 2. Calendar Analysis
If Google Calendar MCP is available:
- Total meetings this week
- Meeting time vs. focus time ratio
- Identify busiest days
- Note cancelled/rescheduled meetings
- Compare to previous week

Format:
```
## 📅 Calendar Overview - Week of [Date Range]

**Meeting Stats**:
- Total meetings: [N] ([X] hours)
- Focus blocks: [N] ([X] hours)
- Meeting/Focus ratio: [X:Y]
- Busiest day: [Day] ([N] meetings)

**Comparison to Last Week**:
- Meetings: [+/-X%]
- Focus time: [+/-X%]
- Trend: [Getting better/worse/stable]

**Notable**:
- Cancelled: [N] meetings
- Rescheduled: [N] meetings
- Conflicts resolved: [N]
```

### 3. Email Summary
If Gmail MCP is available:
- Emails sent/received this week
- Response time analysis
- Identify top communicators
- Note unresolved threads

Format:
```
## 📧 Email Activity

**This Week**:
- Received: [N] emails ([avg per day])
- Sent: [N] emails
- Avg response time: [X hours]
- Unread at week end: [N]

**Top Conversations** (by volume):
1. [Person/Topic] - [N] emails
2. [Person/Topic] - [N] emails
3. [Person/Topic] - [N] emails

**Action Needed**:
- [ ] [N] emails awaiting response
- [ ] [N] threads to close out
```

### 4. Accomplishments
Prompt user to reflect on what got done:

```
## ✅ Accomplishments

**Major Wins** (What are you proud of?):
1. [Accomplishment 1]
2. [Accomplishment 2]
3. [Accomplishment 3]

**Projects Advanced**:
- [Project A]: [What moved forward]
- [Project B]: [What moved forward]

**Problems Solved**:
- [Issue resolved]
- [Challenge overcome]

**Skills/Learning**:
- [What you learned this week]
```

### 5. Challenges & Blockers
Identify what didn't go well:

```
## ⚠️ Challenges This Week

**Blockers Encountered**:
1. [What blocked progress]
   - Impact: [High/Medium/Low]
   - Status: [Resolved/Ongoing/Escalated]

**Time Drains**:
- [What consumed unexpected time]
- [Meeting that could have been email]

**Misses**:
- [Deadline missed]: [Why]
- [Goal not met]: [Reason]

**Lessons Learned**:
- [What you'd do differently]
```

### 6. Pattern Analysis
Look for trends and patterns:

```
## 📊 Weekly Patterns

**Time Allocation**:
- [X]% Meetings
- [X]% Deep work
- [X]% Email/Comms
- [X]% Firefighting

**Energy & Productivity**:
- Best day: [Day] - [Why it worked]
- Worst day: [Day] - [What happened]
- Peak hours: [Time range]
- Energy drains: [What depleted you]

**Meeting Effectiveness**:
- Productive: [N] meetings
- Could've been email: [N] meetings
- Too long: [N] meetings
```

### 7. Key Metrics (if applicable)
Track relevant KPIs:

```
## 📈 Key Metrics

**Productivity**:
- Tasks completed: [N] (target: [M])
- PRs merged: [N]
- Documents created: [N]

**Communication**:
- Avg email response time: [X hours] (goal: <4 hours)
- Slack response rate: [X%]

**Project Progress**:
- [Project A]: [X%] complete (+[Y]% this week)
- [Project B]: [X%] complete (+[Y]% this week)

**Personal**:
- Work hours: [X hours] (avg [Y]/day)
- Days with >1hr focus: [N]/5
```

### 8. Next Week Planning
Look ahead and plan:

```
## 🎯 Next Week Preview - Week of [Date Range]

**Upcoming Highlights**:
- [Major meeting/event on Day]
- [Deadline on Day]
- [Time off/holiday on Day]

**Priorities** (Top 3):
1. [Priority 1]
   - Why: [Impact]
   - Time needed: [X hours]
   - Deadline: [Date]

2. [Priority 2]
   ...

3. [Priority 3]
   ...

**Prep Needed**:
- [ ] [Preparation task for next week]
- [ ] [Material to review]
- [ ] [Person to sync with]

**Time Blocking**:
- [Day]: Focus on [Priority 1] - block 9-12am
- [Day]: [Major meeting] - prep 1hr before
- [Day]: Lighter day - good for admin tasks
```

### 9. Improvements & Actions
Create actionable improvements:

```
## 🔧 Actions for Next Week

**Schedule Optimizations**:
- [ ] Move [meeting] to [better time]
- [ ] Block [X hours] for deep work on [Day]
- [ ] Decline [low-value meeting]

**Process Improvements**:
- [ ] Set up [tool/automation] to save time
- [ ] Batch [task type] into one session
- [ ] Delegate [task] to [person]

**Personal Goals**:
- [ ] Try [new approach] for [challenge]
- [ ] Learn [skill] for [upcoming project]
- [ ] Improve [area] by [specific action]
```

### 10. Reflection & Gratitude
End on a positive note:

```
## 💭 Reflection

**What went well**:
[Positive observation about the week]

**What you're grateful for**:
- [Person who helped]
- [Win or opportunity]
- [Learning experience]

**Looking ahead**:
[One-sentence intention for next week]
```

---

## Example Output

```
# Weekly Review: November 11-15, 2024

---

## 📅 Calendar Overview

**Meeting Stats**:
- Total meetings: 18 (13.5 hours)
- Focus blocks: 5 (7 hours)
- Meeting/Focus ratio: 66% meetings, 34% focus
- Busiest day: Tuesday (6 meetings)

**Comparison to Last Week**:
- Meetings: +3 (↑20%)
- Focus time: -2 hours (↓22%)
- Trend: ⚠️ Getting more meeting-heavy

**Notable**:
- Cancelled: 2 meetings (got back 1.5 hours)
- Rescheduled: 3 meetings
- One 2-hour meeting should have been 30 minutes

---

## 📧 Email Activity

**This Week**:
- Received: 187 emails (37/day avg)
- Sent: 56 emails
- Avg response time: 6.2 hours
- Unread at week end: 12

**Top Conversations**:
1. Q4 Planning - Sarah Chen (23 emails)
2. Client Project - Alex Park (18 emails)
3. Hiring Pipeline - HR Team (12 emails)

**Action Needed**:
- [ ] 4 emails awaiting response (all from Friday)
- [ ] 2 threads to close out next week

---

## ✅ Accomplishments

**Major Wins**:
1. Shipped v2.3 release - all features on time! 🎉
2. Closed ClientCo deal ($120K ARR)
3. Hired new engineer (Sarah starts Monday)

**Projects Advanced**:
- API Redesign: Completed design doc, got engineering buy-in
- Q4 Planning: Drafted objectives, awaiting manager review
- Documentation: Wrote 4 new guides for customer support

**Problems Solved**:
- Fixed production bug affecting 50 users (root cause analysis done)
- Resolved merge conflict between two major features
- Cleared backlog of 12 pending code reviews

**Skills/Learning**:
- Learned PostgreSQL query optimization (15% perf improvement)
- Better at async communication (fewer meeting requests)

---

## ⚠️ Challenges This Week

**Blockers Encountered**:
1. Design team capacity - waiting on mockups for 3 days
   - Impact: Medium (delayed feature work)
   - Status: Escalated to design manager

2. AWS permission issue - couldn't deploy to staging
   - Impact: Low (workaround found)
   - Status: Resolved Thursday

**Time Drains**:
- Slack interruptions averaged 8/day (need DND mode)
- 2-hour planning meeting could have been 45 min with better agenda

**Misses**:
- Documentation review delayed to next week (ran out of time Friday)
- Didn't complete personal OKR check-in (forgot)

**Lessons Learned**:
- Need to block focus time earlier in week, not just Friday
- Should have async'd the Thursday standup (all updates)

---

## 📊 Weekly Patterns

**Time Allocation**:
- 48% Meetings (13.5 hrs)
- 25% Deep work (7 hrs)
- 15% Email/Slack (4 hrs)
- 12% Firefighting (3.5 hrs)

**Energy & Productivity**:
- Best day: Wednesday - 3-hour focus block in morning, shipped feature
- Worst day: Tuesday - back-to-back meetings 9am-4pm, exhausted
- Peak hours: 9-11am (before meetings start)
- Energy drains: Context switching, 30-min meetings (too short to be useful)

**Meeting Effectiveness**:
- Productive: 11 meetings
- Could've been email: 4 meetings
- Too long: 3 meetings

---

## 📈 Key Metrics

**Productivity**:
- Tasks completed: 28/30 (target: 25) ✓
- PRs merged: 12
- Documents created: 7

**Communication**:
- Avg email response time: 6.2 hours (goal: <4 hours) ⚠️
- Slack response rate: 94%

**Project Progress**:
- API Redesign: 35% complete (+15% this week) ✓
- Documentation Sprint: 60% complete (+25% this week) ✓
- Q4 Planning: 80% complete (+40% this week) ✓

**Personal**:
- Work hours: 44 hours (avg 8.8/day)
- Days with >1hr focus: 3/5 (Tuesday was all meetings)

---

## 🎯 Next Week Preview - Week of Nov 18-22

**Upcoming Highlights**:
- Monday: New engineer onboarding (allocate 3 hours)
- Wednesday: Exec presentation on API redesign (HIGH STAKES)
- Friday: Half-day (Thanksgiving prep)

**Priorities**:
1. **Prepare exec presentation**
   - Why: Critical for Q1 roadmap approval
   - Time needed: 6 hours (draft + practice)
   - Deadline: Wed 2pm

2. **Onboard new engineer Sarah**
   - Why: Set her up for success
   - Time needed: 4 hours (spread across week)
   - Deadline: Ongoing

3. **Complete Q4 planning deliverables**
   - Why: Due to manager EOW
   - Time needed: 3 hours
   - Deadline: Friday 5pm

**Prep Needed**:
- [ ] Review Q3 API metrics for presentation
- [ ] Prepare Sarah's onboarding checklist
- [ ] Finalize Q4 objectives doc

**Time Blocking**:
- Monday: Focus 9-12pm (draft presentation)
- Tuesday: Sarah onboarding + meetings
- Wednesday AM: Practice presentation, Afternoon: Deliver
- Thursday: Focus on Q4 planning
- Friday: Wrap up week, only half-day

---

## 🔧 Actions for Next Week

**Schedule Optimizations**:
- [x] Already blocked Mon/Thu morning for deep work
- [ ] Decline "optional" sync meetings (save 1.5 hours)
- [ ] Move 1-on-1s to Friday AM when I'm fresher

**Process Improvements**:
- [ ] Set Slack status to DND during focus blocks
- [ ] Batch code reviews: Tue/Thu 3-4pm instead of ad-hoc
- [ ] Create email template for common responses

**Personal Goals**:
- [ ] Use "1-2-3 rule" for presentation: 1 big idea, 2 supporting points, 3 examples
- [ ] Try shorter 25-min meetings instead of 30 (see if it helps)
- [ ] Read that onboarding best practices article I saved

---

## 💭 Reflection

**What went well**:
Shipped the release on time despite some hiccups. Team collaboration was
excellent, especially during the production bug fix. Felt productive when I
had focused time - need more of that.

**What you're grateful for**:
- Alex for jumping in on the client escalation
- Design team for turning around mockups quickly (once unblocked)
- Landing the new hire - team will be stronger

**Looking ahead**:
Next week is about nailing that exec presentation and setting Sarah up for
success. If I can protect my focus time, it'll be a great week.

---

**Overall Grade**: B+ (solid week, room to improve meeting load)
**Next Week Goal**: Deliver outstanding presentation + better focus time ratio
```

---

## Customization Options

- `/weekly-review --this-week` - Current week in progress
- `/weekly-review --last-week` - Previous week (default)
- `/weekly-review --range="Nov 1-7"` - Custom date range
- `/weekly-review --export` - Save to file
- `/weekly-review --compare` - Compare to prior weeks

## Integration

- Uses Google Calendar MCP for meeting data
- Uses Gmail MCP for email stats
- Can integrate with Notion MCP to save review
- Can pull data from project management tools if available

## Best Practices

- Run Friday afternoon or Sunday evening
- Be honest in reflection (it's for you)
- Look for patterns over 4-6 weeks
- Act on insights (don't just review)
- Celebrate wins, don't just focus on problems

## Notes
- Takes 15-30 minutes to complete
- More valuable when done consistently
- Can surface trends not visible day-to-day
- Combines data (calendar/email) with reflection
- Designed for continuous improvement

## Version
Created: 2025-11-14
