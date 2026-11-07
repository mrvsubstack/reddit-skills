---
name: reddit-audience-insights
description: "Mines Reddit threads for what your audience actually says: their pains, desired outcomes, objections, failed solutions, the exact words they use and the questions they keep asking. Collects threads from chosen subreddits (by browsing or from what you paste), codes every relevant comment, counts how often each theme appears, and hands back a voice-of-customer report with real quotes, ready for copy, offers and content. Use this skill whenever the user says things like \"what are people saying about X on Reddit\", \"mine Reddit for customer pain points\", \"find objections to my offer on Reddit\", \"voice of customer research\", \"what language does my audience use\", \"Reddit market research\". Not for finding which subreddits to look in (use subreddit-finder) or writing posts (use reddit-post-writer)."
metadata:
  author: Mr V
  version: "1.0"
  group: Reddit
---

# Reddit Audience Insights

You tell it who your audience is and what you want to learn. It collects real Reddit threads, codes what people say and hands back a report: top pains, desires, objections and the exact phrases people use, each backed by real quotes and counts.

---

## The core discovery: Reddit is the only place people describe their problems without performing

On LinkedIn people perform success. On Instagram they perform a lifestyle. On Reddit, often anonymously, they say the embarrassing part out loud. "I've started my newsletter four times and quit every time at issue 6." "I hate selling. I'd rather undercharge than send a follow-up email."

That's the raw material of every good headline, offer and post. Not your guess at what they feel. Their words.

**Marketer's guess:** "Struggling with content consistency?"
**Reddit's words:** "I keep starting and quitting at issue 6."

The second is what the reader recognises as their own thought. Use it.

---

## Intake

1. **Audience** in one line.
2. **Research question:** pains? objections to a price? what they've already tried? how they talk about a competitor?
3. **Subreddits** to search (or run `subreddit-finder` first).
4. **Seed phrases:** 5 to 10 ways people might describe the problem.
5. **Time window:** last year by default (older threads may be out of date).
6. **Your offer**, if you want objections mapped to it.

---

## Step 1: Collect threads

If Claude can browse or search the web:
- Search Google with `site:reddit.com/r/[sub] "[phrase]"` for each seed phrase.
- Search within each subreddit for the phrases, sorted by top and by relevance.
- Open 15 to 30 threads with real discussion (10+ comments).

If not, give the user the same searches and ask them to paste threads (post + comments).

Record for every thread: subreddit, title, date, link, comment count. Never invent a thread or quote.

---

## Step 2: Code every relevant comment

Tag each relevant sentence with one or more codes:

| Code | Means | Sounds like |
|---|---|---|
| PAIN | A problem or frustration | "I keep...", "I hate...", "I'm stuck..." |
| DESIRE | The outcome they want | "I just want...", "I wish..." |
| TRIED | A solution they already tried | "I tried X and..." |
| OBJECTION | A reason not to buy or act | "too expensive", "don't trust", "no time" |
| TRIGGER | The moment they went looking for help | "When my boss...", "After I lost..." |
| LANGUAGE | A vivid phrase worth reusing | Any memorable wording |
| QUESTION | A question that keeps coming up | "How do you...?" |

---

## Step 3: Count and rank

Group similar coded items into themes. For each theme, count:
- **Mentions:** how many comments raised it.
- **Threads:** how many separate threads it appeared in (one loud thread shouldn't dominate).
- **Intensity:** high (emotional, urgent), medium, low.

Rank themes by threads first, then mentions. A theme in 12 threads matters more than a theme mentioned 30 times in one.

---

## Step 4: Turn insights into uses

| Insight | Use it for |
|---|---|
| Top pains in their words | Headlines, hooks, post openers |
| Desires | Offer promises, outcomes on sales pages |
| Tried + failed | "Why this is different" sections |
| Objections | FAQ, guarantees, pricing decisions |
| Triggers | Ad and content timing, email sequence starts |
| Repeated questions | Posts, videos, lead magnets |

---

## Rules

1. **Every claim has a quote.** No theme without at least two real quotes with links.
2. **Counts, not vibes.** "Came up in 9 of 22 threads" beats "people often say".
3. **Quote exactly.** Don't clean up grammar in the quote. That's the point.
4. **Protect people.** Don't include usernames in reports meant for public use. Don't reproduce personal details. Paraphrase anything sensitive.
5. **Separate signal from noise.** Note when a theme comes from one angry thread.
6. **Date everything.** Reddit opinions shift. Mark the window searched.
7. **Never invent or composite a quote.** If you only have a paraphrase, label it as one.
8. **Respect Reddit's terms.** Read and summarise threads for research. Don't build large scraped datasets of user content. Check Reddit's current user agreement if the user plans to collect at scale.

---

## Worked example

**Input:** Audience: people who started a newsletter and stalled. Question: why they quit. Subs: r/Substack, r/Newsletters, r/blogging. Window: last 12 months.

**Collected:** 22 threads, 340 comments, 118 coded.

**Top themes (excerpt):**
| Theme | Code | Threads | Mentions | Intensity | Quote examples |
|---|---|---|---|---|---|
| Writing into silence | PAIN | 14 | 31 | High | "It feels like I'm writing to nobody" / "6 issues, 11 subs, 9 are family" |
| Running out of ideas | PAIN | 9 | 17 | Medium | "By issue 5 I had nothing left to say" |
| Growth tactics feel spammy | OBJECTION | 7 | 12 | High | "I'd rather quit than spam every group I'm in" |
| Tried posting on X | TRIED | 6 | 9 | Low | "Tweeted every issue, got zero clicks" |

**Language to reuse:** "writing to nobody", "issue 6 wall", "I'd rather quit than spam".

**Implications:** a lead magnet on getting the first 100 readers *without* spamming; an opening hook built on "writing to nobody"; an FAQ answering "do I have to self-promote constantly?".

(Every number and quote above must come from real threads. This table shows the format.)

---

## Output format

```
## Reddit insights: [audience] — [question]
Window: [ ]   Subreddits: [ ]   Threads: [n]   Comments coded: [n]

### Top themes
| Theme | Code | Threads | Mentions | Intensity | Quotes (with links) |

### Language bank
[exact phrases]

### Repeated questions
[list]

### What this means
- Hooks: [ ]
- Offer: [ ]
- Objections to handle: [ ]
- Content ideas: [ ]

### Sources
[thread title — sub — date — link]
```

---

## Sibling skills

- `subreddit-finder`: choose where to look.
- `reddit-post-writer`: answer the top repeated questions in a post.
- `reddit-comment-drafter`: reply to threads you found along the way.
- `reddit-ama-planner`: use the question list as an AMA answer bank.
- `audience-research-analyst` and `customer-persona` (in this library): turn these insights into a full persona.

---

## Pre-flight checklist

- [ ] Research question stated.
- [ ] 15+ real threads with links and dates.
- [ ] Every theme counted by threads and mentions.
- [ ] Every theme backed by at least two exact quotes.
- [ ] No usernames or personal details in shareable output.
- [ ] Insights mapped to uses.
- [ ] Nothing invented or composited.
