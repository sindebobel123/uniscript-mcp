# Installing the Uniscript MCP server (for AI agents)

Uniscript is a **remote** MCP server — nothing to clone, build or run locally.

1. Ask the user for their Uniscript connection link. They get it at https://carousel.uniscript.app → profile menu → **Connect API** → **Get my link** (requires a Starter, Pro or Agency plan). It looks like:
   `https://us-central1-contentum-97362.cloudfunctions.net/carousel/mcp/usk_…`
2. Add it as a remote server (Streamable HTTP). For Cline, in `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "uniscript": {
      "type": "streamableHttp",
      "url": "https://us-central1-contentum-97362.cloudfunctions.net/carousel/mcp/usk_YOUR_KEY"
    }
  }
}
```

   Alternative: URL without the key (`…/carousel/mcp`) plus header `Authorization: Bearer usk_YOUR_KEY`.
3. Check it: call `get_account` — it returns the plan and carousels left.
4. Try: `create_carousel` with `{"topic": "5 coffee mistakes at home"}`, then `edit_carousel` / `export_layers`.

The link is a secret (it acts as the user). Never print it in full or commit it.
