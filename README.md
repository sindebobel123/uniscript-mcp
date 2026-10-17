# Uniscript MCP — AI carousel maker for TikTok & Instagram

Let your AI agent (Claude, ChatGPT, Codex, Cursor, any MCP client) create finished carousel posts and edit them **layer by layer** — then export layered **PSD** and **SVG** for Photoshop, Photopea and Figma.

<p><img src="assets/mcp_01.webp" width="160"> <img src="assets/mcp_02.webp" width="160"> <img src="assets/mcp_03.webp" width="160"> <img src="assets/mcp_04.webp" width="160"></p>

*Slide 3 after `edit_carousel`: number hidden, title recolored.*

Uniscript does the actual work — idea, slide texts, photos (5,000+ for 42 niches), rendering — with the same engine as the [Uniscript app](https://uniscript.app). Your agent is the remote control.

- 🌐 Website: https://uniscript.app/mcp/
- 🧩 Transport: remote MCP, Streamable HTTP (no install)
- 🖼 Output: 1080×1920 PNG slides, layered PSD, SVG with live text
- 💳 Included in every paid plan (from $12/month) · edits and exports never use your plan

## Connect

1. Get a subscription at **[carousel.uniscript.app](https://carousel.uniscript.app/)**, then profile menu → **Connect API** → **Get my link**.
   The link looks like `https://us-central1-contentum-97362.cloudfunctions.net/carousel/mcp/usk_…` — it works like a password, keep it private.
2. Add it to your client:

| Client | How |
|---|---|
| Claude (web / desktop) | Settings → Connectors → Add custom connector → paste the link |
| ChatGPT | Settings → Apps & Connectors → Advanced settings → Developer mode → Create → paste the link |
| Claude Code | `claude mcp add --transport http uniscript YOUR_LINK` |
| Cursor | `~/.cursor/mcp.json` → `{"mcpServers":{"uniscript":{"url":"YOUR_LINK"}}}` |
| Other clients | Remote MCP server, Streamable HTTP, URL = your link |

Prefer a header? Use the URL without the key (`…/carousel/mcp`) and send `Authorization: Bearer usk_…`.

## Tools

| Tool | What it does | Uses plan |
|---|---|---|
| `create_carousel` | Topic in → finished carousel out (idea, texts, photos, render). Returns slide URLs, every slide's layers and a preview image | 1 carousel |
| `create_carousel_from_video` | Video → carousel with its key points: a link (TikTok, Reels, Shorts, VK, RuTube…), the file as base64 (≤20 MB) or `upload_id` (≤30 MB) | 1 carousel |
| `get_video_upload_url` | Upload URL for a video file up to 30 MB (`curl -F video=@clip.mp4 URL`) → `upload_id` | free |
| `video_to_idea` | Video (link / file) → idea only (then `build_carousel`) | free |
| `edit_carousel` | Layer edits: `hide` / `show`, `set_text`, `style` (move `dx`/`dy`, `color`), `set_photo` (your image by URL or base64), `delete_slide`, `move_slide`, `duplicate_slide`, `insert_slide`; plus theme, layout, fonts. Saves a new version | free |
| `export_layers` | Layered PSD + SVG per slide | free |
| `get_carousel` | Slide URLs, layers with texts/visibility, preview | free |
| `list_carousels` | Your carousels, newest first | free |
| `generate_ideas` | Brainstorm ideas without building | free |
| `build_carousel` | Build a chosen idea | 1 carousel |
| `upload_image` | Upload your own image → `photo_id` | free |
| `list_options` | Niches, themes, layouts, hook formulas, structures, hook styles, fonts, languages, layer names | free |
| `get_account` | Plan and carousels left | free |
| `get_payment_link` | Checkout page to buy or renew a plan (works without an active plan) | free |

`create_carousel` and `build_carousel` also take `images` (your own photos by URL or base64) — the carousel is built from them, like “Your photos” in the app.

Layers: `photo`, `kicker`, `title`, `body`, `number`, `pre`, `hero`, `accent`, `author`, `quote_mark`, `button`, `swipe_hint`, `divider`, `watermark`.

## Example

> **You:** Make a carousel about 5 coffee mistakes at home
> **Agent:** `create_carousel` → 6 slides
> **You:** On slide 3 remove the number and make the title yellow
> **Agent:** `edit_carousel` → `[{"op":"hide","slide":3,"layer":"number"},{"op":"style","slide":3,"layer":"title","color":"#FFD400"}]`
> **You:** Give me a PSD
> **Agent:** `export_layers` → 6 PSD + 6 SVG

## Pricing

The API is included in every subscription: Starter $12/mo (40 carousels), Pro $35/mo (120), Agency $80/mo (300). Edits and exports are free (up to 150 per day).

## Privacy

The link is stored only as a SHA-256 hash; create a new link anytime and the old one stops working. Slide links are signed and expire after 30 days. [Privacy policy](https://uniscript.app/privacy_en.html).

## Support

uniscript@mail.ru
