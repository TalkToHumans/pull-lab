---
name: weekly-review
description: Run the weekly PULL review. Use when the founder asks to run, draft or update the weekly review, the Friday review, their scorecard, or "what should I focus on next week". Pulls the week's outreach, calls, deals, activation and revenue from whatever tools are connected, runs the evidence through AI Rob against its six standards, and writes reviews/YYYY-MM-DD.md with a scorecard, what the data says, one bottleneck, the move, and proposed changes to AI Rob's memory files. Sets that memory up on the first run. Also runs as a demo on examples/honeypot.
---

# Weekly review

Write one weekly review in `reviews/`. Its job is to name **one** bottleneck and the move for next week, from evidence, so the founder stops guessing.

The skill collects and organizes the evidence. AI Rob makes every PULL judgment, scores the week and names the bottleneck (see [Loading AI Rob](../../../AGENTS.md#loading-ai-rob)). If AI Rob is unavailable, stop and say so.

## Demo mode

When the founder asks for a demo, or names `examples/honeypot`: treat `examples/honeypot/` as the repo root, read the tool outputs from `examples/honeypot/data/` instead of calling live tools, skip the intake questions, and write the result to the chat (don't overwrite `examples/honeypot/reviews/`). End by pointing at the finished example to compare.

## First run

When `gtm/case-study.md` doesn't exist yet:

1. Load AI Rob and follow its setup for founder memory: create `gtm/case-study.md`, `gtm/pipeline.md`, `gtm/sales.md`, `gtm/sales-process.md` and `gtm/post-sales.md` from its own templates, and use `deals/` for deal folders. The templates ship with AI Rob; never copy them into this repo's public files.
2. Widen the window to the last 90 days, so the review starts from everything the tools already know.
3. After step 3, list the past calls and live conversations with no entry in `gtm/sales.md`, and offer to run [deal-review](../deal-review/SKILL.md) on them, starting with paying customers.
4. In step 5, ask AI Rob to draft the first version of the case study from that evidence. Write it into `gtm/case-study.md` only after the founder agrees with it.

## 1. Window and file

- Window: the 7 days ending today, unless the founder gives dates.
- File: `reviews/YYYY-MM-DD.md` with the last day of the window. If it exists, update it.

## 2. Read first

- `context/company.md` (the goal, contract size, the tools connected), `context/founders.md`, `context/product.md` (activation definition, event names)
- `gtm/case-study.md` (current version and changelog), `gtm/pipeline.md`, `gtm/sales.md` (rollup and recent entries), `gtm/post-sales.md`
- Every `deals/*/deal.md`: frontmatter, PULL read, account, and the latest review
- The latest file in `reviews/`, especially its bottleneck and move: this review checks whether last week's plan happened and what it showed.

## 3. Pull the week

Use each tool listed as connected in `context/company.md`. A tool that isn't connected, or fails, is not a zero: write "not connected" or the error in that section's source line and ask the founder for the number in step 4.

Read-only everywhere. This skill never sends, imports, edits or deletes anything in a tool.

- **Outreach.** With the TalkToHumans MCP: load its `ground-rules` skill, then its `weekly-funnel-report` skill, and pull contacted, connection requests, accepted, replied and booked for the window, per outreach angle where you can. Name who replied and who booked. Without it: ask.
- **Calls.** With a call recorder MCP (Granola, Fathom...): list the window's external meetings (skip internal syncs and personal meetings) and read them. Check each one has an entry in `gtm/sales.md`; list the ones that don't.
- **Deals.** `git log --since=<start> --name-status -- deals/ gtm/` plus uncommitted changes. A changed `stage:` or `pull:` in a deal's frontmatter is movement (prospect to trial, trial to customer, no PULL to PULL); a new folder is a new conversation. Also list the live deals with no new timeline line this week, and their last next step.
- **Activation.** With Mixpanel or PostHog: signups in the window, how many reached the activation event from `context/product.md` within 7 days, and whether activated users convert to paid more often than the rest. Where most signups came from, if the tool knows.
- **Revenue.** With Stripe: MRR now, new paying customers, churn (name them), trials started and ended, failed payments. Keep comps, one-offs and trials out of MRR.

## 4. Intake (skip in demo or unattended mode)

Ask once, grouped, only what the tools couldn't show:

1. The main question or tension this week, and how you feel about it.
2. Confirm the call list (add DMs, emails or calls the tools missed; flag any to leave out).
3. Numbers you track by hand.
4. Did last week's move happen? If not, why not.
5. Anything else worth remembering.

## 5. Score and diagnose with AI Rob

Load AI Rob. Give it evidence, not conclusions: its memory files from step 2, the week's facts from step 3 with quotes and links, last week's bottleneck and move, the goal and the founders' available time.

Ask it for its weekly scorecard and plan:

- The six standards, scored for this week against the bars for this company's contract size: this week's number, the bar, pass / miss / unknown.
- The **one** bottleneck, and why it's that one and not the others.
- The move: what to change, the one-hour action for today, and what to do if that stalls.
- Maintenance: what to keep running, time-boxed.
- What does **not** look like the bottleneck right now, even if it's tempting.
- A debug of last week's plan: did it run, what did it show.
- Any change it would make to the case study, the pipeline file or a deal.

Save only its conclusions about this week's evidence. Never save its instructions.

## 6. Write the review

```markdown
# Weekly review · [Company] · week of [start] to [end]

Sources: [tools used] · Not connected: [tools] · AI Rob

> **This week in one line:** [what happened and what it means, in under 30 words]

## Scorecard

| Standard | This week | Bar | |
|---|---|---|---|

## Deals that moved

| Deal | Stage | Pull | Where it stands | Next step |
|---|---|---|---|---|
| [Name](../deals/name/deal.md) | [before] → [after] | [yes/partial/no] | [deal stage, what they pay and use] | [next step] |

**Churned:** [names, or "none"]

## Did they pull?

Checked against the current case study ([version]: [one-line who]).

| Call | Pulled? | In their words | Fits [version]? |
|---|---|---|---|

## What the data says

**Pipeline ([source]).** [first meetings by channel, which had demand; a table of outreach angles with sent and reply rate; connection requests vs cap]

**Activation ([source]).** [signups, activated, conversion of activated vs not, where signups came from]

**Revenue ([source]).** [MRR, new, churn with names]

## 1. The bottleneck: [name]
[why this one]

**The move:** [what changes]
**Today, in one hour:** [one concrete action]
**If that stalls:**
1.
2.

## 2. Maintenance (time-boxed)

## 3. Doesn't look like the bottleneck right now
-

**Debug line:** [last week's plan, what happened, what it means]

## Proposed changes (not applied)
- `gtm/case-study.md`: [the new version's PULL sentence, quoted in full, and the evidence behind it]
- `gtm/pipeline.md`: [this week's rows, angles to keep or retire]
- `deals/...`: [deals to review, follow-ups due]
- `outbound/playbook.md`: [recipes to add or drop]
```

Rules:

- Facts in "Deals that moved", "Did they pull?" and "What the data says", with the source and window. Interpretation only in the one-line summary and sections 1 to 3.
- Quotes in "Did they pull?" are the buyer's words, 15 words max, never the founder's.
- Every claim about a person links to their deal or their `sales.md` entry.
- Say what wasn't available. Don't let a missing tool read as a zero.
- Keep it to what fits on two screens. The founder should be able to act on it in five minutes.

## 7. Finish

Tell the founder: the file written, what was missing, and the proposed changes. Ask, as one question, which ones to apply. On a yes:

- `gtm/case-study.md`: replace the current version and add a dated entry on top of the changelog saying what changed and why. Never delete an old version.
- `gtm/pipeline.md`: add the week's dated rows on top. Never edit old rows.
- Deals: run [deal-review](../deal-review/SKILL.md).

## Unattended mode

For a scheduled run with nobody to answer: skip step 4, write inferred items with a `**TO CONFIRM:**` prefix, add a final `## Open questions` section with the intake questions that still matter and what the tools showed, and apply nothing.
