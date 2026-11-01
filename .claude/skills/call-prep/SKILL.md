---
name: call-prep
description: Sales-call copilot. Before a call, gathers what we know about the person (their deal, LinkedIn thread, past calls, the current case study) and turns AI Rob's call script into a one-screen view. During the call, each time the founder pastes a partial transcript or says "update", it answers with the same screen: where they are in the call, what to say next, the PULL sheet filled from the buyer's own words, and the transition line. After the call, debriefs. Use for "prep my call with X", a calendar screenshot of an upcoming call, a transcript chunk pasted mid-call, "update", "where am I", or "call's over".
---

# Call prep

Founders get lost mid-call in long scripts and have no time to read. Every reply in this skill is **one screen**, with the same blocks in the same order, so the eye always knows where to look. Speed beats completeness during a call.

Three modes: **Prep** (before), **Live** (each transcript chunk), **Debrief** (after).

AI Rob owns the call's phases, questions, branches, exits and what counts as P, U, L and L (see [Loading AI Rob](../../../AGENTS.md#loading-ai-rob)). This skill owns gathering the data, the screen format and the update loop. AI Rob's script lines only ever appear in chat for the current call; never save them to a file. If AI Rob is unavailable, say so in one line and stop.

## Prep mode

Trigger: a name, a calendar screenshot, or "script for my call with X".

### 1. Gather (in parallel)

- **The deal:** search `deals/` for the name and company and read the whole `deal.md`: context, PULL read, account, timeline and the latest review. Then their past entries in `gtm/sales.md`.
- **LinkedIn thread:** with the TalkToHumans MCP, load its `ground-rules` skill, find the contact and read the conversation.
- **Past calls:** with a call recorder MCP, search meetings with this person and read them.
- **Case study:** the current version in `gtm/case-study.md`: does this person look like that situation, and which slot is still unproven (often U).
- **Call script:** `gtm/sales-process.md`, if the founder keeps one.
- **AI Rob:** load it.

If the deal file is stale (its newest timeline line is over 14 days old, or the thread or past calls hold something newer) and the call is more than 20 minutes away, run [deal-review](../deal-review/SKILL.md) first. Otherwise build from the fresh data and leave the review for Debrief.

### 2. Build

Give AI Rob everything gathered and ask for this call's script: the phases in order, the questions and branches, the no-PULL exit and the next-step move. If it's a second call, ask for its second-call prep instead. Render it in the screen format below, with the Prep extras.

Prefill the PULL sheet from past evidence, but mark every prefilled slot 🟡 `📁 confirm`: past words still need confirming today.

If the person could fit two situations, say so on the Situation line and put a fork in the first discovery question. Never fill one situation's sheet with the other's evidence.

## Live mode

Trigger: a pasted transcript chunk, or "update", "u", "where am I".

- Call no tool except AI Rob re-reads (one parallel batch). With nothing pasted, try today's transcript from the call recorder; if it isn't there, ask for the paste in one line.
- Work out the current phase from the last few exchanges, not from the clock.
- Merge into the previous PULL sheet. Keep ✅ slots unless the buyer contradicts them. Mark changed slots 🆕.
- **Slot rules:** ✅ only for the buyer's own words (12 words max). 🟡 for a hedge, an inference, a past quote not confirmed today, or something the founder said that the buyer agreed to. ❌ for not heard. The founder's words never fill a slot.
- **Flags** on the top line: 🔥 the buyer started a purchase action or urgent next step on their own (AI Rob decides what counts); ⚠️ a hedged confirmation, or they ask for a pilot or a demo; ⏱ under 8 minutes left and no next meeting booked.
- If discovery is over and AI Rob says there's no PULL, **Say now** is the no-PULL exit.
- One screen, then stop. No intro, no recap.

## Debrief mode

Trigger: "call's over", "done", or a final full transcript.

1. One screen: the final PULL sheet, whether the buyer started a PULL action (quote it), whether the next meeting is booked and when, and the one thing that was missing.
2. Offer, as one question: run [deal-review](../deal-review/SKILL.md) on the full transcript, which logs the call in `gtm/sales.md` and reviews the deal. Don't run it without a yes.
3. If the script changed during the call in a way worth keeping, offer to add it to `gtm/sales-process.md` with today's date.

## Screen format

Same blocks, same order, every mode. About 25 lines. Skip a block only when it's empty.

```markdown
### 📍 ✅ {phase 1} › ✅ {phase 2} › **▶ {CURRENT PHASE}** › ○ {phase 4} › ○ {phase 5}
⏱ {n} min in · ~{n} left · Situation: {label}   {🔥 / ⚠️ flags}

### 🗣 Say now
> "{the one question or line to say next}"
→ {buyer answer type}: {where to go, a few words}
→ {buyer answer type}: {…}
→ {no-PULL answer}: 🚪 exit

### 🧩 PULL sheet
| | Heard (their words) | |
|---|---|---|
| **P** Project | "{quote}" | ✅ |
| **U** Why now | ❌ not heard | ask: "{question}" |
| **L** Options | {option}, {option} | ✅ |
| **L** Limits | {option}: "{quote}" · {option}: ❓ | 🟡 ask: "{question}" |

### 🔁 Transition {ready ✅ / not yet: missing U}
> "{playback sentence, filled: **bold** = their words, [❓ U] = still missing}"

### ⏭ Coming up
**{next phase}** · "{key line}"
🚪 No-PULL exit: "{exit line}"

Why: {one line of reasoning}
```

- The rail is always the first line: ✅ done, **▶** current in capitals, ○ to come.
- **Say now** holds one line and at most three short branches.
- The ask column holds the exact question that fills the slot.
- **Transition** says "ready ✅" only when all four slots are ✅.
- **Prep extras**, above the rail: `🪪` two lines from the deal's context (who they are, how the conversation started, what they pay and use if they're already in), and `🎯` one line on what a win looks like on this call.
- No paragraphs, and no dashes in anything the founder will read aloud.
