# PULL Lab

An AI company OS to find product-market fit systematically, built on Rob Snyder's [PULL framework](https://thephysicsofstartups.substack.com/p/the-pull-framework).

Built by Robin Labrot ([TalkToHumans](https://www.talktohumans.app/?utm_source=pull-lab&utm_medium=github&utm_campaign=readme)) on top of [AI Rob](https://airobsnyder.com), the AI version of Rob Snyder.

## What you get

If you're pre-PMF, you know the pain cave: lots of calls, lots of "wow, this is amazing", a few pilots, and nobody buys. Every Monday you're not sure what to work on, so you build another feature.

Pre-PMF, you don't need a GTM strategy. You need to find ONE customer who actually wants to buy, then another one just like them. This repo runs that loop with you, every week:

- **You know what to do on Monday.** Every Friday, AI Rob reads your week (who you messaged, what buyers said, who signed up, who paid) and names the one bottleneck, with a one-hour action for today. Everything else can wait.
- **You stop chasing fake demand.** Every call gets the same question: did they pull, or did they just say "this is amazing" (but not for them, not today)? Compliments, pilots and "send me more info" stop counting as progress.
- **You find who would be weird NOT to buy.** Your case study gets sharper every week, in your buyers' own words. Dead ends get closed with the evidence, so you don't reopen them a month later.
- **You walk into every call already knowing the person.** How you met, what they said last time, what they pay, how they use the product, and what to say next.
- **You talk to more of the right people.** Leads who are in that situation right now, and outreach drafted for you to review and send.
- **Your learning compounds.** It remembers what a buyer told you three months ago. Every week starts from what the last one proved, not from scratch.

Want to see it before you set it up? Read [the sample week](examples/honeypot/reviews/2026-10-17.md): a startup selling to bears, where the review catches a signup spike made of raccoons.

## How it works

### The weekly loop

```
            ┌──────────────────────────────────────────┐
            │  gtm/case-study.md                       │
            │  who has PULL, and every past version    │
            └──────────────────────────────────────────┘
   7. iterate ▲                                │ 1. case study
              │                                ▼
 6. /weekly-review                       2. /lead-gen
 AI Rob scores the week,                 find people showing the
 names ONE bottleneck                    situation in public
              ▲                                │
              │                                ▼
 5. /deal-review                         3. /outbound-setup
 one file per person: context,           import + draft a sequence,
 PULL, usage, AI Rob's review            you review and send
              ▲                                │
              └──────── 4. /call-prep ◄────────┘
                  prep with AI Rob, record,
                  debrief into a PULL sheet
```

1. **Case study.** The one situation you're trying to serve, written as PULL in `gtm/case-study.md`. It starts as a guess and gets sharper every week.
2. **Leads.** `/lead-gen` turns the case study into public signals and finds people showing them recently.
3. **Outreach.** `/outbound-setup` imports the list and drafts a short sequence. You review and send every message.
4. **Calls.** `/call-prep` builds a one-screen call script with AI Rob, updates it live as you paste the transcript, and debriefs.
5. **Memory.** `/deal-review` keeps one file per person in `deals/`: context, PULL, what they pay and use, a timeline, and AI Rob's dated deal reviews. Every call is also logged in `gtm/sales.md`.
6. **Review.** `/weekly-review`, every Friday: outreach, calls, deals, activation and revenue go to AI Rob, which scores the week and names the one bottleneck.
7. **Iterate.** Fix the bottleneck, update the case study, repeat.

### What you need

| Slot | Why | Required? | What I use | Also works |
|---|---|---|---|---|
| Agent | Runs the skills, reads your tools and keeps the files up to date | Yes | [Claude Code](https://claude.com/claude-code) or Claude Cowork | Codex, Cursor (they read `AGENTS.md`) |
| PULL brain | Judges every call and every week against the PULL framework: is there a real Project, can it wait, which options fail and why | Yes | [AI Rob](https://airobsnyder.com), delivered through the Skillfully MCP | — |
| Lead sourcing | Find people showing your case study's situation in public, right now | Optional | [TalkToHumans](https://www.talktohumans.app/?utm_source=pull-lab&utm_medium=github&utm_campaign=readme) MCP | Any web search tool |
| LinkedIn outreach | Import leads, draft sequences, and see who accepted, replied and booked, per outreach angle | Optional | [TalkToHumans](https://www.talktohumans.app/?utm_source=pull-lab&utm_medium=github&utm_campaign=readme) MCP | A CSV and sending by hand |
| Call recording | Keep buyers' exact words. They're the evidence, and your memory of a call isn't | Optional | Granola MCP | Fathom, Fireflies, any transcript you paste |
| Billing | See who actually paid, trialed or churned. Only a purchase proves PULL | Optional | Stripe MCP | Paste your numbers |
| Product analytics | Understand signups, activation and retention, and what's actively used or not | Optional | Mixpanel MCP | PostHog MCP |

Every skill runs without the optional tools. It asks you for what it can't fetch and says so in the review.

### What's inside

```
pull-lab/
├── AGENTS.md              # instructions for your agent (CLAUDE.md imports it)
├── context/               # company, founders, product: read before every task
├── gtm/                   # AI Rob's memory: case study, pipeline, sales log, sales process, post-sales
├── deals/                 # one file per person: context, PULL, account, timeline, AI Rob's reviews
├── evidence/              # public signals (posts, reviews, job ads) per buyer situation
├── outbound/              # signals and sourcing recipes
├── reviews/               # one weekly review per Friday
├── .claude/skills/        # weekly-review, call-prep, deal-review, lead-gen, outbound-setup
└── examples/honeypot/     # a complete sample week for a fictional startup. Delete when ready.
```

## Get started

### Set up (once)

1. **Fork it, privately.** Click **Use this template** → **Create a new repository** → **Private**. A regular fork of a public repo stays public, and your copy will hold your customers' words.
2. **Clone it locally.**
   ```bash
   git clone git@github.com:<you>/pull-lab.git
   ```
3. **Open the folder as a project** in Claude Code or Claude Cowork (or Codex, if that's what you use).
4. **Connect the tools.** AI Rob first ([airobsnyder.com](https://airobsnyder.com)), then the MCPs from [What you need](#what-you-need) that you don't have yet.
5. **Fill in `context/`.** Ask your agent: *"Help me fill in context/"*. It will ask what you sell, your stage and your one goal with a date.
6. **Run a first weekly review.** Say *"run my weekly review"*. AI Rob sets up its memory in `gtm/` and `deals/`, loads what your tools already know (past calls, customers, signups, revenue), helps you write the first version of your case study, and names where to start. Want to see a finished week first? Say *"Run /weekly-review on examples/honeypot as a demo."*

### Then, every week

7. **Find leads.** *"Find leads"* (`/lead-gen`).
8. **Start outreach.** *"Launch outreach for this list"* (`/outbound-setup`). You review and send.
9. **Have calls, and record them.** *"Prep my call with Jane"* before (`/call-prep`), *"review this call"* after, and after every reply or email too (`/deal-review`).
10. **Next Friday, run the weekly review.** Apply the changes you agree with, and iterate on the bottleneck it names.
11. **Find product-market fit,** after many iterations.

## Credits

The PULL framework is by [Rob Snyder](https://thephysicsofstartups.substack.com) ([The Physics of Startups](https://thephysicsofstartups.substack.com)).

Issues and PRs welcome.
