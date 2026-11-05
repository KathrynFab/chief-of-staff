---
name: plan-my-day
description: Kathryn's morning brief and day plan. Runs a 2-question personal check-in, reads today's Outlook calendar, triages priority email, pulls today's Todoist tasks and open L10 to-dos, and proposes a time-blocked plan with Top 3. Use when Kathryn says "plan my day", "organize my day", "morning brief", "what's my day look like", or starts the day.
---

# Plan my day

Read `CLAUDE.md`, `context/preferences.md` and `context/priorities.md` first.

## 1. Personal check-in (30 seconds)
Ask both in one message and wait for the answer (skip if she says "skip"):
- "Energy 1–5?"
- "One thing that would make today a win?"
Use the answers: energy ≤2 → lighter plan, fewer focus blocks, more delegation suggestions.

## 2. Gather (run these in parallel)
- **Calendar**: `mcp__Microsoft_365__outlook_calendar_search` for today and tomorrow morning.
  Note meetings, gaps ≥30 min, conflicts, meetings with no agenda, and anything she organizes.
- **Email**: `mcp__Microsoft_365__outlook_email_search` — unread + flagged from the last 24h
  (72h on Mondays). Classify with the Prioritization list in `CLAUDE.md`; keep only P1/P2 here.
- **Teams**: `mcp__Microsoft_365__chat_message_search` for messages mentioning her in the last 24h.
- **Todoist**: tasks due today, overdue, and P1/P2 in "Production Plan".
- **Jira**: open APC to-dos assigned to her (`assignee = currentUser() AND project = APC AND statusCategory != Done`).
- **Fireflies**: yesterday's meetings — action items assigned to Kathryn only (no transcript dumps).

## 3. Brief (output format)
```
☀️ <Day, date> — energy <n>/5 · win: <her answer>

🚨 Needs you now (P1)          — max 5, one line each + suggested action
📅 Today                        — time · meeting · prep needed? (✓ / ⚠ no agenda / 📝 prep below)
📬 Priority email (P2)          — sender · subject gist · action (reply / delegate / decide)
✅ Tasks due today / overdue     — from Todoist + Jira
🧱 Proposed plan                — time blocks filling gaps: focus block for #1 priority,
                                  inbox windows, 1:1 prep, buffer before L10
⭐ Top 3 today
⏳ Waiting on you               — people blocked by her decision
```
PHI rule: describe client items by office/role only.

## 4. Offer actions (one line each, do them only on "yes")
- Draft replies for the P1/P2 emails → hand off to `/draft-email`.
- Put focus blocks on the calendar (`outlook_create_event`, show as busy, title "Focus: <topic>").
- Add new tasks / reschedule overdue ones in Todoist (no PHI in task names).
- Prep notes for any meeting flagged 📝 → `/meetings prep`.
