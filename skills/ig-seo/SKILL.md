---
name: ig-seo
description: >-
  Instagram SEO. Since July 2025 Google and Bing index public professional
  accounts, so captions, bios, alt text and hashtags are search surfaces.
  This skill does the keyword research, rewrites the caption's first line and
  the bio name field for search intent, and writes manual alt text for every
  post. Use when the user says "instagram seo", "get found in search",
  "keywords", "alt text", or when optimizing any post for discovery.
---

# ig-seo

On July 10, 2025, Instagram let Google and Bing index public content from
professional accounts (indexing is on by default; Settings → Privacy to opt
out). Stories and private accounts are excluded. That made every caption a
tiny web page, and almost nobody is optimizing for it yet. Instagram's own
search works the same way: keywords beat hashtags.

## Keyword research, the cheap way

1. **Instagram autocomplete.** Type the niche term into IG search and record
   what it suggests - those are real queries. The ig-research agent can
   collect these; otherwise ask the user for 2 minutes in their app.
2. **Google check.** Search the candidate phrases; note which already surface
   Instagram posts (proof the door is open) and which SERPs are weak.
3. Keep a working set of 5-10 phrases in `~/.claude/instagram/keywords.md`:
   the head term, the question forms, and the "near me / for X" variants if
   local or audience-specific.

## What gets optimized, in order of leverage

1. **Bio name field** - not the handle, the bold name line. `Name | head
   keyword` is the single highest-leverage edit (it is weighted in both IG
   and Google search). Coordinate with `/ig-profile`.
2. **Caption first line** - the search-intent phrase appears naturally in the
   first sentence, *without* breaking the hook. A hook and a keyword are not
   enemies; "How I price freelance projects after losing $18,000" carries
   both. Lint the result with `python3 skills/ig-caption/caption.py
   --keywords "..."` - it already checks search-term presence.
3. **Alt text, written manually, every post** - one sentence, what is
   literally in the image plus the keyword where honest. Instagram's
   auto-alt-text is generic; manual alt text is indexed. Deliver it with
   every carousel slide and image post the ig-creator agent produces.
4. **Hashtags** - max 5, treated as topic labels not reach magic. Specific
   beats generic (#freelancecontracts beats #freelance).

## Rules

- Keywords serve the reader or they don't ship. A stuffed caption fails the
  humanizer and reads like 2012 blogspam; one natural phrase per surface.
- Never promise rankings. Log which optimized posts get indexed (site:
  instagram.com search) and which rank; that goes in the ig-analyst agent's
  monthly report as evidence, not prediction.
- Bio and name-field changes are profile edits the user makes by hand - hand
  them the exact text.
