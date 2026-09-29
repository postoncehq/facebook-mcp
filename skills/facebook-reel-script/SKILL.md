---
name: facebook-reel-script
description: Write short vertical Facebook Reel scripts with a hook, beats, on-screen text and a caption, or adapt an existing TikTok or Instagram Reel for a Facebook Page, then post it with the PostOnce Facebook MCP. Use when the user asks for a Facebook Reel script, Reel ideas for Facebook, a short video script for their Page, or to repurpose a TikTok or Instagram Reel to Facebook.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# Facebook Reel script

Every video this server posts to a Facebook Page goes up as a Reel. Write for a vertical, full-screen, sound-optional viewer.

## Video requirements

- Vertical 9:16, at least 540×960. 1080×1920 is the safe choice. Other aspect ratios are rejected for Reels.
- One video per post, MP4 or MOV. It can't be combined with photos.
- Optional cover: a JPEG or PNG passed as `thumbnail_url` on the video (up to 8 MB).

## Before writing

Get or infer: the Page and its audience, the one idea, who's on camera (face, voiceover, hands, screen), and the target length. Facebook's audience is often a little older and more local than TikTok's. Plain explanations, real people and practical value tend to travel well. Never invent results, prices or testimonials.

## Structure

| Part | Time | Job |
| --- | --- | --- |
| Hook | 0–3 s | Spoken line, on-screen text and first shot that make the same promise. Start mid-action. |
| Setup | next few seconds | Why this matters to the viewer, in one line. |
| Beats | the middle | 3–5 beats, one point each, a visual change on every beat. |
| Payoff | last seconds | Deliver the promise. End with one ask: follow the Page, visit, book, or answer a question. |

15–60 seconds suits most Reels.

Rules:
- Captions on screen. Many people watch Facebook video with the sound off.
- Keep text away from the bottom fifth and the right edge, where the caption and buttons sit.
- No intros, no logo slate.

## Adapting a TikTok or Instagram Reel

- Upload the original file, not a download with another app's watermark.
- Rewrite platform-specific lines ("link in bio", "stitch this", TikTok sounds).
- Replace trend references Facebook viewers may not know with plain context.
- Rewrite the caption for Facebook: fewer or no hashtags, a clear first line.

## Caption

One or two lines: what the viewer gets, then the ask. 0–3 specific hashtags, or none.

## Output format

A table: Time | Spoken | On-screen text | Shot. Then the caption, the suggested cover frame, and a filming checklist.

## Output

Once the video exists, offer to publish or schedule it with the `postonce` skill: upload with `create_upload_url`, confirm the Page and the time, then call `create_post` with the video in `media`.
