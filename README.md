# Uniscript MCP — AI Carousel Maker for TikTok & Instagram

**Stop spending an hour per carousel in Canva.** Tell Claude, ChatGPT, Cursor or Codex what you need and get a finished, scroll-stopping TikTok / Instagram carousel in about 40 seconds — then fix any detail by just asking.

<p><img src="assets/mcp_01.webp" width="160"> <img src="assets/mcp_02.webp" width="160"> <img src="assets/mcp_03.webp" width="160"> <img src="assets/mcp_04.webp" width="160"></p>

*Real output. Slide 3 is after one request: “remove the number on slide 3 and make the title yellow”.*

## The problem

Carousels are the most saved post format on Instagram and TikTok — and the most tedious to make: write the hook, split the idea into slides, find photos that fit, lay out every slide, export. AI agents can write the text, but they can't hand you a finished, on-brand design.

## What Uniscript gives your agent

- 🪄 **A finished carousel from one sentence.** Topic in → hook cover, 5–7 slides with real photos (5,000+ for 42 niches), 1080×1920 PNGs out. Hooks follow proven formulas.
- 🎬 **Repurpose videos.** Send a TikTok / Reels / Shorts / VK / RuTube link or the video file — get a carousel with its key points.
- 📸 **Your own photos.** Product shots, your café, your face — the carousel is built from them.
- ✏️ **Edit any layer by asking.** Hide the number, move the title, recolor the button, rewrite a slide, swap a photo, reorder or add slides, change theme or fonts. Edits are re-rendered instantly and free.
- 🧩 **Layered PSD & SVG.** Every element on its own layer — finish in Photoshop, free Photopea or Figma (SVG keeps live text).
- 🌍 **Any language.** Slides are written in the language of your topic.

**Made for:** indie hackers and developers marketing their own product without leaving the editor · SMM managers and agencies batching client content · creators turning videos and podcasts into carousels · small businesses posting from their own photos.

## Connect in a minute

The server is remote — nothing to install. Endpoint:

```
https://us-central1-contentum-97362.cloudfunctions.net/carousel/mcp
```

Your client opens a Uniscript sign-in page (OAuth) — approve access and you're in. Requires a Uniscript plan (Starter, Pro or Agency).

| Client | How |
|---|---|
| Claude (web / desktop) | Settings → Connectors → Add custom connector → paste the endpoint |
| ChatGPT | Settings → Apps & Connectors → Advanced settings → Developer mode → Create → paste the endpoint |
| Claude Code | `claude mcp add --transport http uniscript https://us-central1-contentum-97362.cloudfunctions.net/carousel/mcp` |
| Cursor | `~/.cursor/mcp.json` → `{"mcpServers":{"uniscript":{"url":"https://us-central1-contentum-97362.cloudfunctions.net/carousel/mcp"}}}` |
| Other clients | Remote MCP server, Streamable HTTP, the endpoint above |

No OAuth in your client? Get a personal link in the app — [carousel.uniscript.app](https://carousel.uniscript.app/) → profile menu → **Connect API** — and use it instead (or send `Authorization: Bearer usk_…`).

## Try saying

- “Make a carousel about 5 mistakes people make with home coffee.”
- “Turn this video into a carousel: https://www.tiktok.com/@…”
- “Make a promo carousel for my bakery from these photos.”
- “On slide 3 remove the number and make the title yellow.”
- “Give me the PSD files.”

## Tools

| Tool | What it does | Uses plan |
|---|---|---|
| `create_carousel` | Topic (+ optional `images`) → finished carousel. Returns slide URLs, every slide's layers and a preview image | 1 carousel |
| `create_carousel_from_video` | Video → carousel: a link, the file as base64 (≤20 MB) or `upload_id` (≤30 MB) | 1 carousel |
| `edit_carousel` | Layer edits: `hide` / `show`, `set_text`, `style` (`dx`/`dy`, `color`), `set_photo` (your image by URL or base64), `delete_slide`, `move_slide`, `duplicate_slide`, `insert_slide`; theme, layout, fonts. Saves a new version | free |
| `export_layers` | Layered PSD + SVG per slide | free |
| `get_carousel` | Slide URLs, layers with texts/visibility, preview | free |
| `list_carousels` | Your carousels, newest first | free |
| `generate_ideas` | Brainstorm ideas without building | free |
| `build_carousel` | Build a chosen idea | 1 carousel |
| `video_to_idea` | Video → idea only (then `build_carousel`) | free |
| `get_video_upload_url` | Upload URL for a video file up to 30 MB → `upload_id` | free |
| `upload_image` | Upload your own image → `photo_id` | free |
| `list_options` | Niches, themes, layouts, hook formulas, structures, hook styles, fonts, languages, layer names | free |
| `get_account` | Plan and carousels left | free |
| `get_payment_link` | Checkout page to buy or renew a plan | free |

Layers: `photo`, `kicker`, `title`, `body`, `number`, `pre`, `hero`, `accent`, `author`, `quote_mark`, `button`, `swipe_hint`, `divider`, `watermark`.

## Pricing

Included in every Uniscript plan: Starter $12/mo (40 carousels), Pro $35/mo (120), Agency $80/mo (300). Edits and exports are free (up to 150 a day).

## Privacy

Sign-in runs on Uniscript's own server; agents get a short-lived token tied to a pseudonymous account id — no email or password ever reaches the agent. Personal links are stored only as SHA-256 hashes and can be replaced anytime. Slide links are signed and expire after 30 days. [Privacy policy](https://uniscript.app/privacy_en.html).

## Links

- Website: https://uniscript.app/mcp/
- App: https://carousel.uniscript.app/
- Official MCP Registry: `app.uniscript/carousels`
- Support: uniscript@mail.ru
