---
name: outbound-setup
description: Import a founder-approved lead list and draft a short outreach sequence for the current case study, with the message from AI Rob and the buyers' own words. With the TalkToHumans MCP it imports the contacts, groups them under the case study version and sets up the sequence as a draft for the founder to review and launch; without it, it writes a CSV with the drafted messages. Use for "launch outreach", "set up a sequence for this list", "draft messages for these people", or after lead-gen.
---

# Outbound setup

Get an approved list into a sequence the founder can review and launch, grouped under the case study version it tests so the weekly review can count it.

**Draft, never send.** This skill never sends a message, connection request or email. The founder reviews and launches everything.

## 1. Inputs

- An approved list (from [lead-gen](../lead-gen/SKILL.md), a CSV, or names). If it's missing, ask.
- The current version of `gtm/case-study.md`, and its section in `outbound/playbook.md`.
- The `gtm/sales.md` entries of buyers who pulled: their words are the raw material for the message.
- The "angles tried" in `gtm/pipeline.md`: what already worked and what didn't.

## 2. The message

Load AI Rob and ask for the outbound message for this case study. Give it the case study, the buyers' own words, the angles already tried, and the founder's background from `context/founders.md`. Keep:

- One line that's interesting to the reader, and a short ask for a chat.
- No quoting the signal back at them ("saw your account got restricted"), no feature list, no pitch.
- A one-word bump two to three days later.

Show the founder the message and the sequence before setting anything up. Default sequence (from the playbook):

1. Day 0: connection request, no note.
2. Day after accept: the message.
3. Two to three days later: the bump.
4. Stop.

## 3. Set it up

**With the TalkToHumans MCP:** load its `ground-rules` skill, then `import-and-prep-list` for the import and `write-linkedin-messages` for the drafts, and follow them. Before importing, check that nobody on the list already has a folder in `deals/` or a conversation with the founder; those get a personal note, not a sequence. Group the contacts under the case study version (a tag or a view, e.g. `case study v3 · grizzlies, berry crop failed · 2026-10-17`) so the weekly review can count them. Set the sequence up as a draft and tell the founder where to review and launch it.

**Without it:** write `outbound/leads/YYYY-MM-DD.csv` with name, link, company, signals, score and the drafted messages, and give the founder the sending order.

## 4. Record

- Add the angle with its date to "angles tried" in `gtm/pipeline.md`, result "too early to tell". The weekly review fills the result.
- Tell the founder the benchmarks to watch (30%+ accept, 50%+ reply, 50%+ book) and that the weekly review will report against them.
