# Contributing

Thanks for wanting to make this better. The short rules:

## What makes a good PR

- **Facts with sources.** Platform claims in `skills/ig-agent/facts.md` or
  any SKILL.md need a date and a source. Instagram changes things; dated
  facts can be checked, undated ones rot silently.
- **One job per skill, one job per agent.** If a new skill does three
  things, it is three skills. Frontmatter descriptions should say when to
  use it in the user's words ("plan my week", "A/B test my hook"), because
  that is what routes requests.
- **Evidence over vibes.** New heuristics (hook formulas, scoring checks,
  best-practice claims) should say what they were tested on, even if the
  answer is "nothing yet, this is a prior".
- **The Python tools stay dependency-free.** Standard library only, no
  network calls, nothing uploaded anywhere.

## What gets closed

- Anything that crosses Instagram's ToS line: scraping, browser automation
  against instagram.com, credential handling, auto-follow/auto-like, mass
  cold DMs. The fine print in the README is the design, not a disclaimer.
- Anything that weakens the approval gate - the rule that no post or
  automation reaches the live account without the user approving that exact
  thing.
- Fabrication features - anything that invents metrics, clients, or
  outcomes under the user's name.

## House style

- SKILL.md files: plain prose, short sections, honest about limitations.
  Numbers over adjectives.
- Data files (`hooks.json`, `slop.json`, `rubric.json`) are meant to be
  extended - keep the existing schema.
- Run `python3 skills/ig-human/detect.py` on your own README/SKILL prose if
  you want to fit in.

## Reporting problems

Open an issue with: what you asked, what the skill/agent did, what you
expected. For stale platform facts, a link to the current truth is worth
more than the report alone.
