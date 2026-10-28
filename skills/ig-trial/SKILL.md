---
name: ig-trial
description: >-
  The Trial Reels lab. Turns one script into 2-3 hook variants, runs them as
  Trial Reels (shown to non-followers only, hidden from the profile), reads
  the 24-hour results, and publishes only the winner. Use when the user says
  "trial reel", "A/B test my hook", "test this before posting", or wants to
  know which of two versions to post.
---

# ig-trial

Trial Reels are the only free A/B test Instagram has ever shipped: a reel
marked as a trial goes to **non-followers only**, never appears on the
profile, and reports its numbers about 24 hours later. That turns the
riskiest guess in short-form - the hook - into a measurement.

Requires a public professional (Creator/Business) account. The feature is
still rolling out; if the user doesn't see the Trial toggle, say so and fall
back to `/ig-reel`'s hook scoring alone.

## The workflow

1. **One script, 2-3 hooks.** Take the script (write it via
   `skills/ig-reel/SKILL.md` if it doesn't exist) and generate hook variants
   from different formulas in `skills/ig-reel/hooks.json` - not three
   phrasings of the same formula, three different bets. Score each with
   `python3 skills/ig-reel/hookscore.py` and drop anything WEAK before it
   costs a take.
2. **Shoot once, swap the first 3 seconds.** The body is identical across
   variants; only the hook (spoken line + on-screen text) changes. Give the
   user the exact alternate openings as a copy-ready block.
3. **Run the trials.** All variants go up as Trial Reels in the same session,
   same audio, same caption (the caption from `/ig-caption`, SEO-keyworded
   per `/ig-seo`). If a connected scheduler supports trial scheduling, the
   ig-publisher agent handles it - with the usual per-post approval;
   otherwise the user posts the trials by hand.
4. **Read at 24h.** Compare variants on **views, sends-per-reach, and watch
   time** against the account's trial baseline - not against each other's raw
   views alone. One clear winner → publish it publicly (or let Instagram
   auto-share it). No separation → the hook wasn't the variable that
   mattered; say so instead of inventing a winner.
5. **Log the learning.** Append one line per test to
   `~/.claude/instagram/trials.md`: date, topic, the formula that won, the
   formula that lost, the multiple between them. After ~10 tests this file
   outranks every generic hook guide, and the ig-research and ig-creator
   agents should read it.

## Rules

- Never run more than one *topic* per test. Two variables, zero conclusions.
- A trial that outperforms is evidence about non-followers; it says nothing
  about what the existing audience wants. Don't let trial wins rewrite the
  whole strategy - that is the ig-strategist agent's call.
- Trials still count as content: humanizer gate and fabrication rules apply.
