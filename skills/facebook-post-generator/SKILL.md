---
name: facebook-post-generator
description: Write Facebook Page posts and captions for text, link, single-photo and multi-photo (up to 10) posts, with one clear call to action, ready to publish with the PostOnce Facebook MCP. Use when the user asks for a Facebook post, a Facebook post generator, a Facebook caption or caption generator, or to turn an update, event, offer, article or photos into a post for their Facebook Page.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Facebook post generator

Write one post for a Facebook Page, then hand it to the `postonce` skill if the user wants it published or scheduled. This server posts to Pages only, not personal profiles or Groups.

## Before writing

Get or infer: the Page (business, creator, community, local shop), who follows it, the one thing the post should get people to do or know, and any facts that matter (date, price, place, link). Never invent prices, dates, reviews or results.

## Pick the format

| Format | Use when | Notes |
| --- | --- | --- |
| Text | A question, a short story, an opinion, a quick update | Keep it short enough to read without tapping "See more". |
| Link | Sending people to an article, booking or product page | Put the URL in the text. Facebook builds its own preview from the page's metadata. |
| Single photo | One strong image: a product, a person, a moment | Real photos of people and places beat stock images. |
| Multiple photos (2–10) | An event, a before/after, a product range, a menu | Lead with the best image; the first few show in the grid. |
| Video | Anything moving | Every video posts as a Reel. Use `facebook-reel-script`. |

Photos: JPEG or PNG, up to 10 MB each, up to 10 per post. Photos and video can't be mixed in one post.

## Writing rules

- The first line carries the post. Facebook truncates longer posts behind "See more", so say the news, the benefit or the hook first.
- Write like a person on the Page's team. Name people, places and specifics.
- One post, one message, one call to action: book, reply, share with someone, visit, vote with a comment.
- Short paragraphs with blank lines between them. Most Page posts land best under about 80 words; stories and announcements can run longer. The hard limit is 63,206 characters.
- Questions work when they're easy to answer from experience ("Which one would you order first?"). Avoid engagement bait like "Comment YES", "Tag 5 friends" or "Share if you agree"; Facebook demotes it.
- Hashtags are optional on Facebook. Use 0–3 specific ones, or none.
- One or two emoji at most, where they help scanning. No emoji bullet walls.
- Plain words. No "game-changer", "unlock", "we're thrilled to announce".

## Output format

Give 2–3 options exactly as they'll appear, each labeled with its format and the media it needs (for photos: what each image should show and the order). Recommend one.

## Output

Offer to publish or schedule it with the `postonce` skill: upload any photos with `create_upload_url`, confirm which Page and the time, then call `create_post`.
