---
name: facebook-content-calendar
description: Plan 1 to 4 weeks of Facebook Page posts and Reels from the user's goals and content pillars, or by repurposing a blog post, video or transcript, then draft every slot and schedule them with the PostOnce Facebook MCP. Use when the user asks for a Facebook content calendar, a content plan or posting schedule for their Facebook Page, Facebook post ideas, or to turn one piece of content into a month of Facebook posts.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Facebook content calendar

Plan native Facebook Page posts, not copies of another platform's captions. This server posts to Pages only (no personal profiles, Groups or Stories).

## Inputs

Get or infer:
- Goal: bookings, sales, website visits, event turnout, community, awareness.
- The Page and its audience (local customers, a niche community, clients).
- 2–4 content pillars (for example: offers, behind the scenes, customer stories, useful tips, events). Or a source to repurpose: a blog URL, a YouTube video, a newsletter, a transcript.
- Assets and capacity: photos they have, whether they can film Reels, how many posts a week they can sustain.
- Timezone, the weeks to cover, and preferred times.

Never invent offers, prices, dates, reviews or results.

## Formats available

| Format | Limits |
| --- | --- |
| Text | Up to 63,206 characters; short works best. |
| Link | URL in the text; Facebook builds the preview. |
| Photo | 1 photo, or 2–10 in one post. JPEG or PNG, up to 10 MB each. |
| Reel | 1 vertical 9:16 video, at least 540×960. Every video posts as a Reel. |

## Build the plan

- Frequency: match what the Page can sustain. A few good posts a week beat daily filler.
- Mix formats: photos and Reels for reach, text questions for conversation, links for traffic. Don't make every post a link.
- Rotate pillars so adjacent posts differ.
- Repurposing: split the source into single ideas. One post, one idea: a tip as a photo post, a story as text, a how-to as a Reel, the article itself as one link post.
- Time-bound posts (events, offers) get a reminder slot close to the date.

## Draft every slot

For each slot: date, time and timezone; format; the post text (see `facebook-post-generator`) or the Reel script (see `facebook-reel-script`); media needed and its order.

Return the plan as a table (date, time, pillar, format, first line, media status), then the full drafts.

## Schedule it

On approval:
1. Confirm the Page with `list_accounts` and the timezone.
2. For each slot with media ready (or text-only): upload media with `create_upload_url`, then `create_post` with `publish_at` as an ISO timestamp with offset.
3. For slots still waiting on photos or video, save the text with `create_draft`.
4. Report each post ID and status with `get_post`. Scheduled is not published; say which is which.

Scheduled posts can be changed with `update_post` or cancelled with `cancel_post` before they run.
