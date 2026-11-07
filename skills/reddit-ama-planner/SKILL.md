---
name: reddit-ama-planner
description: "Plans a Reddit AMA (Ask Me Anything) from first contact with moderators to the follow-up: picks the right subreddit, drafts the mod pitch, prepares proof of identity, writes the title and intro post, builds an answer bank for likely and hard questions, sets a schedule for the live session and promotion that stays within the rules. Use this skill whenever the user says things like \"plan a Reddit AMA\", \"how do I do an AMA\", \"write my AMA intro\", \"pitch an AMA to moderators\", \"prepare for my Ask Me Anything\", \"promote my AMA\". Not for regular posts (use reddit-post-writer) or individual comments (use reddit-comment-drafter)."
metadata:
  author: Mr V
  version: "1.0"
  group: Reddit
---

# Reddit AMA Planner

You tell it who you are, what you know and what you hope comes out of it. It hands back the whole AMA package: subreddit choice, mod pitch, proof plan, title, intro post, answer bank, live-session runbook, promotion plan and follow-up.

---

## The core discovery: an AMA is judged by your answers, not your intro

People think AMAs succeed because of a great title or a famous name. A good title gets people in. What makes an AMA land is answers: specific, honest, sometimes surprising, and given to the hard questions as well as the easy ones.

The fastest way to fail is to treat it as a launch. Dodge the awkward question, plug your product in every reply, and the thread turns on you in public, permanently.

**Launch AMA:** "I'm the founder of X, the best tool for Y! Ask me anything (and check out our launch discount)."
**Real AMA:** "I ran a bakery for 11 years, went bust in 2023, and now teach small food businesses about cash flow. AMA about what went wrong."

The second invites real questions. The real questions make it worth reading.

---

## Intake

1. **Who you are** and the specific experience that makes you worth asking (a role, an event, a result, an unusual path).
2. **Target audience** and what they'd want to know.
3. **Goal:** reputation, research, awareness of a project. (Sales as the goal usually backfires.)
4. **Proof you can share:** photo with a sign, link to an official bio or profile, mod verification.
5. **Availability:** dates and a 2 to 3 hour window you can be fully present.
6. **Your Reddit account:** age, karma, history.
7. **Limits:** topics you can't discuss (legal, client confidentiality).

---

## Step 1: Pick the subreddit

| Option | Best for | Note |
|---|---|---|
| Niche subreddit (r/[your field]) | Most experts | Smaller, more engaged, more likely to say yes |
| r/IAmA | Broad public interest | Strict verification and scheduling rules. Check its current requirements. |
| r/AMA | Ordinary people with unusual experiences | Lighter rules, check current ones |
| Industry or hobby subs | Practitioners | Often host occasional AMAs with mod approval |

Use `subreddit-finder` if unsure. Check each subreddit's AMA rules (sidebar, wiki or a pinned post).

---

## Step 2: Pitch the mods

Message the moderators through modmail, at least a couple of weeks before your preferred date (or follow the subreddit's stated lead time).

**Pitch template:**
```
Subject: AMA request: [who you are, one line]

Hi mods,
I'm [name], [one-line credential]. I'd like to do an AMA in r/[sub] about [topic], because [why this community specifically].

Proposed: [date/time + timezone], live for [2–3] hours.
Proof: [what you can provide].
I won't promote anything during the AMA [or: I'll mention X once in the intro, if you're OK with it].

Happy to adjust to your rules or schedule.
```

---

## Step 3: Write the title and intro

**Title formula:** `I'm [specific identity + credential]. [Interesting hook]. Ask me anything.`
- Bad → "Marketing expert here, AMA!"
- Good → "I've written 400 cold emails for SaaS startups, and 3 of them made more money than all the others combined. AMA."

**Intro post (150 to 300 words):**
1. Who you are (two lines).
2. Why you're qualified (specific, not grand).
3. What you're happy to talk about, and what you can't.
4. Proof (photo or link, as the subreddit requires).
5. When you'll be answering ("I'll be here 2–5pm ET and will come back tomorrow for late questions").

One mention of your project, only if the mods agreed.

---

## Step 4: Build the answer bank

Prepare draft answers so you can be fast without being canned:
- **Likely questions** (10 to 15): from your field's common questions and `reddit-audience-insights`.
- **Hard questions** (5 to 10): the awkward ones. Mistakes, money, criticism of your industry, "isn't this just an ad?". Draft honest answers.
- **Personal questions:** decide in advance what you'll share.

Rule for live answers: personalise every one to the question asked. A pasted answer to a slightly different question reads badly.

---

## Step 5: Live session runbook

| Time | Do |
|---|---|
| −30 min | Post goes up (or mods post it). Check proof is visible. |
| 0 | Start answering the top-voted questions first. |
| Every 20 min | Sort by new to catch fresh questions. |
| Throughout | Answer hard questions early. Avoiding them is noticed. |
| End | Post a short "wrapping up, will check back tomorrow" edit to the intro. |
| +24 h | Answer a batch of late questions. |

Get a helper if possible to flag good questions, but answer as yourself only.

---

## Step 6: Promotion and follow-up

- **Before:** announce the date on your own channels (newsletter, LinkedIn, X). Link to the thread once it's live.
- **Never ask people to upvote.** That's vote manipulation under Reddit's rules. Invite them to ask questions.
- **After:** write a summary post or newsletter issue of the best questions and answers on your own channels, linking back to the thread.

---

## Rules

1. **Mods first.** No AMA without approval where it's required.
2. **Specific credential, specific hook.**
3. **Answer the hard questions, early.**
4. **No plugging in answers.** One intro mention, at most, if approved.
5. **Never ask for upvotes.**
6. **Be fully present for the window you promised.**
7. **Never invent credentials or stories.** Reddit will check.

---

## Worked example

**Input:** Freelance copywriter, 9 years, wrote email sequences for 60+ e-commerce brands. Goal: reputation. Available Tuesday 6–9pm UK.

**Subreddit:** r/copywriting (niche, engaged). Check AMA rules in sidebar → mods require proof via modmail.

**Title:** "I've written email sequences for 60+ online shops over 9 years. The best one was 4 emails long. AMA about email copy."

**Hard questions prepared (excerpt):**
- "Isn't AI making you obsolete?" → honest answer about what's changed in their own work.
- "What's your worst-performing email ever?" → a real one, with numbers if they'll share.

**Promotion:** newsletter mention Monday, LinkedIn post Tuesday morning with the thread link once live. No "please upvote".

---

## Output format

```
## AMA plan: [who] in r/[sub]
Date: [ ]   Window: [ ]

1. Subreddit + rules summary
2. Mod pitch (ready to send)
3. Proof plan
4. Title options (3)
5. Intro post
6. Answer bank (likely / hard / personal)
7. Live runbook
8. Promotion + follow-up plan
```

---

## Sibling skills

- `subreddit-finder`: choose the host subreddit.
- `reddit-rules-checker`: check the intro against the subreddit's AMA rules.
- `reddit-audience-insights`: source the likely questions.
- `reddit-comment-drafter`: help shape live answers.
- `reddit-post-writer`: when an AMA isn't a fit and a regular post is better.

---

## Pre-flight checklist

- [ ] Mods contacted and approval received (where required).
- [ ] Proof ready in the subreddit's required format.
- [ ] Title has a specific credential and hook.
- [ ] Hard questions drafted honestly.
- [ ] Window blocked and follow-up time planned.
- [ ] Promotion invites questions, never upvotes.
- [ ] No invented credentials.
