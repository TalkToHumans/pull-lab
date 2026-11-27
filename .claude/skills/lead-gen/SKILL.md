---
name: lead-gen
description: Turn the current case study in gtm/case-study.md into the week's quota of people to contact, warmest first. Works out the quota from the funnel (contacted to first meeting rates in gtm/pipeline.md, capped by what the founder can send in a week), then fills it down a waterfall. First come signups and trials the founder hasn't had a call with, then leads buried in the inbox and follow-ups owed (unanswered replies, positive replies never booked, stalled deals). Then warm people who engaged with the founder's content, a borrowed audience's post or their profile and fit the case study. Then two recipes from the signal library (posts and threads, job ads, competitor complaints, engagers of competitors' or influencers' posts), at least one outside post search. Then a capped test of cold prospects (20 a week), saying what the gap costs instead of filling it. Scores them by tier (a direct signal, or two that agree), each with a reason to talk this week, returns the list for the founder to approve, then runs outbound-setup on the approved list in the same session so the drafts are ready to review. Use for "find leads", "find and draft leads for next week", "prep next week's outreach", "who should I contact this week", "source people for my case study", "I need more leads", or when the weekly review's move needs a new batch.
---

# Lead gen

Fill the week's quota of people to contact, warmest first, all of them in the case study's shape. Signals decide who comes first; the quota decides how far down the list you go.

Follow the rules in [outbound/playbook.md](../../../outbound/playbook.md). The short version: start from the case study; every lead needs a reason to talk now, in one sentence (a direct signal, or two signals that agree); wide in and 90 to 99% out; by hand before automating.

## 1. Read the case study

Read the current version in `gtm/case-study.md`: who, the PULL sentence, P, U, L+L, and the proof. Read the `gtm/sales.md` entries of the buyers who pulled: their own words are the best source of search terms. Read the case study's section in `outbound/playbook.md` if one exists, and the "angles tried" in `gtm/pipeline.md`.

If the founder asks for leads for a different situation than the current version, say so and ask whether to test it as a separate sprint.

If the current version's block in the playbook is parked, read its reopen condition. When the condition is met, or the block doesn't say, tell the founder in one line why it was parked and ask whether to unpark it before searching. Never run only part of lead gen without saying so up front.

## 2. Set the week's quota

Work out how many people to contact this week, and show the math in one short table:

1. **Meeting target:** the first-meetings bar in `gtm/pipeline.md` (the founder can set a lower one for the week).
2. **Rates, last 4 to 6 weeks, from `gtm/pipeline.md`** (or the outreach tool's own report): contacted to first meeting held, per source when the file splits it (signups, warm hand-picked sends, cold). Fall back on the playbook's benchmarks when a source has fewer than 20 contacts, and say so.
3. **Quota per source** = the meetings each source should bring ÷ its rate. Total quota = their sum.
4. **Cap:** new connection requests or cold emails can't exceed what the founder's accounts can send safely in a week (on LinkedIn, about 100 connection requests a week on a free account). People already connected, signups and follow-ups get a message, not a request, so they don't count against the cap. When the quota is above the cap, say how many meetings the gap costs and fill to the cap.

The quota is a floor for the search, not a reason to lower the bar: someone who is out (a seller, a competitor, no fit) stays out even when the quota isn't met.

## 3. Write the signals

The current version's block in the playbook holds its signal library. If it has none yet, draft one and show it to the founder before searching. Sort each signal by type:

- **Direct:** they're doing the Project now, in public or in your product: a first-person post or comment about the Project or a failing option, a question in a thread, a signup who used the product. Use the words buyers used.
- **Indirect:** a trace the situation leaves without them saying it: a job ad for the role the Project would need (the need is often written in the ad), a complaint or low review about a competitor, a comment (not a bare reaction) on a competitor's, an influencer's or a borrowed audience's post about the topic.
- **Inferable:** the company's shape or stack makes the Project likely (team size, tools, how the founder posts). Never enough alone.
- **Urgency:** the case study's U happened in the last 30 to 60 days. It ranks the list; it gates outreach only when the case study says the U must be there.
- **Out:** competitors, people who sell the same thing as a service, anyone the evidence says isn't the buyer.

Before counting a signal, check it (the playbook's "Checking a signal"): fresh, specific, from the right person (the buyer, not an employee or a fan), not the same event repeated across sources, and still odd if they never bought anything. A job ad can be a replacement or a stale post; a funding round can precede cuts.

Every lead kept ends with **one sentence: "they could answer this week because…"**. No sentence, no message.

Load AI Rob (see [Loading AI Rob](../../../AGENTS.md#loading-ai-rob)) and check the signal library against the case study (is the urgency the case study's U, does a direct signal show the Project, not just the topic). If AI Rob is unavailable, stop and say so.

## 4. Find them

The lead gen waterfall. Go down it in order. Steps 1 to 3 always run in full: these people already know the founder, and trust and a first reply, the hardest steps, are done. Steps 4 and 5 run until the quota is met. Paying customers are never leads: they belong to the weekly review's success work.

1. **Signups and trials with no call yet**, from the last 60 days. Match each signup to a person (email to LinkedIn or company), check `deals/` and `gtm/sales.md` for a call, and keep the ones in the case study's Who. What they did in the product counts as a direct signal. They get a personal note asking what was going on the week they signed up, not a sequence.
2. **Leads buried in the inbox, and follow-ups owed.** Read the founder's inboxes (LinkedIn, email) and `deals/` for:
   - replies the founder never answered (the thread is waiting on the founder), from the last 60 days, including replies to old sequences, inbound DMs and connection notes;
   - positive replies that never booked a meeting, and meetings offered with no slot taken;
   - deals with no new timeline line in 14+ days and no next meeting booked;
   - trials that ended with no card.

   Keep only the people whose own words fit the current case study, or who showed PULL before. Warm isn't PULL: someone with no Project or no deadline gets nothing, because following up would be pushing. An unanswered reply is the exception: it always gets an answer, and fits or not, the answer goes in the list so nothing stays buried. Each time the case study gets a new version, re-check the past "no fit" deals against it.
3. **Warm: people who engaged with the founder's content, viewed their profile, or commented on a borrowed audience's post about the founder's work** (a collab, a guest post, a newsletter that featured them) in the last 30 days, and whose profile fits the case study's Who. The engagement is warm, not a need signal: score the rest from their words, profile and company.
4. **Recipes from the signal library.** Run **2 recipes** from the current version's block, **at least one outside post search** (job ads, competitor reviews and complaints, public threads, engagers of a competitor's or an influencer's posts). Run a new recipe by hand on 20 to 50 people first. Log what each recipe gave in the block (looked at, kept, contacted, replies, qualified replies, meetings) and give it a verdict after about 50 leads: keep, change or drop.
5. **Cold, by role and company size: a capped test, not a filler.** At most **20 a week**. Translate the Who into filters, exclude the Out list, read each headline and company, and prefer people likely to accept (an active profile, 1,000+ connections when visible). Mark them "cold, no signal". **When steps 1 to 4 don't fill the quota, say how many meetings the gap costs instead of filling it with more cold.**

**With the TalkToHumans MCP (recommended).** Lead gen writes the brief; the MCP executes it. Load its `ground-rules` skill, then follow its `find-leads` skill for the searches and imports, passing it the brief: the signals by type from step 3 (including job titles and ad keywords for this version), the Out list, the quota and the cap. Use its job offers tool for job ads, `content-engagers` (with `import_content`) for the engagers of a competitor's, an influencer's or a borrowed audience's post, and `track_content` for a daily watch on those accounts (only after the founder's OK: it runs until stopped). Let the MCP rank by freshness and warmth; then re-score its results with step 5 below: the MCP's ranking orders the list, the PULL score decides who gets a message. Skip its `icp-scoring` skill: demographics aren't the score here. Say the cost and check the balance before more than one page of credits.

1. Signups: TalkToHumans doesn't hold your product's signups. Pull them from your product analytics or billing tool, then use `list_contacts` with `query` to find each one in your LinkedIn contacts.
2. Inbox and follow-ups: `list_conversations` with `conversation.reply_state` `waiting_for_my_reply` (its `reply-triage` skill), then `waiting_for_their_reply` with the last message over 14 days old, then `list_messages` on each. Skip vendors, investors and automated messages.
3. Warm: the "Engaged with me" view and `member.signals` in the last 30 days; engagers of borrowed-audience posts through `content-engagers`.

`get_activity_summary` gives the accept and reply rates for the quota.

**With anything else:** the same waterfall, with the tools the founder has: the product's analytics for signups, the inboxes read by hand or through a CRM, post analytics read at a human pace, web search for public threads, job boards and review sites read by hand, and a people database only for the capped cold test.

Check a tool's inputs before running it, and give the founder a cost estimate before any batch above a few dollars. Never scrape LinkedIn while logged in as the founder. When credits run out, stop and report.

Read the survivors in full: keep first-person evidence of the situation, not keyword matches, vendors, or people commenting a keyword to get a lead magnet.

## 5. Score and cut

**Follow-ups first.** The people from steps 1 and 2 aren't scored. Keep for each: the deal, the last touch date, their last words, why they fit the case study, the next step, and any date that matters (a trial end, an event). Buried replies first, then positive replies that never booked, then signups, then stalled deals.

Score everyone else by tier, with the playbook's "Scoring":

| Tier | What it takes | Goes to |
|---|---|---|
| **A · direct** | One direct signal from the person | Outreach |
| **B · corroborated** | Two indirect signals that agree (a job ad and a founder posting about the Project; a competitor complaint and a fitting profile; a comment on a competitor's post and a visible need) | Outreach |
| **C · single** | One indirect or inferable signal | Watch list, re-checked monthly |
| **Cold** | No signal | The capped test (20 a week) |

Urgency ranks within a tier. Any signal beats no signal: never send cold while a tier A or B lead waits. Keep for each: company, link, **found via** (signups, inbox, warm, the recipe's name, or cold), each signal with its date and link, the tier, and the "could answer this week because…" sentence.

## 6. Hand back, in the chat

**No file.** Don't write a lead-list file. The list lives in the chat, and once approved, on the contacts in the outreach tool (tag, signals, notes), or in the CSV outbound-setup writes when there's no tool. The only write is the playbook recipe after the founder's yes.

The founder reads this on a screen, fast. Structure over sentences: no paragraphs, every quote 10 words or fewer, every number with its unit, icons always next to a label (never color alone). Always this layout, in this order:

1. **Headline**, one line: `Week of {date} · {case study version} · {n} people · expected {m} of {target} meetings · short {gap}`.
2. **Visual 1 · the quota.** One meter per source (follow-ups, signups, posts, cold): expected meetings against the target, with the rate it used and its sample size. Beside it: connection requests planned against the weekly cap.
3. **Visual 2 · the waterfall.** One bar per step and per recipe: looked at, kept, and the main cut reason in 5 words or fewer. Tool costs at the end. When the quota isn't met, the gap in meetings, not more cold.
4. **The people, one card or row each, in blocks with a header:** Reply first · Yes, not booked · Signups · Stalled and fit · Tier A · Tier B · Cold (capped). This order is the review order: with TalkToHumans, outbound-setup numbers the contacts in it, so the review view lists them the same way. Each shows:
   - name (linked) and company;
   - the tier and signals as blocks, not prose: `◆` per direct signal, `▲` per indirect signal, `⚡` urgency, `♨` warm (`◆ ⚡ · A`, `▲▲ · B`);
   - found via (the recipe), and the reason to talk this week, in 10 words or fewer;
   - their last words, 10 words or fewer (follow-ups only);
   - the next step, 6 words or fewer;
   - the date that matters, with a ⏰.
5. **Watch list**: one line of names with their score. **Out**: one line of counts per reason.
6. **What I'd change in sourcing**, at most 3 bullets, only when the run taught something.
7. **One question:** approve the list, with any cuts?

How to show it: when the agent can render visuals inline (a widget or chart tool), put items 1 to 5 in one visual, as large as it needs to be: meters, bars and a card per person, grouped by block. Then keep the chat reply to items 6 and 7. Otherwise (a terminal), show the meters and bars as text bars in a code block, and the people as one table per block.

- Save the recipe that worked (tool, query, filters, cost) in the case study's section of `outbound/playbook.md`, after the founder's yes.
- **Then draft, in the same session.** As soon as the founder approves the list (with any cuts), run [outbound-setup](../outbound-setup/SKILL.md) on the approved rows. Don't stop to offer it, and pass on what this run already read so it isn't read again. Signups and follow-ups get a personal note there, not a sequence: its only job is to get them on a call by asking what changed in their situation, never to pitch. Approving the list is the founder's one stop before the drafts; nothing is sent.
