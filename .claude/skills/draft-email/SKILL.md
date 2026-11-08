---
name: draft-email
description: Write a new email, reply or reply-all in Kathryn's voice and save it to her Outlook Drafts folder. Never sends. Use for "write an email to…", "draft a reply", "respond to…", "put a draft in my outbox/drafts".
---

# Draft email

1. Read `context/email-voice.md`. If replying, fetch the thread (`outlook_email_search`, then
   `read_resource` for the message) so the draft answers what was actually asked.
2. Resolve recipients with `mcp__Microsoft_365__search_people` when only a name is given.
   If "Matt" is ambiguous, ask which one.
3. Show the draft in chat: To / CC / Subject / Body. Keep it short; first line = the ask or decision.
4. Run the PHI check before saving: if the body has a client's name, diagnosis, medications,
   care details, or a care partner's HR matter, warn Kathryn and suggest a de-identified version
   — especially for recipients outside apexcare.com / tended.team / eldercm.com.
5. Save on her go-ahead (or right away if she said "just put it in drafts"):
   - new → `outlook_create_draft`
   - reply → `outlook_create_reply_draft`; reply-all → `outlook_create_reply_all_draft`
   - edits → `outlook_update_draft`
6. Confirm: "Saved to Drafts: <subject>". **Never call send, forward or send_draft** — those are
   blocked; Kathryn sends from Outlook.
7. If the email creates a commitment for her, offer a Todoist follow-up task (label @waiting if
   she's waiting on someone else).
