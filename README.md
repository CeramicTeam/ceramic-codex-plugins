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

### Step 2 — Restart Codex

Required for the new marketplace to appear in the plugin directory.

### Step 3 — Install the plugin

Open the plugin directory:

- **Codex app** — click **Plugins** in the sidebar
- **Codex CLI** — start a session with `codex`, then type `/plugins`

Find `ceramic-search` under the **Ceramic AI Plugins** marketplace. Open it and select **Install plugin**.

### Step 4 — Authenticate with Ceramic

Open a **new terminal outside of any Codex session** and run:

```bash
codex mcp login ceramic-search
```

Open the printed authorization URL in your browser and complete the **WorkOS OAuth** flow — sign in or create an account. The browser will show "Authentication complete. You may close this window." and your terminal will confirm `Successfully logged in to MCP server 'ceramic-search'`.

> **Important:** do not run `codex mcp login` as a command inside a Codex session. Codex's sandbox blocks the OAuth callback server from binding to its port, causing the login to hang silently.

Sessions last a maximum of **7 days**, with a **2-day inactivity timeout**. When your session expires, re-run `codex mcp login ceramic-search` from a terminal outside of Codex.

### Step 5 — Start a new Codex session and use it

The `search` skill is now active in every Codex session. You do not need to invoke it manually — the agent calls it automatically whenever it needs current information from the web.

## Links

- [Ceramic documentation](https://docs.ceramic.ai)
- [Ceramic API reference](https://docs.ceramic.ai/api-reference/search)
- [Ceramic MCP server](https://docs.ceramic.ai/mcp/ceramic-mcp)
