---
name: deal-review
description: Keep one file per person you're selling to, current after every touch. After a call, reply, email or "no", updates deals/<person-company>/deal.md (context, latest PULL read, billing and usage, timeline, and for live opportunities a dated AI Rob deal review on top) and logs calls in gtm/sales.md. Use for "review this call", "log this call", "where is the deal with X", "what do I do with X", "add X to deals", after a call-prep debrief, or when the weekly review proposes it.
---

# Deal review

Every time something happens with someone you're selling to (a reply, a call, an email, a "no", silence), run this. It keeps two files current:

- [deals/](../../../deals/README.md)`<person-company>/deal.md`: everything about this person, so the next conversation starts from context. The format is in [deals/README.md](../../../deals/README.md).
- [gtm/sales.md](../../../gtm/README.md): one entry per sales call, in AI Rob's format. It feeds the weekly scorecard.

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
- **Context:** who, source, what they used before us, links. Add what's new; fix what's wrong.
- **PULL (latest read):** replace it with AI Rob's new read, dated: the two verdict lines, then the P, U and L table with the buyer's own words. Never the founder's words.
- **Account:** replace it with today's check, dated.
- **Timeline:** add one line per event, oldest first.
- **Deal reviews:** for a live opportunity, add AI Rob's new review on top. Never edit an older one. No review for people with no demand, peers or partners: say so in one line instead.

## 4. Write `gtm/sales.md` (calls only)

Add the call as a new row on top of the Calls table (columns in [gtm/README.md](../../../gtm/README.md)), linked to the deal file, and update the rollup lines. P, U and L+L go in the deal file, not here. Fill the outcome of earlier rows when you learn it.

## 5. Report

In a few lines: did they pull (with the quote), what moved since the last touch, the next step, and whether this evidence supports or contradicts the current case study. If it contradicts it, propose the change to `gtm/case-study.md`; don't make it.

If nothing moved since the last review, say so: a deal that doesn't move between two reviews is itself the finding.

## Rules

- Quote the buyer. Enough quotes to audit every claim, no more.
- Never store card or bank details. Billing and analytics ids are fine.
- A failed payment is not a decision to cancel; no events may be a tracking gap. Separate measured facts from interpretation.
