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

Go down this list, warmest first, and stop once you have 20 to 50 candidates for the recipe:

1. **People engaging with the founder's own content.** Who commented on their posts or viewed their profile in the last 30 days. They already know the founder. Keep the ones whose comment or profile shows the situation: an engagement alone isn't a need signal.
2. **People posting about the situation, and who comments on those posts.** Search posts from the last 30 days with the buyers' own words. Keep authors writing in the first person about the Project or a failing option, and commenters adding their own story.
3. **Cold, by company and role.** Only when 1 and 2 come up short. Qualify the company first (playbook rule 2), then find the person by role. Demographics aren't a signal: check each person's recent posts and company for a need or urgency signal before scoring, and say which leads are cold with no signal.

The other sources in "Where signals live" in the playbook (job ads, review sites, news, public threads) can feed any step.

**With the TalkToHumans MCP (recommended):** load its `ground-rules` skill and follow its credit rules: say the cost and check the balance before more than one page.

1. Own content: the "Engaged with me" contact view, and the engagers of the founder's recent posts (its `content-engagers` skill). Check when they last synced: if nothing is newer than 30 days, go to step 2.
2. Posts: `search_posts` with the buyers' words as keywords and `posted_within` `month`. Read the authors, then import the commenters of the best posts with `content-engagers`, after the founder's OK on its estimate.
3. Cold: `search_people`, following its `import-and-prep-list` skill, with `exclude` for competitors. Check a shortlisted person's recent posts with `find_content`.

Its searches run on credits, not on the founder's LinkedIn account. Skip its `icp-scoring` skill: the playbook's score decides here, not demographics.

**With anything else:** a scraping tool the founder connected (post search, post comments, job ads, review sites, website change checks) or web search (threads, reviews, news, company pages). Check a tool's inputs before running it, and give the founder a cost estimate before any batch above a few dollars. Never scrape LinkedIn while logged in as the founder.

Read the survivors in full: keep first-person evidence of the situation, not keyword matches, vendors, or people commenting a keyword to get a lead magnet.

## 4. Score and cut

Score with the playbook's rules. 7 or more goes on the list, 4 to 6 to a watch list, the rest out. For each person on the list:

| Name | Company | Link | Found via | Signals (with dates and links) | Score |
|---|---|---|---|---|---|

`Found via` is the step that found them (own content, posts, cold), so the weekly review can compare them.

## 5. Hand back

- Show the list and the watch list. Say how many candidates each step looked at, how many were cut, and why.
- Save the recipe that worked (tool, query, filters, cost) in the case study's section of `outbound/playbook.md`, after the founder's yes.
- Interesting public posts or reviews that aren't leads go to the situation's file in `evidence/`.
- Offer [outbound-setup](../outbound-setup/SKILL.md) for the approved list. Don't import the list or draft messages yourself.
