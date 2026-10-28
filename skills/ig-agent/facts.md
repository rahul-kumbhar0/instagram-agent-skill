# Instagram platform fact sheet

Researched October 2026. Platform numbers go stale: if Instagram's live docs
or behavior contradict this file, Instagram is right. Agents should re-verify
anything load-bearing with a fresh search before acting on it.

## Content Publishing API

- Only **Business and Creator (professional) accounts** can publish via API.
- Two paths: the classic Instagram Graph API via Facebook Login (needs a
  linked Facebook Page, `instagram_content_publish` permission), and the newer
  "Instagram API with Instagram Login" (no Page required,
  `instagram_business_content_publish`). Both need a Meta developer app and
  App Review before serving external users.
- Supported media: images, videos, Reels (`media_type=REELS`), Stories
  (`media_type=STORIES`), carousels up to 10 items. Flow: create media
  container(s), then `media_publish`.
- **Publish rate limit:** Meta's docs have said both 50 and 100 API-published
  posts per rolling 24h. Query `GET /{ig-user-id}/content_publishing_limit`
  for the live quota rather than trusting either number. A carousel counts as
  one post. Practically, 1-2 posts/day is a strategy; near the cap is a spam
  signal.

## Messaging / DM automation

- Legal DM automation goes through the official Messaging API or approved
  partners only.
- **24-hour window:** automated replies are allowed within 24h of the user's
  last interaction; each interaction resets it.
- **Comment-to-DM:** a comment entitles the app to **one private reply**,
  within 7 days of the comment. The conversation continues only if the person
  replies (which opens the standard 24h window). Design funnels around that
  single message.
- Meta's policy requires bot disclosure. The "200 DMs/hour" cap often quoted
  by vendors is not in Meta's docs.
- Gets accounts banned: unsolicited mass cold DMs, password-based third-party
  logins, scraping follower lists for outreach, fake engagement.

## Algorithm and format facts

- **Hashtag cap is 5 per post** (cut from 30, announced December 2025,
  rolling out through 2026). Generic tags (#reels, #explore) do not boost
  reach.
- **Trial Reels** (launched Dec 2024): shown to non-followers first; a winner
  can be promoted to followers; schedulable since early 2026.
- Strongest ranking signals per Mosseri: **sends/shares** and **watch time**
  (total + replays). Common craft advice: original audio, under 90s, hook
  lands in the first 3 seconds.
- Posting frequency: no official number; third-party consensus is 3-4 reels a
  week, and consistency beats volume.
- Best-time studies (weak priors; the account's own Insights beat all of
  them): weekday midday and early evening generally outperform weekends.

## Insights / metrics

- **Deprecated since April 2025:** `impressions`, `plays`, `video_views`,
  `clips_replays_count`.
- Current: `views` (the unified metric), `reach`, `saved`, `shares`, `likes`,
  `comments`, `total_interactions`, `follows`, `profile_visits`; for Reels,
  `ig_reels_avg_watch_time` and `ig_reels_video_view_total_time`; plus
  account-level demographics.

## The ToS line

- **Prohibited:** browser automation and password-login bots, scraping,
  auto-follow/unfollow, auto-like, engagement pods, bought followers.
  Scraping triggers enforcement fastest; penalties run reduced reach →
  restriction → permanent ban.
- **Allowed:** the official APIs within their rate limits, approved partner
  tools, content scheduling, inbound-triggered reply automation, insights
  pulls.

Every agent in this plugin stays on the allowed side of that line, and says
so instead of improvising when a capability sits on the prohibited side.
