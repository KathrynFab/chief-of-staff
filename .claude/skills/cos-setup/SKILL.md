---
name: cos-setup
description: One-time (re-runnable) setup for Kathryn's chief of staff — checks the Microsoft 365, Todoist, Fireflies, Notion and Atlassian connectors, captures her real job description, team roster and preferences into context/, and creates her private Notion log pages. Use for "set up my chief of staff", "/cos-setup", or when a skill fails because a connector or context file is missing.
---

# Chief of staff setup

## 1. Connectors (one read-only call each, in parallel)
| Connector | Test call | If missing |
| --- | --- | --- |
| Microsoft 365 | `get_me` | claude.ai → Settings → Connectors → Microsoft 365 → sign in with work account |
| Todoist | list projects / today's tasks | claude.ai → Settings → Connectors → add **Todoist** → sign in |
| Fireflies | `fireflies_get_user` | add Fireflies connector |
| Notion | `notion-get-self` | add Notion with Tended Notion account |
| Atlassian (Jira/Goals) | `atlassianUserInfo` | add Atlassian connector |
Report ✅/❌ per connector with the fix. Continue with what works.

## 2. Context (ask one block at a time; write to `context/`)
- **Job description**: ask her to paste the JD (or a SharePoint link → `sharepoint_search` /
  `read_resource`). Rewrite `context/job-description.md` keeping the headings
  "Areas of responsibility" and "Scorecard".
- **Team**: names, roles/offices, emails, 1:1 cadence → `context/team.md`
  (offer to look up emails with `search_people`). Staff only — no HR or health details.
- **Preferences**: confirm workday hours, focus time, VIP senders → `context/preferences.md`.
- **Voice**: offer to read 5 of her recent sent emails and summarize her style into
  `context/email-voice.md` (style notes only — never copy client details).

## 3. Notion (private to Kathryn; ask before creating)
Create a private page "Chief of Staff" with two databases:
- **Daily Check-ins**: Date (date), Energy (number), Win (text), On my mind (text), Tomorrow (text).
- **Team Check-ins**: Person (title), Date (date), Mood (select: green/yellow/red), Topics (text),
  Follow-ups (text).
Record their URLs in `context/preferences.md` under "## Notion".

## 4. Todoist
Create project "Production Plan" with sections = the JD's Areas of responsibility, plus the labels in
`context/preferences.md` (ask first).

## 5. Optional automation
Offer a weekday scheduled task (~7:40am Pacific) that runs `/plan-my-day` and a Friday 3:30pm
`/production-plan` review. Create only on "yes".

Finish with: what's set up, what's still missing, and "Try `/plan-my-day`."
