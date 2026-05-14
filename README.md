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

Codex will prompt you to authenticate. Ceramic uses **WorkOS OAuth** — you will be redirected to sign in/create an account. On success, an access token is issued containing your `org_id`, which is used to authorize requests to the Ceramic MCP server.

### Step 5 — Start using it

The `search` skill is now active in every Codex session. You do not need to invoke it manually — the agent calls it automatically whenever it needs current information from the web.

## Links

- [Ceramic documentation](https://docs.ceramic.ai)
- [Ceramic API reference](https://docs.ceramic.ai/api-reference/search)
- [Ceramic MCP server](https://docs.ceramic.ai/mcp/ceramic-mcp)
