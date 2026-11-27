# Outbound playbook

How we find people in the case study's situation. The case study itself lives in [gtm/case-study.md](../gtm/README.md), and the weekly numbers and outreach angles in `gtm/pipeline.md`; refer to them here, don't copy them.

## Six rules

1. **Start from the case study, not a list.** Write the PULL statement first. Then ask: what would this situation leave behind in public? Those traces are your signals.
2. **Company first, people last.** Qualify the company (site, job ads, stack, team shape, reviews) before looking up the person.
3. **Skip the obvious signals, stack the quiet ones.** "Looking for a tool" posts are seen by every vendor. Three weak hints on the same company beat one loud one.
4. **Every lead needs a reason to talk now: one direct signal, or two signals that agree.** Direct: they're doing the Project now, in their own words or in your product. Two indirect signals (a job ad, a competitor complaint, a comment on a competitor's post, the company's shape) count only when they point at the same situation. Urgency (the case study's U in the last 30 to 60 days) ranks the list; it gates outreach only when the case study says so. One signal alone goes to a watch list.
5. **Wide in, 90 to 99% out.** Start with the biggest pool you can get, exclude fast with cheap checks, and give only the top few percent a human look.
6. **Manual before machine.** Run a new recipe by hand on 20 to 50 companies. Automate it only once it produced real conversations.

## Where signals live

The lead gen waterfall, warmest first, until the week's quota is met: signups and trials you haven't had a call with; then leads buried in your inbox and follow-ups owed; then people who engaged with your content or viewed your profile and fit the case study; then people posting about the situation and their commenters; then cold leads by role and company size. The quota comes from your funnel (contacted to first meeting, last 4 to 6 weeks in `gtm/pipeline.md`), capped by what your accounts can send in a week. How it's computed is in the [lead-gen skill](../.claude/skills/lead-gen/SKILL.md).

| Source | What to look for |
|---|---|
| Your own signups and trials | People who signed up in the last 60 days and never had a call, what they did in the product, and whether they fit the case study's Who |
| Your own inbox | Replies you never answered, positive replies never booked, deals gone quiet, trials ended with no card |
| Your own posts and profile | Who commented, reacted or viewed your profile lately, and what their comment or profile says about the situation |
| Job ads | Roles and tools named in the ad, and the need written in the description. Reach the founder or hiring manager, not the future hire |
| Company websites | New careers pages, new sales or partner pages, new scripts in the page source |
| Review sites (1 and 2 stars) and public complaints | Named reviewers leaving a competitor, with the reason; posts and comments saying a competitor broke or stalled |
| Competitors', influencers' and borrowed audiences' posts | People who comment (not just react) with their own situation; check they aren't the competitor's staff or fans |
| Public threads (Reddit, communities, LinkedIn comments) | Someone stuck on the exact Project, recently |
| Posts | First-person "here's what I tried" posts, and who comments with their own story |
| News | Events that create a deadline for a whole group at once |

## Checking a signal

Before a signal counts:

- **Fresh:** the last 30 to 60 days. Older is background.
- **Specific:** names the Project, the option or the role, not the topic in general.
- **The right actor:** the buyer, not a competitor's employee, a fan, a vendor or a recruiter.
- **Not one event repeated:** a funding post, a hiring post and a press article about the same news are one signal.
- **Still odd without a purchase:** would this behaviour make sense if they never bought anything? A job ad can be a replacement or a stale post; a funding round can precede cuts; event attendance proves no project.
- **Say only what the evidence shows:** the message may build on a fact (the ad, the post), never on a guess about their pain.

## Scoring (keep it dumb)

| Tier | What it takes | Goes to |
|---|---|---|
| A · direct | One direct signal from the person | Outreach |
| B · corroborated | Two indirect signals that agree | Outreach |
| C · single | One indirect or inferable signal | Watch list, re-checked monthly |
| Cold | No signal, found by role and company size | A capped test, at most 20 a week |

- Urgency ranks within a tier. Warm (commented on, reacted to or viewed your posts or profile in the last 30 days) also ranks, but isn't a signal on its own.
- Your own exclusions are out: competitors, people who sell the same thing as a service.
- Any signal beats no signal: never send cold while a tier A or B lead waits. When the week's quota isn't met, report the gap in meetings instead of filling it with cold. The weekly review compares each recipe and the cold test.

## Message and sequence (default)

Signals decide **who** and **when**. The message only earns the call: it needs a believable reason for this person to answer this week, and credibility amplifies that reason without replacing it. Don't quote a private or sensitive signal back at them ("saw your account got restricted"): it reads as surveillance. A public post or a job ad is fair to build on. Ask AI Rob for the outbound message, then keep it to one line that's interesting to them and a short ask.

**By signal:** warm or engager, start from the exchange or answer the public post; job ad, start from the hire and give something useful about it; competitor complaint, never mention the complaint, ask about the option in the follow-up; signup, what was going on the week they signed up. Give before you ask, inside the text. No direct meeting ask in the first message, no video or heavy asset before a yes.

1. Day 0: connection request, no note. Your profile is the landing page.
2. Day after accept: the message.
3. Two to three days later: an easy, factual question about the option they use now ("Btw, what are you using today for …?"). It gives them something to answer; a one-word bump doesn't.
4. Stop. On a positive reply, convert while it's warm: answer their context in a line or two, say what the call would cover, then ask whether they have a calendar you can book into, and offer a slot today, with your own link only as a fallback. No product dump. No booking after a day: a short nudge. Two days later, one last follow-up, then stop.

**Benchmarks per stage:** 30%+ of requests accepted (under 20% is a profile or list problem), 20%+ of accepted connections reply (under 5% is a message problem), 50%+ of replies qualified, and most qualified replies book a call. Count any reply, qualified reply, meeting, paid: a social "thanks" isn't qualified. Judge a copy test on qualified replies and meetings, never on acceptance (invites go without a note). Fix only the stage furthest below its benchmark.

## Do and avoid

General patterns, checked against real outbound. Keep your own dated evidence under each version block.

**Do:** lead with a public signal of the Project, not demographics; answer public posts about the exact problem the day they appear (the strongest move there is); ask every new signup what was going on the week they signed up; reply in old threads before sending new requests; send invites without a note to people likely to accept; ask for the meeting the same day someone shows interest.

**Avoid:** demographic lists with no signal; filling the quota with cold leads; generic "trigger + pain + CTA" copy; a direct meeting ask in the first message; product dumps after a positive reply; unsolicited videos; staged spontaneity or borrowed friendships; lead-magnet keyword commenters; judging a copy test on acceptance.

## Per case study version

<!-- Add a block when a new version of the case study gets sourcing. Keep the old blocks: they show which recipes worked for which version. -->

### v1 · <!-- short name, date -->

**Signals**

| Type | Signal | Notes |
|---|---|---|
| Direct | | |
| Indirect | | |
| Inferable | | never alone |
| Urgency | | ranks within a tier |
| Out | | |

**Recipes** (log each: looked at, kept, contacted, replies, qualified, meetings; verdict after about 50 leads)

| Recipe | Tool, query, filters, cost per batch | Status |
|---|---|---|
| | | |
