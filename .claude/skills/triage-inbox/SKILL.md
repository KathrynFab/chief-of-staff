---
name: triage-inbox
description: Prioritize Kathryn's Outlook inbox into P1–P4 using home-care operations rules, then offer reply drafts, Todoist tasks and archive suggestions. Use for "triage my inbox", "prioritize my email", "what emails need me", "clean up my inbox".
---

# Triage inbox

1. Search `mcp__Microsoft_365__outlook_email_search` for unread and flagged mail in the inbox
   (default: last 24h; she can say "this week"). Group by conversation thread.
2. Classify each thread with the Prioritization list in `CLAUDE.md` and VIPs in `context/preferences.md`:
   - **P1 — act now**: safety/coverage, incidents, regulator, a leader or direct report blocked today.
   - **P2 — today**: commitments with a date, decisions she owes, client escalations, L10 items.
   - **P3 — this week**: plan work, FYIs needing a short reply, scheduling.
   - **P4 — batch/archive**: newsletters, vendors, notifications.
   Signals: sender, words like call-out / uncovered / no-show / incident / fall / complaint /
   cancel service / survey / audit / payroll, whether she's on To vs CC, whether she was asked a direct question, age of thread.
3. Output a table per priority: `# · From · Gist (no PHI) · Why · Suggested action`.
   Flag ⚠PHI on rows whose detail is clinical/personal — gist stays generic.
4. Offer, in one line each:
   - "Draft replies for #…?" → `/draft-email` (drafts only — never send).
   - "Turn #… into Todoist tasks?" → title = verb + outcome, no client names; link the email by
     subject + date in the description; priority per `context/preferences.md`.
   - "Mark P4s read / move to a folder?" → `outlook_modify_labels` only after a yes. Never delete.
