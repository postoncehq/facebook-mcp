<p align="center"><img src=".github/cover.png" alt="Facebook MCP server for Claude, ChatGPT, Cursor and Codex" width="100%"></p>

# Facebook MCP Server

Facebook MCP server for Claude, ChatGPT, Cursor and Codex. Your AI agent can write, publish and schedule posts, photos and Reels on your Facebook Page through Facebook's official API. There's no scraping, no browser automation and no Facebook developer app to set up.

It runs on [PostOnce](https://postonce.to?utm_source=github&utm_campaign=facebook-mcp)'s hosted MCP server and comes with Facebook skills for Page posts, Reel scripts and content calendars, so your agent knows what works on a Facebook Page before it posts.

**[Start free for 7 days, no card →](https://postonce.to?utm_source=github&utm_campaign=facebook-mcp)** · Used by 3,500+ users

[![Claude](https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logoColor=white&logo=claude)](https://postonce.to/integrations/claude?utm_source=github&utm_campaign=facebook-mcp) [![ChatGPT](https://img.shields.io/badge/ChatGPT-10A37F?style=for-the-badge&logoColor=white)](https://postonce.to/integrations/chatgpt?utm_source=github&utm_campaign=facebook-mcp) [![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=for-the-badge&logoColor=white&logo=claude)](https://postonce.to/integrations/claude-code?utm_source=github&utm_campaign=facebook-mcp) [![Codex](https://img.shields.io/badge/Codex-000000?style=for-the-badge&logoColor=white)](https://postonce.to/integrations/codex?utm_source=github&utm_campaign=facebook-mcp) [![Cursor](https://img.shields.io/badge/Cursor-000000?style=for-the-badge&logoColor=white&logo=cursor)](https://postonce.to/integrations/cursor?utm_source=github&utm_campaign=facebook-mcp) [![Gemini CLI](https://img.shields.io/badge/Gemini_CLI-8E75B2?style=for-the-badge&logoColor=white&logo=googlegemini)](https://github.com/postoncehq/postonce-gemini-extension) [![Grok](https://img.shields.io/badge/Grok-000000?style=for-the-badge&logoColor=white&logo=x)](https://postonce.to/integrations/grok?utm_source=github&utm_campaign=facebook-mcp) [![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logoColor=white&logo=n8n)](https://postonce.to/integrations/n8n?utm_source=github&utm_campaign=facebook-mcp) [![Make](https://img.shields.io/badge/Make-6D00CC?style=for-the-badge&logoColor=white&logo=make)](https://postonce.to/integrations/make?utm_source=github&utm_campaign=facebook-mcp) [![Zapier](https://img.shields.io/badge/Zapier-FF4F00?style=for-the-badge&logoColor=white&logo=zapier)](https://postonce.to/integrations/zapier?utm_source=github&utm_campaign=facebook-mcp) [![Any MCP client](https://img.shields.io/badge/Any_MCP_client-1D4ED8?style=for-the-badge&logoColor=white)](https://postonce.to/integrations/mcp?utm_source=github&utm_campaign=facebook-mcp)

```
You:    Write a Facebook post for our bakery page announcing the new sourdough
        class, with these 3 photos, and schedule it for Thursday 10am.
Claude: Drafted it with the facebook-post-generator skill. The first line
        gives the date and what people will bake; the booking link is in the
        last line. Scheduled on PostOnce for Thu 10:00 on "Rise Bakery".
```

Full setup guide with examples: [postonce.to/mcp/facebook](https://postonce.to/mcp/facebook?utm_source=github&utm_campaign=facebook-mcp)

## What hosted PostOnce handles for you

| | |
| --- | --- |
| Approved platform apps | No developer app or platform review on your side. Connect your accounts and post. |
| Official APIs | Every post goes through each platform's official API. No scraping, no browser automation. |
| Retries | Temporary platform errors retry on their own, without posting twice. |
| Status per platform | Each post shows its status and live link on every platform. |

## What you can do

| Ask your agent to | How it works |
| --- | --- |
| Publish a text post now, with or without a link | `create_post` on your connected Facebook Page |
| Schedule a post for later | `create_post` with `publish_at` |
| Post one photo or up to 10 photos | `create_upload_url`, upload, then `create_post` with `media` |
| Post a video as a Reel (9:16, at least 540×960) | Upload one video, then `create_post`; every video posts as a Reel |
| Set the Reel cover | `thumbnail_url` on the video |
| Post to any Page you manage | Pick the Page from `list_accounts` |
| Save a draft to finish later | `create_draft` |
| Check whether a post went out, and get its URL | `get_post` |
| Change or cancel a scheduled post | `update_post`, `cancel_post` |
| See views, likes, comments, shares and saves for your posts | `get_analytics`, `get_post_analytics` |
| Post the same thing to Facebook and other platforms | Add more targets to `create_post` (Instagram, TikTok, YouTube, LinkedIn, X, Threads, Pinterest, Bluesky) |

Not supported: personal profiles, Groups, Facebook Stories, regular (non-Reel) video posts, mixing photos and video in one post, reading or replying to comments, Messenger, and editing or deleting posts after they're published. Links in the post text use Facebook's own link preview.

## Setup (about a minute)

You need a [PostOnce account](https://postonce.to?utm_source=github&utm_campaign=facebook-mcp) (free for 7 days, no card) with your Facebook Page connected.

**Claude (claude.ai and desktop) and ChatGPT:** add a custom connector with the URL below and sign in with PostOnce. No API key.

```
https://postonce.to/mcp
```

Step-by-step: [Claude](https://postonce.to/integrations/claude?utm_source=github&utm_campaign=facebook-mcp) · [ChatGPT](https://postonce.to/integrations/chatgpt?utm_source=github&utm_campaign=facebook-mcp)

**Claude Code:** install the plugin. It adds the MCP connection and the skills together, and the first time it connects your browser opens to sign in with PostOnce. No API key.

**Cursor:** install the plugin, then click **Connect** next to `postonce` in Cursor's MCP settings and sign in with PostOnce. No API key.

**Codex:** install the plugin, then run `codex mcp login postonce` and sign in with PostOnce in the browser. No API key.

```bash
# Claude Code
claude plugin marketplace add postoncehq/plugins
claude plugin install facebook-mcp@postoncehq
```

Step-by-step: [Claude Code](https://postonce.to/integrations/claude-code?utm_source=github&utm_campaign=facebook-mcp) · [Codex](https://postonce.to/integrations/codex?utm_source=github&utm_campaign=facebook-mcp) · [Cursor](https://postonce.to/integrations/cursor?utm_source=github&utm_campaign=facebook-mcp)

**Any other MCP client:** point it at `https://postonce.to/mcp` (Streamable HTTP) and sign in with PostOnce when it asks. Clients without OAuth can send the header `Authorization: Bearer <your PostOnce API key>` instead (API keys are in [PostOnce preferences](https://postonce.to/dashboard/preferences?utm_source=github&utm_campaign=facebook-mcp) and need a paid plan).

## Skills included

| Skill | What it does |
| --- | --- |
| [`facebook-post-generator`](skills/facebook-post-generator/SKILL.md) | Writes Facebook Page posts and captions for text, link, single-photo and multi-photo posts, with one clear call to action. |
| [`facebook-reel-script`](skills/facebook-reel-script/SKILL.md) | Writes vertical Reel scripts with a hook, beats, on-screen text and the caption, or adapts a TikTok or Instagram Reel for Facebook. |
| [`facebook-page-description`](skills/facebook-page-description/SKILL.md) | Writes the Page intro and About copy, for you to paste into your Page settings. |
| [`facebook-content-calendar`](skills/facebook-content-calendar/SKILL.md) | Plans 1 to 4 weeks of Page posts and Reels from your goals or a source you already have, then schedules them. |
| [`postonce`](skills/postonce/SKILL.md) | Publishing workflow: pick the right account, upload media, schedule, and confirm the post actually went live. |

## FAQ

**Is there an official Facebook MCP server?**
This server uses Facebook's official API through PostOnce. Your agent talks to PostOnce over MCP, and PostOnce publishes to your Page with the permissions you grant when you connect.

**Can Claude post to a Facebook Page?**
Yes, once it's connected to an MCP server that can publish, like this one. Claude writes the post, uploads any photos or video, then calls `create_post`.

**Is it safe for my Facebook account?**
Yes. Posts go through Facebook's official posting API with the permissions you grant when you connect. There's no scraping and no browser session, and you can revoke access any time.

**Do I need a Facebook developer app or API approval?**
No. PostOnce holds the Facebook API access; you just connect your Page.

**Can it post to my personal profile or a Facebook Group?**
No. It posts to Facebook Pages you manage. Facebook's API doesn't allow apps to publish to personal profiles, and Groups aren't supported.

**Can it post Facebook Reels?**
Yes. Every video posts as a Reel, so send a vertical 9:16 video at least 540×960. You can set the cover with a thumbnail image.

**Is it free?**
The skills and this repo are free and MIT-licensed. Publishing runs through a PostOnce account, which you can try free for 7 days without entering a card. After that, see [pricing](https://postonce.to/pricing?utm_source=github&utm_campaign=facebook-mcp).

## Data and privacy

- The posts, captions and media you ask your agent to publish are sent to PostOnce and on to the platforms you choose. Nothing is published without a request from you.
- Media files you upload go straight to PostOnce's file storage through a short-lived signed upload link, then publish from there. Uploaded media is publicly reachable so the platforms can fetch it.
- PostOnce stores your posts, media and connected account names so it can schedule them and show your publishing history. You can disconnect accounts and revoke access at any time in [PostOnce preferences](https://postonce.to/dashboard/preferences?utm_source=github&utm_campaign=facebook-mcp).
- The skills themselves run in your agent and send nothing anywhere else.

Full details: [privacy policy](https://postonce.to/privacy-policy?utm_source=github&utm_campaign=facebook-mcp) · [terms](https://postonce.to/tos?utm_source=github&utm_campaign=facebook-mcp).

## Other platforms

The same connection posts everywhere PostOnce supports. Platform repos with their own skills:
[LinkedIn MCP](https://github.com/postoncehq/linkedin-mcp) · [Instagram MCP](https://github.com/postoncehq/instagram-mcp) · [TikTok MCP](https://github.com/postoncehq/tiktok-mcp) · [YouTube MCP](https://github.com/postoncehq/youtube-mcp) · [X (Twitter) MCP](https://github.com/postoncehq/x-mcp) · [Threads MCP](https://github.com/postoncehq/threads-mcp) · [Bluesky MCP](https://github.com/postoncehq/bluesky-mcp) · [Pinterest MCP](https://github.com/postoncehq/pinterest-mcp)

## License

MIT. See [LICENSE](LICENSE).
