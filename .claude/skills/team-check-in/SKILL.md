---
name: team-check-in
description: Prep for or log a 1:1 / check-in with one of Kathryn's direct reports or team members. Pulls recent email, Teams, Fireflies action items, Jira to-dos and Todoist items about that person into an agenda, then logs outcomes and follow-ups after. Use for "prep my 1:1 with…", "check in with my team", "who haven't I checked in with", "log my check-in with…".
---

# Team check-in

Team roster: `context/team.md`. Log: Notion "Team Check-ins" database (created by `/cos-setup`).

## Modes
- **"who's due?"** — compare `context/team.md` cadence with the last log entry per person and
  with the calendar; list who's overdue for a check-in and propose times
  (`outlook_find_available_time`). Book only on "yes".
- **prep <name>** —
  1. Last check-in log entry for this person: open follow-ups.
  2. Last 2 weeks: emails and Teams chats with them (`outlook_email_search`, `chat_message_search`).
  3. Fireflies: last 1:1 or shared meetings — action items for either of them.
  4. Jira APC to-dos assigned to them; Todoist tasks labeled `@1on1-<name>` or `@delegated`.
  5. Output agenda:
     ```
     1:1 — <name> · <date>
     Wins to recognize · Their open commitments · What I owe them · Decisions needed ·
     KPIs from their office (if in Scorecard) · Development / career · Questions to ask
     ```
- **log <name>** — ask for (or extract from the Fireflies recording) the takeaways, then:
  - add a row to "Team Check-ins": Person, Date, Mood (green/yellow/red), Topics, Follow-ups (no PHI,
    no HR specifics — write "HR matter discussed, see HR" instead).
  - create Todoist tasks for Kathryn's commitments; `@waiting` tasks for theirs.
  - offer a recap email draft via `/draft-email`.
