---
name: reddit-comment-drafter
description: "Drafts genuinely helpful Reddit comments that earn upvotes and profile clicks: picks threads worth answering, writes a comment that answers the exact question with specifics from your own experience, matches the subreddit's tone, and keeps any mention of your product inside the community's rules (usually none). Also handles replies on your own posts and tricky replies to critics. Use this skill whenever the user says things like \"help me answer this Reddit thread\", \"write a Reddit comment\", \"reply to this comment on my post\", \"how do I mention my product on Reddit without spamming\", \"someone is criticising me on Reddit\", \"build karma by helping people\". Not for top-level posts (use reddit-post-writer)."
metadata:
  author: Mr V
  version: "1.0"
  group: Reddit
---

# Reddit Comment Drafter

You paste a Reddit thread (the post plus relevant comments) and tell it what you know. It hands back a comment that answers better than anyone else in the thread, in that community's voice.

You post it yourself.

---

## The core discovery: the best comment in the thread is the best ad on Reddit

When someone asks a question on Reddit, dozens of people answer. The one that gets upvoted to the top is read by everyone who finds that thread later, often for years through Google. If it's genuinely the most useful answer, a share of readers click the name to see who wrote it.

That's the funnel: a useful answer → a profile click → a profile that mentions what you do. No pitch needed.

**Spam comment:** "Great question! I actually built a tool for this, check it out: [link]"
**Top comment:** "I had the same problem with three clients last year. What fixed it: I moved the deposit into the proposal instead of the invoice, and gave one reason ('it books your slot'). Nobody pushed back. The one client who did had already haggled on price, so it was a useful filter."

The second never mentions a product. It gets upvoted. People check the profile.

---

## Intake

1. **The thread:** the post and the top comments, pasted in.
2. **The subreddit** and its rules (or let Claude read them).
3. **What you actually know** about the topic: experience, numbers, mistakes.
4. **Your goal:** help, reputation, or (only where allowed) mention your offer.
5. **Your connection** to anything you might mention.

---

## Step 1: Is this thread worth answering?

Answer when:
- the question is one you can answer better than the existing comments
- the thread is recent enough that people are still reading (or it ranks in Google for a useful search)
- the subreddit allows the kind of answer you'd give

Skip when:
- 30 good answers already exist and yours adds nothing
- the thread is a fight
- the only useful thing you could say is "buy my product"

---

## The five comment moves

| Code | Move | Use when | Shape |
|---|---|---|---|
| C1 | Direct Answer | A clear question | Answer in line one → why → one specific example |
| C2 | Been There | Someone describes a struggle | Short relatable line → what you did → what happened |
| C3 | Step List | A "how do I" question | Numbered steps, each one line, with the gotcha flagged |
| C4 | Gentle Correction | Wrong info in the thread | Agree with what's right → correct the error with a source |
| C5 | Better Question | The asker is solving the wrong problem | Ask the clarifying question → offer a provisional answer |

---

## Rules

1. **Answer in the first line.** Redditors skim.
   - Bad → "Great question! So, I've been freelancing for about six years now, and..."
   - Good → "Ask for 50% upfront and put it in the proposal, not the invoice."
2. **Specifics from your own experience.** A number, a tool, a mistake. That's what separates you from generic advice.
3. **Match the tone.** Technical subs want precision. Support subs want warmth. Some subs want dry humour. Read the top comments.
4. **No links unless they genuinely answer the question and the rules allow them.** Even then, prefer a non-commercial source.
5. **Mentioning your own thing:** only when it directly answers the question, only where the rules allow, always with disclosure ("I made this, so take it with salt"), and never in most of your comments. If in doubt, leave it out. The profile does the work.
6. **No AI tells.** No "Great question!", no "I hope this helps!", no bold headers in a three-line comment, no tidy three-part lists for a casual answer. Write like a person typing.
7. **Short beats thorough unless the question asks for depth.**
8. **Disagree with the claim, never the person.**
9. **Never invent experience.** If the user hasn't done it, the comment doesn't say they have.

---

## Handling critics on your own post

| Critic type | Reply |
|---|---|
| Fair point | "That's fair. I didn't think about X. Here's what I'd change." |
| Misread | Clarify once, politely, with the specific line they missed. |
| Accusing you of shilling | Acknowledge your connection plainly, point to the value in the post, don't argue. |
| Troll | Don't reply. Report if it breaks rules. |

Never argue in a chain more than one or two replies deep. The thread's readers decide who looks reasonable.

---

## Profile setup (do this once)

A comment strategy only works if the profile converts. Suggest the user:
- writes a one-line bio saying who they are and what they help with
- adds one link (site or newsletter) in the profile, where Reddit allows
- keeps a healthy mix of non-promotional activity

---

## Worked example

**Thread pasted (r/Substack):** "How do people get their first 100 subscribers? I've posted 8 issues and have 12, mostly friends."

**Comment (C2 Been There + C3 Step List):**
```
I was stuck at 19 for two months. What got me to 100 (took about 7 weeks):

1. Stopped posting issues into the void and started leaving real comments on 3 bigger newsletters in my niche every day. Several of their readers clicked through.
2. Wrote one issue that was a genuinely useful resource (a list of free tools I actually use) and shared it in two subreddits where that was allowed.
3. Added a one-line "who this is for" at the top of my About page. Sounds tiny, but conversions on profile visits went up.

The thing that didn't work: asking friends to share. They did, once, and nothing came of it.

What's your niche? The comment approach depends a lot on who the bigger writers are.
```
(Numbers and steps come from the user's real experience. No link, no product.)

---

## Output format

```
## Comment for: [thread title] in r/[sub]
Worth answering: [yes/no + why]
Move: [C1–C5]
Tone: [ ]

[comment text]

Mentions offer: [no / yes, allowed by rule X, disclosed]
Likely follow-up questions: [ ]
```

---

## Sibling skills

- `reddit-post-writer`: when your answer is big enough to be its own post.
- `reddit-rules-checker`: if unsure whether a mention is allowed.
- `subreddit-finder`: find threads in the right communities.
- `reddit-audience-insights`: find the questions that come up again and again.

---

## Pre-flight checklist

- [ ] Thread is worth answering.
- [ ] Answer in line one.
- [ ] At least one specific from real experience.
- [ ] Tone matches the subreddit.
- [ ] No link or product unless it answers the question, is allowed and is disclosed.
- [ ] No AI tells.
- [ ] Nothing invented.
