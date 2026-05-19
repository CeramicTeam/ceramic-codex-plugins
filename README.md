# Ceramic Codex Plugins

Codex plugins for [Ceramic AI](https://docs.ceramic.ai). Install once, use across every project.

## Plugins

| Plugin | Description |
|--------|-------------|
| `ceramic-search` | High quality web search for AI agents using Ceramic |

## Installation

### Step 1 — Register the marketplace

```bash
codex plugin marketplace add CeramicTeam/ceramic-codex-plugins
```

This clones the repo and makes the plugins discoverable in Codex. The plugins are not installed yet.

### Step 2 — Install the plugin

Open the plugin directory:

- **Codex app** — click **Plugins** in the sidebar
- **Codex CLI** — type `/plugins`

Find `ceramic-search` under the **Ceramic AI Plugins** marketplace. Open it and select **Install plugin**. Codex should automatically open the **WorkOS OAuth** authorization page in your browser — sign in or create an account. The browser will show "Authentication complete. You may close this window."

If authentication completed, continue to **Step 4**. Otherwise, continue to **Step 3** to authenticate manually.

### Step 3 — Authenticate manually (fallback)

If the browser did not open automatically during install, run the following from a **new terminal outside of any Codex session**:

```bash
codex mcp login ceramic-search
```

Open the printed authorization URL in your browser and complete the flow. Your terminal will confirm `Successfully logged in to MCP server 'ceramic-search'`.

If your OAuth session expires re-run `codex mcp login ceramic-search` from a terminal outside of Codex.

### Step 4 — Start a new Codex session and use it

The `search` skill is now active in every Codex session. You do not need to invoke it manually — the agent calls it automatically whenever it needs current information from the web.

## Links

- [Ceramic documentation](https://docs.ceramic.ai)
- [Ceramic API reference](https://docs.ceramic.ai/api-reference/search)
- [Ceramic MCP server](https://docs.ceramic.ai/mcp/ceramic-mcp)
