---
name: reddit-rules-checker
description: "Checks a Reddit post or comment draft against a specific subreddit's rules, sidebar, wiki, flair requirements and Reddit's own sitewide norms before you post. Returns a pass, a fix-list or a stop, with each rule quoted, the exact line in your draft that breaks it, and a corrected version. Flags self-promotion, links, title formats, banned topics, entry requirements and likely automod triggers. Use this skill whenever the user says things like \"check this against the subreddit rules\", \"will this get removed\", \"is this allowed on r/...\", \"why was my Reddit post removed\", \"can I post a link here\", \"is this self-promotion\". Not for writing the post from scratch (use reddit-post-writer)."
metadata:
  author: Mr V
  version: "1.0"
  group: Reddit
---

# Reddit Rules Checker

You paste your draft and the subreddit's rules. It hands back a verdict (Pass / Fix / Stop), each problem tied to the exact rule it breaks, and a corrected draft.

---

## The core discovery: most removals are about the rule you didn't read

People think Reddit removals are random. Usually they're not. They come from a rule in the sidebar, a line in the wiki, a flair requirement, a title format or an automated filter (AutoModerator) that quietly removed the post before any human saw it.

Every subreddit is its own country with its own laws. The draft that's welcome in one is a ban in the next.

**Unchecked:** a helpful post in r/Entrepreneur with your landing page link at the bottom. Removed in minutes. No explanation.
**Checked:** the rules say links only in the weekly "Share your startup" thread and posts need a flair. The post goes up without the link, with the right flair, and the link goes in the weekly thread.

Checking takes five minutes. A ban lasts much longer.

---

## Intake

1. **The draft:** title + body, or the comment.
2. **The subreddit.**
3. **The rules.** Paste the sidebar rules, and the wiki if it has posting guidelines. If Claude can browse, read them directly from the subreddit's About/Rules page and wiki. Old.reddit.com/r/[sub]/about/rules is often easier to read.
4. **Your account:** age and karma (some subreddits silently filter new or low-karma accounts).
5. **Your connection** to anything linked or mentioned.
6. **If it was already removed:** the removal message, if any.

Rules change. Always check the current rules on the day you post, and say when they were read.

---

## The check (run every item)

### A. Subreddit rules
For every numbered rule, mark: Applies + passes / Applies + fails / Doesn't apply.

### B. Common hidden requirements
| Check | Look for |
|---|---|
| Flair | Is a flair required? Which one fits? |
| Title format | Required tags like [Question], [Discussion], minimum length, no all-caps |
| Links | Banned entirely? Only certain domains? Only in specific threads? |
| Self-promotion | Banned? Weekly thread only? Ratio rules? |
| Surveys / market research | Often banned or need mod approval |
| Repeat topics | "Search before posting" or a megathread for common questions |
| Post type | Text only? Images banned? |
| Entry bar | Minimum account age or karma (often unstated; watch for comments mentioning it) |
| Days | Promotion or certain topics only on set days |

### C. Reddit-wide norms
- Reddit's content policy and its guidance against spam.
- Self-promotion should be a minority of your activity. Accounts that mostly promote get flagged.
- No vote manipulation (asking friends to upvote, using multiple accounts).
- No posting the same content across many subreddits at once.
- Disclose your connection to anything you promote.

### D. Likely automod triggers
- Link shorteners (bit.ly, etc.)
- Certain domains (many subs block specific sites)
- Words like "DM me", "check my profile", "link in bio"
- Brand-new account + link

---

## Verdicts

| Verdict | Means |
|---|---|
| **Pass** | No rule broken. Post as is. |
| **Fix** | One or more rules broken but fixable. Corrected draft provided. |
| **Stop** | The core of the post is banned here (a pure promo in a no-promo sub, a survey where surveys are banned). Don't post. Suggest an alternative subreddit or format. |

---

## Rules

1. **Quote the rule.** Every problem cites the rule word for word, with its number.
   - Bad → "This might be too promotional."
   - Good → "Rule 3: 'No self-promotion outside the weekly thread.' Your line 'Grab the template here: [link]' breaks it."
2. **Point to the exact line in the draft.**
3. **Fix with the smallest change.** Keep the user's voice and value.
4. **When unsure, say so and suggest asking the mods.** Message the mods via modmail before posting a borderline post. Draft the modmail.
5. **Never suggest evading rules.** No disguising links, spelling domains oddly, using alt accounts or posting and deleting.
6. **Date the check.** Rules read on [date].

---

## Worked example

**Input:** r/Entrepreneur draft. Title: "How I got my first 50 customers for my SaaS 🚀". Body: lessons + "Try it free: bit.ly/xyz". Account: 2 months old, 80 karma.

**Rules (pasted, excerpt):** 1. No self-promotion outside the "Thank you Thursday" thread. 2. No link shorteners. 3. Use the correct flair.

**Verdict: Fix**
| # | Rule | Draft line | Problem | Fix |
|---|---|---|---|---|
| 1 | "No self-promotion outside the Thank you Thursday thread." | "Try it free: bit.ly/xyz" | Promo link in a regular post | Remove. Post the link in Thursday's thread. |
| 2 | "No link shorteners." | bit.ly/xyz | Automod will likely remove | Covered by fix 1. |
| 3 | "Use the correct flair." | No flair | Missing | Choose the lessons/how-to flair. |
| — | Reddit norm | Account 2 months, 80 karma | May be filtered by automod on some subs | Consider commenting more first, or ask mods. |
| — | Style | 🚀 in title | Not a rule, but reads promotional | Remove. |

**Corrected title:** "How I got my first 50 customers for a B2B SaaS (no ads, 4 months)"

---

## Output format

```
## Rules check: r/[sub]
Rules read on: [date]   Source: [sidebar / wiki / pasted]
Verdict: [Pass / Fix / Stop]

| # | Rule (quoted) | Draft line | Problem | Fix |

Reddit-wide: [ ]
Automod risks: [ ]
Corrected draft: [ ]
Modmail draft (if borderline): [ ]
Alternative (if Stop): [ ]
```

---

## Sibling skills

- `reddit-post-writer`: rewrite from scratch if the fix list is long.
- `reddit-comment-drafter`: comments, which have their own rules (check them too).
- `subreddit-finder`: find a better-fit subreddit after a Stop.
- `reddit-ama-planner`: AMAs usually need mod approval. Check here first.

---

## Pre-flight checklist

- [ ] Rules read on today's date, source stated.
- [ ] Every rule marked applies/passes/fails.
- [ ] Hidden requirements and automod risks checked.
- [ ] Every problem quotes the rule and the draft line.
- [ ] Fixes are minimal. No evasion tactics.
- [ ] Verdict given. Corrected draft or alternative provided.
