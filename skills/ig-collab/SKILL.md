---
name: ig-collab
description: >-
  The collab matchmaker. Finds and scores niche-adjacent accounts worth
  collaborating with, drafts the pitch DM, and plans the joint post. Collab
  posts appear on both profiles with merged engagement - the cheapest
  legitimate reach-borrowing on Instagram. Use when the user says "collab",
  "who should I partner with", "joint post", "pitch this creator", or growth
  has plateaued and the content is already good.
---

# ig-collab

A collab post is one post, two profiles, merged likes and comments, and both
audiences in the feed. It borrows reach from an adjacent audience with zero
ad spend, and both parties have to accept the tag - which means the whole
game is picking the right partner and writing a pitch that gets a yes.

## Picking partners - the scorecard

Build a shortlist of 5-10 candidates (the ig-research agent collects them;
within ~3x of the user's size in either direction - collabs work on rough
parity, nobody big collabs down for free). Score each 1-5 on:

1. **Audience overlap without content overlap** - same person follows both,
   but for different things. A copywriter and a designer share clients; two
   copywriters share competitors.
2. **Sends-per-reach on their recent posts** - a partner whose audience
   shares is worth more than one whose audience likes (estimate from their
   outlier posts if exact numbers aren't visible).
3. **Engagement authenticity** - real comments with substance, not pods and
   emoji walls.
4. **Warmth** - have they interacted with the user before? A cold pitch to a
   warm account converts several times better; the ig-engager agent's
   commenting plan (`/ig-comment`) is how accounts get warmed, 2-3 weeks
   ahead.

Present the shortlist as a table with scores and the one-line reason.

## The pitch

Follow `/ig-dm`'s collab pitch structure, plus the collab-specific parts:
name the *specific* post idea (never "we should collab sometime"), say what
their audience gets out of it, propose the format and the split of work, and
make saying yes one word. Two follow-ups maximum, per `/ig-dm`. The user
sends it - outreach is never automated.

## The joint post

Plan it like any other post (hooks scored, caption linted, humanized), with
the collab-specific rules:

- The format that shares best between audiences is the **carousel** (the 9x
  saves advantage compounds across two audiences) or a conversation-format
  reel.
- The hook must work for *both* audiences cold - test it against each
  account's framing.
- Agree upfront, in the pitch thread: who posts the original, who gets the
  collab tag, posting time, and whether either boosts it.

## Rules

- Never fabricate familiarity in a pitch ("long-time fan" the user isn't).
- One collab per 2-4 weeks. A feed of collabs reads as an account with
  nothing of its own.
- Log outcomes in `~/.claude/instagram/collabs.md`: partner, post, their
  audience's response (follows gained, per the ig-analyst agent's
  attribution) - evidence for who to work with again.
