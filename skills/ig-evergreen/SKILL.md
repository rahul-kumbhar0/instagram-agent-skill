---
name: ig-evergreen
description: >-
  The evergreen library. Keeps a categorized library of the account's proven
  content and recycles it on a rotating schedule - each re-run rewritten as a
  fresh variation, never a repost. Use when the user says "recycle",
  "evergreen", "repost my best content", "I have nothing to post", or the
  queue has gaps the strategist needs to fill.
---

# ig-evergreen

The best-performing post an account ever made was seen by a fraction of its
audience, once. Recycling it is the highest-ROI content work that exists -
*if* it comes back as a new post, not a repost. Instagram's aggregator
penalty replaces reposted content with the original in recommendations, so
the unit of recycling here is the **idea**, re-executed, never the file,
re-uploaded.

## The library

One file: `~/.claude/instagram/evergreen.md`. Each entry:

```
## [category] The $18,000 contract clause
proven: 2026-01-14 reel, 4.1x outlier, 2.3% sends/reach
core idea: approval is a feeling, delivery is a date - put payment on delivery
ran as: reel (talking head) · carousel (2026-03) 
next variation: story sequence with poll, or reel from the client's POV
cooldown until: 2026-05-01
```

- **Entry criteria:** only outliers get in - above ~2x the account median or
  unusually high sends/saves per reach (the ig-analyst agent nominates them
  in every post-mortem).
- **Categories** (4-6, the account's actual pillars): the strategist agent
  defines them once; the rotation cycles through categories so the feed never
  runs three of the same pillar in a row.
- **Cooldown:** 6-8 weeks minimum before an idea runs again, longer for
  smaller accounts where the same followers see everything.

## A variation is a new post

Re-running an entry means handing the ig-creator agent the core idea plus a
*changed angle* - new hook formula (different row of
`skills/ig-reel/hooks.json` than last time), new format (reel → carousel →
story sequence), new entry point (the mistake → the fix → the client's view
→ the numbers). Same thesis, new post. It goes through the full pipeline:
hook scoring, caption lint, humanizer, user approval. If the variation reads
like the original with synonyms, it isn't one - change the angle, not the
words.

## The rotation

When the strategist builds the week and has open slots, evergreen fills them:
pick the category least recently run, the entry longest off cooldown, and
propose it in the plan marked `[evergreen: <entry>]` so the user knows it is
a re-run of a proven idea. Target mix: roughly 1 evergreen per 3-4 new posts.
An account that is mostly recycling has a research problem, not a library
problem.

## Rules

- Never re-upload the same video or image file as a new post.
- Every variation's performance gets logged back onto its entry - an idea
  that flops twice in a row leaves the library.
- Seasonal/time-sensitive content never enters the library; it gets an
  expiry note in the plan instead.
