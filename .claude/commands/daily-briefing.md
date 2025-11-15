# Daily Briefing Command

Run this command each morning to get a comprehensive overview of your day ahead.

## Instructions

When the user runs `/daily-briefing`, perform the following steps:

### 1. Greet and Set Context
Start with a personalized greeting based on the time of day and current date.

### 2. Calendar Summary
If Google Calendar MCP is available:
- Show today's meetings in chronological order
- Highlight conflicts or tight schedules
- Note prep time needed for important meetings
- Show tomorrow's first meeting as a preview

Format:
```
## 📅 Today's Schedule - [Day, Date]

**Morning** (9am-12pm):
- 9:00-9:30am: Team Standup (Zoom link)
- 10:00-11:00am: Client Call - PrepCo (⚠️ Need deck ready)
- 11:30-12:00pm: 1-on-1 with Sarah

**Afternoon** (12pm-5pm):
- 1:00-2:30pm: Project Planning Workshop
- 3:00-3:30pm: Focus block (no meetings)
- 4:00-4:30pm: Quick sync with Marketing

**Notes**:
- ⚠️ Back-to-back 1-3pm - grab lunch early
- ✓ 90 min of focus time available
- 📝 Prep needed: Client deck (30 min before 10am)
```

If MCP not available:
- Remind user to check calendar
- Offer to analyze pasted calendar info

### 3. Email Digest
If Gmail MCP is available:
- Count unread emails
- Summarize top 3-5 priority emails
- Flag urgent items needing response today
- Note any deadlines mentioned

Format:
```
## 📧 Email Summary

**Inbox**: 23 unread (5 high priority)

**Urgent** (needs response today):
1. **Client Escalation** - Alex Park (2 hours ago)
   - Bug in production affecting 3 users
   - Action: Response + timeline needed ASAP

**Important** (respond soon):
2. **Q4 Planning Input** - Sarah Chen (Yesterday)
   - Deadline: Friday EOD
   - Action: Block 2 hours to draft

3. **Code Review Request** - Dev Team (This morning)
   - PR #453 ready for review
   - Action: 30 min review today

**FYI** (18):
- Weekly updates, newsletters, notifications...
```

If MCP not available:
- Offer to analyze inbox if user shares count/subjects
- Remind to check email

### 4. Tasks & Priorities
Suggest priority order for the day based on:
- Deadlines
- Meeting prep needs
- Urgency of emails
- Available time blocks

Format:
```
## ✅ Today's Priorities

**Before 10am** (1.5 hours):
1. Respond to client escalation (30 min) - URGENT
2. Finish client deck for 10am meeting (45 min)
3. Quick email triage (15 min)

**Mid-day** (12-1pm):
1. Lunch + prep for afternoon workshop
2. Review notes from morning meetings

**Afternoon** (2:30-4pm):
1. Code review PR #453 (30 min)
2. Start Q4 planning draft (1 hour)

**End of day**:
1. Send Q4 planning questions to Sarah
2. Tomorrow prep: [preview tomorrow's needs]

**Can defer to tomorrow**:
- [Lower priority items]
```

### 5. Quick Wins
Identify 3-5 small tasks that can be completed in <15 minutes:
```
## ⚡ Quick Wins (Complete in idle moments)

- [ ] Vote on team lunch poll
- [ ] Approve vacation request
- [ ] Schedule next month's 1-on-1s
- [ ] Review and merge simple docs PR
```

### 6. Weather & Context (Optional)
If relevant and available:
- Weather for today (if location known)
- Important news/events that might affect work
- Time zone considerations if working with global team

### 7. Motivational Close
End with a brief, encouraging note about the day ahead.

---

## Example Output

```
Good morning! It's Tuesday, November 14, 2025. Here's your daily briefing:

## 📅 Today's Schedule

**Morning** (9am-12pm):
- 9:00-9:30am: Team Standup
- 10:00-11:00am: Client Call - PrepCo ⚠️
- 11:30-12:00pm: 1-on-1 with Sarah

**Afternoon** (12pm-5pm):
- 1:00-2:30pm: Project Planning Workshop
- 3:00-4:00pm: Focus block
- 4:00-4:30pm: Marketing sync

**Notes**:
⚠️ Need client deck ready by 10am
✓ 1 hour of focus time at 3pm

---

## 📧 Email Summary

**Inbox**: 23 unread (5 high priority)

**Urgent**:
1. Client Escalation - Alex (needs response now)
2. Q4 Planning - Sarah (due Friday)

**Important**:
3. Code Review - Dev Team
4. Meeting reschedule - Jamie
5. Budget approval - Finance

[Details omitted for brevity]

---

## ✅ Today's Priorities

**Before 10am** (1.5 hours available):
1. 🔥 Respond to client escalation (30 min)
2. 📊 Finish client deck (45 min)
3. 📧 Email triage (15 min)

**Afternoon** (After meetings):
1. Review PR #453 (30 min)
2. Start Q4 planning doc (1 hour)
3. Prep for tomorrow's workshop (30 min)

---

## ⚡ Quick Wins

- [ ] Vote on lunch poll
- [ ] Approve Sam's vacation
- [ ] Schedule Nov 1-on-1s

---

You have a busy but manageable day. Focus on the client escalation first,
then you'll be set up for a productive morning. You've got this! 💪
```

---

## Customization Options

User can customize by adding parameters:
- `/daily-briefing --focus=email` - Email deep dive only
- `/daily-briefing --focus=calendar` - Calendar deep dive only
- `/daily-briefing --tomorrow` - Preview tomorrow instead
- `/daily-briefing --week` - Show week ahead

## Notes
- Run this first thing in the morning (7-9am ideal)
- Can be automated with hooks if user wants
- Adapts based on available MCP servers
- Designed to take 2-3 minutes to read
- Actionable focus - what to do, not just info dump

## Version
Created: 2025-11-14
