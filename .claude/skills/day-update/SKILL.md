---
name: day-update
description: Kathryn's 4:30pm end-of-day update, emailed to her. Checks today's Top 3 against what actually happened, surfaces new P1/P2 items since morning, overdue tasks and tomorrow's start. Use when the afternoon routine fires or Kathryn says "day update" / "how did today go".
---

# Day update (4:30pm)

Read `CLAUDE.md` and `context/preferences.md` first.

## 1. Gather (in parallel)
- **This morning's plan**: the "Your day — <date>" email in Sent Items (Top 3, waiting on you).
- **Calendar**: today (what happened, what moved) and tomorrow morning.
- **Email**: since 7am — VIP senders and keywords from `context/preferences.md`; Sent Items for evidence
  that Top 3 items were done (replies sent, decisions made).
- **Todoist**: completed today; still due today/overdue in "To Do".
- **Jira**: `assignee = currentUser() AND project = APC AND statusCategory != Done`.
- **Fireflies**: today's meetings — action items for Kathryn only.

## 2. Email
Send one HTML email with `outlook_send_mail` to **kathryn@apexcare.com only**, subject
"Day update — <Day Mon D>":
```
✅ Top 3 — done / open / unknown, one line each
🚨 New since this morning (P1/P2) — one line + suggested action
⏳ Still waiting on you
📋 Overdue (Todoist + Jira)
📅 Tomorrow — first meetings + suggested Top 3
End-of-day check-in: reply with energy, a win, and what's on your mind.
```
PHI rule: clients by office/role only; for PHI-heavy threads write "see the email from <sender>, <date>".
Don't create events, tasks or Jira changes — list them as proposals.
