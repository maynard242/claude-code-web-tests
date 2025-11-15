# Meeting Scheduler Skill

## Purpose
Automatically activate when the user is scheduling meetings, checking availability, or coordinating calendars to provide intelligent scheduling assistance.

## Activation Context
This skill should activate when:
- User mentions scheduling, meetings, or calendar
- User asks about availability or time slots
- User needs to coordinate with multiple people
- Calendar-related tasks are detected via MCP

## Capabilities

### 1. Availability Analysis
- Check user's calendar for free slots
- Identify conflicts and double-bookings
- Suggest optimal meeting times
- Consider time zones for remote participants

### 2. Smart Scheduling
- Find common availability across multiple calendars
- Respect working hours and break times
- Avoid back-to-back meetings when possible
- Buffer time for preparation/travel

### 3. Meeting Optimization
- Suggest appropriate duration based on meeting type
- Recommend best time of day (focus time vs. collaborative)
- Group related meetings together
- Identify and suggest rescheduling low-priority conflicts

### 4. Calendar Hygiene
- Flag overscheduled days
- Identify missing preparation time
- Suggest focus blocks for deep work
- Recommend buffer zones

## Output Format

### Availability Check
```
## Availability: [Date Range]

**Open Slots** (>30 min):
- Mon Nov 18: 10:00-11:30am, 2:00-4:00pm
- Tue Nov 19: 9:00-10:00am, 1:00-3:00pm
- Wed Nov 20: Morning blocked, 3:00-5:00pm free

**Recommended Times**:
1. **Tue Nov 19, 2:00-3:00pm** (Best - fresh afternoon slot)
2. Mon Nov 18, 10:00-11:00am (Good - morning energy)
3. Wed Nov 20, 3:00-4:00pm (OK - end of day)

**Notes**:
- Mon is back-to-back after lunch, suggest earlier slot
- Wed morning has focus block - keep protected
```

### Multi-Person Scheduling
```
## Group Availability: [Participants]

**Common Free Times** (this week):
1. **Thu Nov 21, 2:00-3:00pm** ✓ (All available)
2. Fri Nov 22, 10:00-11:00am (John tentative)
3. Tue Nov 19, 4:00-5:00pm (Sarah has conflict)

**Recommended**: Thu Nov 21, 2:00-3:00pm
**Duration**: 1 hour
**Location**: Suggest virtual (2/3 remote)

**Draft Invite**:
Subject: [Meeting topic]
Time: Thu Nov 21, 2:00-3:00pm [Timezone]
Attendees: [List]
Agenda: [To be filled]
```

## Scheduling Guidelines

### Meeting Duration Standards
- **Quick Sync**: 15 min
- **Team Standup**: 15-30 min
- **1-on-1**: 30 min
- **Project Review**: 45-60 min
- **Planning Session**: 90-120 min
- **Workshop/Training**: 2-4 hours

### Best Times for Different Meeting Types

**Deep Focus Work** (9-11am):
- Individual work, analysis, writing
- Avoid scheduling meetings here

**Collaborative Work** (11am-3pm):
- Team meetings, brainstorming
- Client calls, presentations

**Administrative** (3-5pm):
- Email catch-up, light meetings
- Planning, organizing

**Avoid**:
- Early morning (before 9am) unless critical
- Lunch hours (12-1pm)
- End of day (after 5pm) unless urgent
- Fridays after 3pm (low energy)

### Time Zone Considerations
```
When scheduling across zones:
1. Convert all times to local time
2. Find "business hours overlap" (9am-5pm for all)
3. Rotate "inconvenient times" fairly
4. Make timezone explicit in invite
```

## Smart Scheduling Rules

### Priority-Based Scheduling
1. **P0 - Critical**: Client escalations, exec meetings (schedule ASAP)
2. **P1 - High**: Team syncs, project reviews (within 2 days)
3. **P2 - Normal**: 1-on-1s, planning (within 1 week)
4. **P3 - Low**: Informational, social (flexible)

### Conflict Resolution
```
When conflicts occur:
1. Check priority levels
2. Identify moveable vs. fixed meetings
3. Suggest rescheduling lower priority
4. Offer 2-3 alternative times
5. Respect recurring meeting patterns
```

### Buffer Time
- **Before important meetings**: 15 min prep
- **After long meetings**: 15 min decompression
- **Between locations**: 30 min travel time
- **Daily**: At least 1 hour of unscheduled time

## Integration with MCP

If Google Calendar MCP is available:
- Query calendar for availability
- Create/update/delete events
- Send invitations with agenda
- Set reminders and notifications
- Check attendee responses

## Examples

### Example 1: Find Time for Meeting
```
User: "I need to schedule a 1-hour meeting with Sarah and John next week"

## Scheduling Request: Meeting with Sarah & John

**Checking availability**...

**Best Options**:
1. **Wed Nov 20, 2:00-3:00pm** ✓ Recommended
   - All participants free
   - Mid-afternoon (good energy)
   - No conflicts before/after

2. Thu Nov 21, 10:00-11:00am
   - All free, but Sarah has back-to-back after

3. Fri Nov 22, 1:00-2:00pm
   - Available but Friday afternoon (lower energy)

**Shall I send invite for Wed Nov 20, 2:00-3:00pm?**

Draft agenda:
- Welcome & context (5 min)
- Discussion topics (40 min)
- Action items & next steps (15 min)
```

### Example 2: Calendar Optimization
```
User: "Review my calendar for next week and suggest improvements"

## Calendar Analysis: Week of Nov 18-22

**Current State**:
- 23 meetings scheduled (27.5 hours)
- 3 days with no breaks >30 min
- 4 back-to-back blocks of 3+ meetings
- Only 5 hours of focus time

**Issues Identified**:
⚠️ Tuesday: 6 consecutive meetings (9am-3pm)
⚠️ Thursday: No focus blocks for deep work
⚠️ Friday: 2 meetings could be async
⚠️ Missing prep time for client presentation Wed

**Recommendations**:
1. **Reschedule**: Move Mon 4pm standup to Tue 4pm (creates focus block)
2. **Cancel**: Fri 2pm "optional sync" (send update instead)
3. **Shorten**: Wed 11am "planning" from 60→30 min
4. **Add**: 30 min buffer before Wed client presentation
5. **Block**: Tue 8-9am and Thu 2-4pm for focused work

**Projected Improvement**:
- Meetings: 27.5 → 22 hours (-20%)
- Focus blocks: 5 → 11 hours (+120%)
- Buffer time: Added 2.5 hours
```

### Example 3: Time Zone Coordination
```
User: "Schedule call with London office (GMT) and SF team (PST)"

## Multi-Timezone Scheduling

**Participants**:
- You (EST)
- London team (GMT, +5 hours ahead)
- SF team (PST, -3 hours behind)

**Business Hours Overlap**:
Your 1:00-3:00pm EST = London 6:00-8:00pm GMT = SF 10:00am-12:00pm PST
                       ⚠️ Late for London      ✓ Good for SF

Your 9:00-11:00am EST = London 2:00-4:00pm GMT = SF 6:00-8:00am PST
                        ✓ Good for London       ⚠️ Early for SF

**Recommended**:
**10:00-11:00am EST** (compromise)
- London: 3:00pm (good)
- SF: 7:00am (early but acceptable)
- You: Mid-morning

**Fairness**: Rotate next meeting to favor SF timezone

**Calendar Invite**:
Subject: [Topic]
Time: Thu Nov 21, 10:00-11:00am EST / 3:00pm GMT / 7:00am PST
Note: "Thanks SF team for the early start - next one will be afternoon friendly!"
```

## Best Practices

### Before Scheduling
1. Check if meeting is necessary (could it be email?)
2. Define clear purpose and desired outcome
3. Invite only essential participants
4. Choose appropriate duration (default to shorter)

### When Creating Invites
1. Include clear agenda in description
2. Add video link if remote
3. Attach relevant documents
4. Set appropriate reminders
5. Request RSVP for important meetings

### After Scheduling
1. Send prep materials 24 hours before
2. Confirm attendance for critical meetings
3. Reschedule promptly if needed
4. Block prep time on calendar

## Notes
- Works best with Google Calendar MCP configured
- Respects working hours (default 9am-6pm, customizable)
- Learns preferences over time
- Privacy-focused: only accesses calendar when needed

## Version
Created: 2025-11-14
Last Updated: 2025-11-14
