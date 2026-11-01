---
name: lead-gen
description: Turn the current case study in gtm/case-study.md into public need and urgency signals, find people and companies showing them recently, score them, and return a short list for the founder to approve. Use for "find leads", "who should I contact this week", "source people for my case study", or when the weekly review's move needs a new batch.
---

# Lead gen

Find people who are in the case study's situation **right now**, from what that situation leaves behind in public. Signals decide who and when; the message and the call do the rest.

Follow the rules in [outbound/playbook.md](../../../outbound/playbook.md). The short version: start from the case study, pair every need signal with an urgency signal, wide in and 90 to 99% out, by hand before automating.

## 1. Read the case study

Read the current version in `gtm/case-study.md`: who, the PULL sentence, P, U, L+L, and the proof. Read the `gtm/sales.md` entries of the buyers who pulled: their own words are the best source of search terms. Read the case study's section in `outbound/playbook.md` if one exists, and the "angles tried" in `gtm/pipeline.md`.

If the founder asks for leads for a different situation than the current version, say so and ask whether to test it as a separate sprint.

## 2. Write the signals

If the playbook has no signals table for the current version yet, draft one and show it to the founder before searching:

- **Need** (+2 each): they're doing the Project, or the option they use is failing them. Use the words buyers used.
- **Urgency** (+3 each): the U in the case study happened in the last 30 to 60 days. Older counts 0.
- **Out:** competitors, people who sell the same thing as a service, anyone the evidence says isn't the buyer.

Ask AI Rob whether these signals match the situation, if it's loaded for this session.

## 3. Find them

Pick the cheapest source that shows the signal (see "Where signals live" in the playbook):

- **TalkToHumans MCP:** load its `ground-rules` skill, then its lead-search skill, and use it first. It also shows people already in the founder's network who match.
- **Another scraping tool the founder connected:** post search, post comments, job ads, review sites, website change checks. Check its inputs before running it, and give the founder a cost estimate before any batch above a few dollars.
- **Web search:** threads, reviews, news, company pages.

Never scrape LinkedIn while logged in as the founder.

Start with 20 to 50 candidates for a new recipe. Read the survivors in full: keep first-person evidence of the situation, not keyword matches or people commenting a keyword to get a lead magnet.

## 4. Score and cut

Score with the playbook's rules. 7 or more goes on the list, 4 to 6 to a watch list, the rest out. For each person on the list:

| Name | Company | Link | Signals (with dates and links) | Score |
|---|---|---|---|---|

## 5. Hand back

- Show the list and the watch list. Say how many candidates you looked at, how many were cut, and why.
- Save the recipe that worked (tool, query, filters, cost) in the case study's section of `outbound/playbook.md`, after the founder's yes.
- Interesting public posts or reviews that aren't leads go to the situation's file in `evidence/`.
- Offer [outbound-setup](../outbound-setup/SKILL.md) for the approved list. Don't import anything yourself.
