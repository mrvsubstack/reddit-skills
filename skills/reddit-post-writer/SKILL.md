---
name: reddit-post-writer
description: "Writes value-first Reddit posts in the style of a specific subreddit: reads the community's top posts and rules first, picks a post type that fits (detailed how-to, lessons learned, honest breakdown, question, resource share), writes a plain title and a body that gives the whole value in the post itself, and handles any mention of your product the way that community tolerates. Use this skill whenever the user says things like \"write a Reddit post\", \"post this on r/...\", \"how do I share my project on Reddit without getting banned\", \"Reddit post about my experience\", \"make this sound like a Redditor\", \"turn my blog post into a Reddit post\". Not for comments and replies (use reddit-comment-drafter) or checking rules (use reddit-rules-checker)."
metadata:
  author: Mr V
  version: "1.0"
  group: Reddit
---

# Reddit Post Writer

You give it the subreddit, what you want to share and what you'd like to get out of it. It reads (or asks you to paste) what works in that community, then hands back a title and body written the way that subreddit writes, with the value fully inside the post.

---

## The core discovery: Reddit pays you for what you give away in the post

On most platforms, a post is a trailer for something elsewhere. On Reddit, that gets you downvoted, reported or banned. Redditors can smell a funnel from the title.

What works is the opposite: put the whole value in the post. The full process, the actual numbers, the real lessons. No "DM me for the rest". No "link in comments for the guide".

**Funnel post:** "I grew my newsletter to 10K. Here's my free guide → [link]"
**Reddit post:** "I grew a newsletter from 0 to 10K in 14 months. Here's everything that worked, what flopped, and the numbers." Then 600 words of exactly that.

The second earns upvotes, saves and comments. And some readers click your profile, find your link and become subscribers. The value is the marketing.

---

## Intake

1. **The subreddit.** One post per subreddit. Never cross-post the same text everywhere.
2. **The subreddit's rules** (paste them or let Claude read them) and 5 to 10 top posts from the past month.
3. **What you're sharing:** experience, lessons, a guide, a question, a resource, a project.
4. **Your real details:** numbers, timeline, mistakes, tools. Never invented.
5. **Goal:** feedback, discussion, reputation, traffic.
6. **Your relationship to anything you mention** (founder, employee, affiliate).

---

## Step 1: Read the room

From the top posts, note:
- **Title style:** plain or punchy? Questions? Brackets like [Guide] or flair?
- **Length:** quick questions or long breakdowns?
- **Tone:** technical, supportive, blunt, funny?
- **Formatting:** headers, bullet lists, TL;DRs?
- **What gets removed:** check rules and the mod-removed patterns in comments.

Write the post to look like it belongs among those.

---

## The five post types

| Code | Type | Works for | Shape |
|---|---|---|---|
| R1 | Detailed How-To | Teaching a process | Context → steps → pitfalls → results |
| R2 | Lessons Learned | Experience posts | What I did → what worked → what didn't → what I'd do now |
| R3 | Honest Breakdown | Numbers, revenue, experiments | The numbers → how → what surprised me |
| R4 | Real Question | Getting feedback, starting discussion | Context → specific question → what I've tried |
| R5 | Resource Share | Free tools, templates, lists | What it is → why I made it → how to use it → limits |

---

## Rules

1. **Value lives in the post.**
   - Bad → "Comment 'GUIDE' and I'll DM it."
   - Good → the full guide, in the post.
2. **Plain, specific titles.** Reddit hates clickbait.
   - Bad → "This ONE trick changed my business forever 🚀"
   - Good → "I tracked every hour of my freelance week for 3 months. Admin ate 31%."
3. **Write like a person, not a brand.** First person, plain words, admit what went wrong. No marketing adjectives. No "we're excited to share".
4. **Include the failures.** Posts that only show wins read as ads. The mistakes are often the most upvoted part.
5. **Follow the subreddit's link and self-promo rules exactly.** If links are banned, no link. If promo has a weekly thread, it goes there.
6. **Disclose your connection.** If you mention something you made or profit from, say so plainly ("I built this, so I'm biased").
7. **TL;DR for long posts**, at the top or bottom depending on the subreddit's habit.
8. **End with a real question** that invites people's experience, not "thoughts?".
9. **Never invent numbers, stories or testimonials.** Reddit fact-checks in the comments.
10. **Plan to stay.** Reply to comments for the first few hours. A post you abandon looks like a drive-by.

---

## Steps

1. Intake and read the room.
2. Run `reddit-rules-checker` logic on the plan (or the skill itself if needed).
3. Pick a post type.
4. Write 3 title options in the subreddit's style.
5. Write the body.
6. Add disclosure and handle any link per the rules.
7. Suggest the first 2 to 3 replies to likely questions, so the user is ready.

---

## Worked example

**Input:** r/freelance. User is a designer who started requiring 50% deposits. Real data: late payments went from 6 of 20 clients to 1 of 18 over 6 months. Sells a contract template but r/freelance bans self-promo.

**Titles:**
1. "I started asking for 50% upfront. Late payments went from 6 in 20 clients to 1 in 18."
2. "6 months of requiring deposits: what changed and what I lost"
3. "Deposits fixed my late-payment problem. Here's how I brought it up without losing clients"

**Body (excerpt, R2 Lessons Learned):**
```
For two years I invoiced on completion. Out of 20 clients last year, 6 paid late and one never paid.

In March I switched to 50% upfront for every new project. Here's what happened over 6 months.

**What worked**
- Putting it in the proposal, not the invoice. Nobody pushed back when it was there from the start.
- Saying why in one line: "The deposit books your slot in my calendar."

**What didn't**
- Two prospects walked. Both had haggled on price already, so in hindsight, fine.
- I tried it with an existing client mid-project. Bad idea. Only do this for new work.

**Numbers**
18 new clients since March. 1 paid the second half late (by 9 days).

TL;DR: 50% upfront, in the proposal, with a one-line reason. Late payments almost disappeared.

For those who already do deposits: do you go 50/50 or split it into milestones?
```
No link, no template mention, per r/freelance rules. The user's profile can carry their site.

---

## Output format

```
## Reddit post for r/[sub]
Room read: [title style, length, tone, formatting]
Rules that apply: [links / promo / flair / format]

Titles:
1. [ ]
2. [ ]
3. [ ]

Body:
[post]

Flair: [ ]
Disclosure: [included / not needed]
Ready replies: [likely question → short answer]
```

---

## Sibling skills

- `reddit-postiz-publisher` — schedule the finished post through Postiz after you approve it.
- `subreddit-finder`: find the right subreddit first.
- `reddit-rules-checker`: final check before posting.
- `reddit-comment-drafter`: replies on your post and comments elsewhere.
- `reddit-audience-insights`: find which questions to answer in a post.
- `reddit-ama-planner`: when the post should be an AMA.

---

## Pre-flight checklist

- [ ] Written for one subreddit, matching its style.
- [ ] All value inside the post. No funnel.
- [ ] Plain, specific title. No clickbait.
- [ ] Failures included. Numbers real.
- [ ] Link and promo rules followed. Connection disclosed.
- [ ] Ends with a real question.
- [ ] User ready to reply for the first few hours.
