---
name: meetings
description: Prep Kathryn for upcoming meetings or debrief recent ones. Prep pulls attendees, related email threads, prior Fireflies action items and open to-dos into a one-page brief. Debrief pulls Fireflies action items and decisions, creates Todoist tasks and drafts follow-up emails. Use for "prep my meetings", "prep me for the L10", "debrief my meeting", "what came out of…", "action items from today's meetings".
---

# Meetings

## Prep (`/meetings prep [meeting or "today"]`)
For each meeting (skip all-hands/blocked time unless asked):
1. `outlook_calendar_search` → title, time, organizer, attendees, agenda/body.
2. Recent email threads with the attendees on the topic (last 14 days).
3. Fireflies: previous occurrence of this meeting (match date + start time) → open action items only.
4. Open Todoist/Jira items involving the attendees.
5. Brief: `Purpose · What I need from it · Open items from last time · Talking points · Decisions to push for`.
L10 special case: list her to-dos (done / not done for the to-do review), Rock status (on/off track),
Scorecard measures she owns, and issues she wants on the list — follow Notion
"L10 Norms and Procedures" for the issue pre-read format.

## Debrief (`/meetings debrief [meeting or "today"]`)
1. Find the recording in Fireflies by date + start time from the calendar event.
2. Pull summary + action items (`fireflies_get_summary`); read the transcript only if action
   items are missing. Fix name misspellings using Notion → People & Names.
3. Output: `Decisions · Kathryn's action items · Others' action items · Open questions`.
   No client names or health details — reference "client case discussed" instead.
4. Offer (on "yes"): Todoist tasks for hers (`@waiting` for others'); follow-up email draft to
   attendees via `/draft-email`; for L10s, remind that to-dos belong in Jira APC — create only if she asks.
