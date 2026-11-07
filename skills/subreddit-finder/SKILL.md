---
name: subreddit-finder
description: "Finds the subreddits where your buyers actually talk, then sorts them by fit, activity and how open they are to someone like you: a shortlist of 5 to 15 subreddits, each with size and activity signals, the kind of posts that do well, self-promotion rules, entry requirements and a role for you (answer, post, listen only). Use this skill whenever the user says things like \"which subreddits should I post in\", \"find subreddits for my niche\", \"where are my customers on Reddit\", \"best subreddits to promote my product\", \"Reddit communities for my audience\", \"is this subreddit worth it\". Not for writing posts (use reddit-post-writer) or mining what people say (use reddit-audience-insights)."
metadata:
  author: Mr V
  version: "1.0"
  group: Reddit
---

# Subreddit Finder

You describe your buyer and what you offer. It hands back a scored shortlist of subreddits, each with what it's like inside, what it allows and the role you should play there.

---

## The core discovery: buyers hang out where the problem lives, not where the product lives

The obvious subreddit is usually the wrong one. A newsletter tool founder heads to r/newsletters. So does every other newsletter tool founder. The mods are tired, the members are wary, and every post smells like a pitch.

The buyers are elsewhere: in the communities where the **problem** gets talked about. Freelance writers complaining about inconsistent income. Small business owners asking how to keep customers coming back. Teachers asking how to share resources with parents.

**Product-shaped search:** "email marketing subreddit"
**Problem-shaped search:** "how do I get repeat customers", "freelance income dry spell", "keep in touch with clients"

Search by the problem. That's where the conversations, and the buyers, are.

---

## Intake

1. **Your buyer:** who they are, their job or situation, what they struggle with.
2. **Your offer:** product, service, content or community.
3. **Goal on Reddit:** research only, build reputation, drive traffic, or recruit beta users.
4. **Your Reddit account:** age and rough karma (many subreddits block new or low-karma accounts).
5. **Subreddits you already know of.**

---

## Step 1: Generate candidates

Use web search if available. Otherwise give the user these searches to run and paste results from.

1. **Problem searches:** search Google for `site:reddit.com "[problem phrase]"` with 5 to 10 phrasings of the buyer's pain. Note which subreddits keep showing up.
2. **Reddit search:** search the problem phrases on Reddit itself, filtered to communities.
3. **Neighbour mining:** open each good candidate's sidebar or "related communities" list.
4. **Role-based subs:** the buyer's profession or identity (r/freelance, r/smallbusiness, r/Teachers).
5. **Tool and hobby subs:** the tools and activities the buyer already uses.

Aim for 20 to 30 candidates before filtering.

---

## Step 2: Score each candidate

For each, open the subreddit (or ask the user to) and check:

| Factor | What to look at | Score 1–3 |
|---|---|---|
| Buyer fit | Do posters match your buyer? Read 20 recent post titles. | |
| Problem density | How often does your problem come up? | |
| Activity | Posts and comments in the last week (not just member count). | |
| Openness | Rules on self-promotion, links, surveys. Mod tone. | |
| Entry bar | Account age, karma, flair or approval requirements. | |

Member counts mislead. A 40,000-member subreddit with 30 active posts a day beats a 2 million member one that's dead or drowning in memes. Record what you saw and when. Never invent member counts or activity numbers.

---

## Step 3: Assign a role

| Role | When | What you do |
|---|---|---|
| Listen | High fit, strict no-promo | Read only. Mine language with `reddit-audience-insights`. |
| Answer | High fit, comments welcome | Help in comments. Profile does the selling. |
| Post | High fit, value posts welcome | Share genuinely useful posts with `reddit-post-writer`. |
| Promote | Explicit promo threads or rules allow it | Use only the allowed threads or days. |
| Skip | Low fit or hostile | Don't bother. |

---

## Rules

1. **Problem first, product second** in every search.
2. **Activity over size.** Count recent posts and comments, not members.
3. **Read the rules and the sidebar before scoring openness.** Many subreddits ban links, self-promotion or surveys outright, or only allow them in a weekly thread.
4. **Respect entry bars.** If an account is too new or has too little karma, the plan starts with commenting in easier subreddits to build history. Never suggest buying accounts or karma.
5. **Read the room.** Note the tone: supportive, technical, sarcastic, beginner-friendly. It shapes everything you write there.
6. **Never fabricate stats.** Mark anything not seen first-hand.
7. **Reddit's own norms apply everywhere.** Reddit's guidance discourages accounts that exist mainly to self-promote. Most experienced redditors expect the large majority of your activity to be non-promotional.

---

## Worked example

**Input:** Selling a £29 Notion template for freelance designers to track clients and invoices. Account is 3 years old, 2,400 karma. Goal: reputation + some sales.

**Problem phrases searched:** "freelance client tracking", "forgot to invoice client", "how do you manage freelance projects", "late paying clients".

**Shortlist (excerpt — activity as seen by user on [date]):**
| Subreddit | Fit | Problem density | Activity | Openness | Entry | Role |
|---|---|---|---|---|---|---|
| r/freelance | 3 | 3 | 3 | 1 (no self-promo) | low | Answer |
| r/graphic_design | 3 | 2 | 3 | 1 (strict) | low | Listen + answer |
| r/Notion | 2 | 2 | 3 | 2 (templates allowed with rules) | low | Post |
| r/NotionTemplates | 2 | 1 | 2 | 3 (promo is the point) | low | Promote |
| r/smallbusiness | 1 | 2 | 3 | 1 | low | Skip |

**Plan:** answer client-tracking questions in r/freelance and r/graphic_design for 3 to 4 weeks; post a genuinely useful free version or walkthrough in r/Notion per its rules; list the paid template in r/NotionTemplates.

(Check each subreddit's current rules yourself. They change.)

---

## Output format

```
## Subreddit shortlist: [buyer]
Searched: [phrases]   Checked on: [date]

| Subreddit | Fit | Problem density | Activity (as seen) | Openness | Entry bar | Role | Notes |

### Top 3 to start with
1. [sub]: [why, what to do first]

### Account readiness
[ok / build history first in: ...]

Unverified: [anything not seen directly]
```

---

## Sibling skills

- `reddit-audience-insights`: mine the shortlisted subreddits for pains and language.
- `reddit-rules-checker`: check a draft against a subreddit's rules before posting.
- `reddit-post-writer`: write value-first posts for the "Post" subreddits.
- `reddit-comment-drafter`: write helpful comments for the "Answer" subreddits.
- `reddit-ama-planner`: when a subreddit is a fit for an AMA.

---

## Pre-flight checklist

- [ ] Searched by problem, not product.
- [ ] 20+ candidates before filtering.
- [ ] Every shortlisted subreddit scored on all five factors.
- [ ] Rules read for each, openness reflects them.
- [ ] Each has a role.
- [ ] Account readiness checked.
- [ ] No invented numbers. Check dates recorded.
