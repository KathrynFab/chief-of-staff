---
name: production-plan
description: Build or review Kathryn's weekly production plan from her job description, Rocks, L10 to-dos, Scorecard and calendar capacity, and sync it to the Todoist "Production Plan" project. Use for "plan my week", "production plan", "weekly review", "what should I focus on this week", "Sunday/Monday planning", "update my to-do list from my JD".
---

# Production plan (weekly)

Inputs: `context/job-description.md` (Areas of responsibility + Scorecard),
`context/priorities.md`, Notion Company Context → L10 Meetings deep dive.

## 1. Review last week (if a plan exists)
- Todoist "Production Plan": done vs. not done; ask what to carry, drop or delegate.
- Ask for (or read from Metabase/Scorecard email if available) any off-track KPIs.

## 2. Gather this week
- **Rocks**: Atlassian Goals for KF; % done and next milestone.
- **L10 to-dos**: follow the "Additional Context" procedure on the L10 Meetings deep dive
  (calendar series → latest meeting page → Jira `assignee = currentUser()` → check close-out →
  Fireflies action items if not closed out). Due by next L10 unless Jira says otherwise.
- **Calendar capacity**: hours already in meetings this week vs. free hours; flag days >6h meetings.
- **Commitments in email**: threads where she promised something ("I'll…", "will send", "by Friday").

## 3. Build the plan
For each JD area with something due or off-track, write 1–3 **outcomes** (not activities), e.g.
"Office L10 running in Sacramento office" not "work on L10s". Cap at 5–7 outcomes for the week.
Then break each outcome into next actions with an estimate and a day.

Output:
```
Week of <date> — capacity: <free hours> h
Rocks: <rock> — <status> → this week: <milestone>
Outcomes
 1. <outcome> · JD area · why now · next actions (est, day)
 …
Recurring: L10 prep · 1:1s · Scorecard review · inbox windows
Not this week (explicitly deferred): …
Delegate: <task> → <person>
```

## 4. Sync (on "yes")
- Todoist project "Production Plan", one section per JD area; tasks = next actions with due date =
  planned day, deadline = real deadline, labels per `context/preferences.md`. No PHI.
- Offer focus blocks on the calendar for the top 2 outcomes.
- Update `context/priorities.md` "This week's outcomes" (no PHI; it's committed to git).
