---
name: deal-review
description: Keep one file per person you're selling to, current after every touch. After a call, reply, email or "no", updates deals/<person-company>/deal.md (context, latest PULL read, billing and usage, timeline, and for live opportunities a dated AI Rob deal review on top), logs calls in gtm/sales.md, and updates gtm/case-study.md with the new evidence without asking. Use for "review this call", "log this call", "where is the deal with X", "what do I do with X", "add X to deals", after a call-prep debrief, or "update the deals for this week". Also runs as the weekly sweep the weekly review starts with: the week's messages, calls, signups and billing changes, filtered to what's worth a deal.
---

# Deal review

Every time something happens with someone you're selling to (a reply, a call, an email, a "no", silence), run this. It keeps three files current:

- [deals/](../../../deals/README.md)`<person-company>/deal.md`: everything about this person, so the next conversation starts from context. The format is in [deals/README.md](../../../deals/README.md).
- [gtm/sales.md](../../../gtm/README.md): one row per sales call. It feeds the weekly scorecard.
- [gtm/case-study.md](../../../gtm/README.md): the current PULL hypothesis, updated with each new piece of evidence so every other skill targets from the latest data.

AI Rob owns every judgment here: whether the buyer pulled, P, U, L+L, fit with the case study, the deal stage, the next steps (see [Loading AI Rob](../../../AGENTS.md#loading-ai-rob)). This skill gathers the evidence, adds the context and account facts, and writes the files. If AI Rob is unavailable, stop and say so.

## 1. Gather

- **The new input:** the transcript, thread, email or notes the founder gave you. If there's nothing, look in the connected tools: today's meeting in the call recorder, the latest messages in the TalkToHumans thread.
- **The person:** search `deals/` for the name and company and read the whole file. If there's none, build the context: their LinkedIn profile and thread (TalkToHumans MCP), how the conversation started, who introduced them, which outreach angle they answered.
- **The case study:** the current version in `gtm/case-study.md`.
- **Account** (skip if they have no account): with Stripe, plan, amount, since when, invoices paid or open, trial end, cancellation reason. With PostHog or Mixpanel, signup date, activation (as defined in `context/product.md`), what they actually do in the product (the events they use most, and how often), last activity. Note the ids you matched on and the date.

If it's unclear which deal the input belongs to (two people at one company, a new contact), ask once.

## 2. Read it with AI Rob

Load AI Rob. Give it the new input, the whole deal file, the case study and the account facts.

- **For a call:** ask for its call review: did they pull, P, U, L+L, the supply that fits, the next step.
- **For a live opportunity:** also ask for its deal review, in its `deal.md` format.
- **Always:** whether this person fits the current case study, and why.

If `gtm/sales.md` doesn't exist yet, create it from AI Rob's own template (it ships with AI Rob; this repo doesn't copy it), with the calls as the table described in [gtm/README.md](../../../gtm/README.md).

## 3. Write `deals/<person-company>/deal.md`

Follow the structure in [deals/README.md](../../../deals/README.md):

- **Frontmatter:** `stage` from billing first (Stripe is the truth for customer, trial and former), then the conversation; `pull` from AI Rob's read.
  - Create a new folder only for someone above the bar in [What's worth a deal](#whats-worth-a-deal); anyone below it goes in the report instead.
- **Context:** who, source, what they used before us, links. Add what's new; fix what's wrong.
- **PULL (latest read):** replace it with AI Rob's new read, dated: the two verdict lines, then the P, U and L table with the buyer's own words. Never the founder's words.
- **Account:** replace it with today's check, dated.
- **Timeline:** add one line per event, oldest first.
- **Deal reviews:** for a live opportunity, add AI Rob's new review on top. Never edit an older one. No review for people with no demand, peers or partners: say so in one line instead.

## 4. Write `gtm/sales.md` (calls only)

Add the call as a new row on top of the Calls table (columns in [gtm/README.md](../../../gtm/README.md)), linked to the deal file, and update the rollup lines. P, U and L+L go in the deal file, not here. Fill the outcome of earlier rows when you learn it.

## 5. Update `gtm/case-study.md` (every run, without asking)

The case study must always reflect the latest deals. After writing the deal file, apply what this evidence changes yourself; don't propose it and don't wait for a yes.

- **Evidence:** who has bought in this situation, the buyer quotes under P, U and L+L (a new option or limitation goes in the L+L list and, if it's a real gap, in the PULL sentence), the proof, what would kill it, and any drift in the Who (a buyer who doesn't match it).
- **Verdicts the file already set:** when a version's own graduation or kill line is met, apply it: mark the status, and promote or retire the version as that line says.
- **Changelog:** add one dated entry on top ("Evidence update (deal-review)" or the verdict), saying what changed and which deal it came from. Never delete an old version or entry.
- **Nothing changes:** if the evidence only confirms what's written, leave the file alone and say so in the report.
- Writing a new hypothesis from scratch is the weekly review's job: here, update the versions that exist.

## 6. Report

In a few lines: did they pull (with the quote), what moved since the last touch, the next step, and what you changed in the case study (step 5).

If nothing moved since the last review, say so: a deal that doesn't move between two reviews is itself the finding.

## What's worth a deal

A deal is there to teach us about PULL. Open a new one only when there's enough to learn from:

- **A strong signal:** a call, or a conversation where they said enough about a yes, a meh or a no to read their Project, why it's urgent (or not), or what they use instead and why. Their words, not ours.
- **An inbound user who pays and uses it a lot:** activated (as defined in `context/product.md`), active again since, and now paying.

Below the bar, no folder: a signup with no conversation, a trial nobody uses, a one-line "thanks" or "not now", a reply to our message that tells us nothing, a payer who barely uses the product. List them in the report with the reason, so lead-gen can reach out and a later signal can clear the bar.

An existing deal takes any new touch, even a small one: a small one is a Timeline line and a dated Account check, with no new AI Rob review.

## Weekly sweep

Run by the [weekly review](../weekly-review/SKILL.md) as its first step, or when the founder asks to "update the deals for this week". It covers what happened in a window, never every deal: the weekly review passes its catch-up (from the day after the last review to the week's last day), so nothing between two reviews is missed; asked on its own, the last 7 days.

1. **Collect the window's signals** from each connected tool: conversations where the other side wrote (TalkToHumans), external calls (call recorder), new signups and their usage (PostHog or Mixpanel), and billing changes: trials started or ended, new payers, upgrades, downgrades, cancellations, failed payments (Stripe). Also compare the `stage:` of every deal that has a billing id with its subscription today: a drift is a signal.
2. **Match** each signal to a deal by name, email, company, thread link and billing or analytics ids. One person or workspace, one deal; several signals for one person are one update.
3. **Filter** with [What's worth a deal](#whats-worth-a-deal): existing deals take every signal; new people only above the bar.
4. **Run steps 1 to 5** on each deal that's left, as one batch: load AI Rob once and give it the whole batch, and update the case study once for the batch. A match you're unsure of waits for one grouped question (or a `TO CONFIRM` line when nobody's there to answer).
5. **Report** in four lists, each name linked, with the signal behind it: created, updated, below the bar (and why), unsure. The weekly review copies them as they are.

## Rules

- Quote the buyer. Enough quotes to audit every claim, no more.
- Never store card or bank details. Billing and analytics ids are fine.
- A failed payment is not a decision to cancel; no events may be a tracking gap. Separate measured facts from interpretation.
