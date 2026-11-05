# Chief of Staff

A Claude Code chief of staff for Kathryn Fabiani, VP of Home Care Operations at ApexCare.
It connects Outlook mail & calendar, Teams, Fireflies meetings, Todoist, Jira/Atlassian Goals
and Notion to organize the day, prioritize email, run team and personal check-ins, keep a weekly
production plan based on the job description, and write emails **into Drafts only**.

## Commands
| Command | Use it to |
| --- | --- |
| `/cos-setup` | First run: check connectors, add your JD, team and preferences, create Notion logs |
| `/plan-my-day` | Morning brief + time-blocked plan + Top 3 |
| `/triage-inbox` | P1–P4 email priorities with draft/task/archive suggestions |
| `/draft-email` | Write an email or reply and save it to Outlook Drafts |
| `/team-check-in` | Who's due for a check-in; prep or log a 1:1 |
| `/personal-check-in` | 2-minute morning or end-of-day check-in |
| `/production-plan` | Weekly plan from JD + Rocks + L10 to-dos, synced to Todoist |
| `/meetings` | Prep upcoming meetings or debrief recent ones |

Or just talk to it: "what needs me today?", "draft a reply to Joh saying yes to Thursday".

## How it's built
- `CLAUDE.md` — the chief of staff's operating manual: role, systems, prioritization rules, hard rules.
- `context/` — your JD, team, priorities, preferences and email voice. Edit these; every skill reads them.
- `.claude/skills/` — one folder per command.
- `.claude/settings.json` — guardrails: sending, forwarding and deleting email, and posting to Teams,
  are **blocked**. Read-only lookups and draft creation run without prompts.

## Getting started
1. In claude.ai → Settings → Connectors, make sure **Microsoft 365, Todoist, Fireflies, Notion and
   Atlassian** are connected.
2. Open a Claude Code session on this repo and run `/cos-setup`.
3. Replace the DRAFT in `context/job-description.md` with your real JD (setup will ask).
4. Every morning: `/plan-my-day`. Every Friday: `/production-plan`.

## Privacy
Email, Teams and Fireflies can contain client PHI. The chief of staff refers to clients by office/role
only and never writes client or HR details into Todoist, Notion, Jira or this repo. Don't paste PHI
into `context/` files — they're committed to git.
