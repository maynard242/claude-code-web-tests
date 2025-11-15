# Email Analyzer Skill

## Purpose
Automatically activate when the user is working with email content to provide intelligent analysis, categorization, and action item extraction.

## Activation Context
This skill should activate when:
- User mentions emails, inbox, or Gmail
- User shares email content for review
- User asks to analyze/summarize messages
- Email-related tasks are detected via MCP

## Capabilities

### 1. Email Categorization
Classify emails into:
- **Urgent & Important**: Requires immediate response
- **Important, Not Urgent**: Requires thoughtful response, can wait
- **FYI**: Information only, no action needed
- **Low Priority**: Can be archived/deleted
- **Spam/Promotional**: Filter out

### 2. Action Item Extraction
For each important email, identify:
- [ ] Action items (what needs to be done)
- [ ] Deadlines (when it's due)
- [ ] Stakeholders (who's involved)
- [ ] Dependencies (what's blocking/required)

### 3. Response Drafting
When user needs to reply:
- Analyze the context and tone of original email
- Draft appropriate response matching formality level
- Include all necessary information
- Keep responses concise (< 200 words unless complex)

### 4. Thread Summarization
For long email threads:
- Provide chronological summary
- Highlight key decisions made
- Extract action items across all messages
- Note unresolved questions

## Output Format

### Email Analysis Template
```
## Email: [Subject Line]
**From**: [Sender]
**Priority**: [Urgent/High/Medium/Low]
**Category**: [Type]

**Summary** (1-2 sentences):
[Brief overview]

**Action Items**:
- [ ] [What to do] - [Who] - [When]

**Suggested Response**:
[Draft reply if applicable]
```

### Inbox Digest Template
```
## Inbox Summary - [Date]

**High Priority** (3)
1. [Subject] - [Sender] - [Action needed]
2. ...

**Medium Priority** (7)
1. [Subject] - [Sender] - [Summary]
2. ...

**FYI** (12)
- Quick scan items...

**Recommended Actions**:
1. Respond to [X] immediately
2. Schedule time to address [Y]
3. Archive [Z] after quick read
```

## Best Practices

### When Analyzing Emails
1. **Respect Privacy**: Never log full email content
2. **Context Matters**: Consider sender relationship
3. **Tone Detection**: Note urgency/emotion in messages
4. **Thread Awareness**: Review full conversation history

### When Drafting Responses
1. **Match Tone**: Professional ↔ Casual based on sender
2. **Be Complete**: Address all questions asked
3. **Include CTAs**: Clear next steps/requests
4. **Proofread**: Check grammar/clarity

### When Prioritizing
1. **Sender Authority**: CEO > Manager > Colleague
2. **Time Sensitivity**: Deadlines trump FYI
3. **Business Impact**: Revenue/customer facing first
4. **Personal Relevance**: Directly addressed to user

## Integration with MCP

If Gmail MCP is available:
- Pull recent unread messages
- Search for specific senders/subjects
- Mark as read/archive after processing
- Send drafted responses after user approval

## Examples

### Example 1: Single Email Analysis
```
User: "Analyze this email from my manager about Q4 planning"

## Email: Q4 Planning Meeting - Your Input Needed
**From**: Sarah Chen (Manager)
**Priority**: High
**Category**: Action Required

**Summary**:
Manager requesting your input on Q4 objectives and team resource allocation
by EOD Friday.

**Action Items**:
- [ ] Review Q3 performance metrics - You - Thu 5pm
- [ ] Draft Q4 objectives (3-5 goals) - You - Fri 2pm
- [ ] Submit resource needs to Sarah - You - Fri EOD

**Suggested Response**:
"Thanks Sarah. I'll review Q3 metrics tomorrow and have my Q4 proposals to
you by Friday 2pm. Quick question: should resource requests include contractor
budget or just FTEs?"
```

### Example 2: Inbox Digest
```
User: "Give me my email digest from the last 24 hours"

## Inbox Summary - Nov 14, 2025

**High Priority** (2)
1. Q4 Planning Input Needed - Sarah Chen - Draft objectives by Fri
2. Client Escalation: Bug Report - Alex Park - Response needed today

**Medium Priority** (5)
1. Team Lunch Next Week - Poll - Jamie Lee - Vote by Wed
2. Code Review Request: PR #453 - Dev Team - Review when available
3. Conference Speaker Invitation - Tech Summit - Decide by Nov 20
...

**FYI** (8)
- Weekly metrics dashboard, newsletter subscriptions, calendar invites...

**Recommended Actions**:
1. Respond to client escalation first (30 min)
2. Block time tomorrow for Q4 planning (2 hrs)
3. Quick wins: vote on lunch poll, review PR (45 min total)
```

## Notes
- This skill works best when Gmail MCP is configured
- Can also analyze pasted email content without MCP
- Privacy-focused: analyzes content, doesn't store emails
- Adapts to user's communication style over time

## Version
Created: 2025-11-14
Last Updated: 2025-11-14
