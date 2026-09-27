# ORC8R plugin for Claude

Connect Claude to [ORC8R Cloud](https://orc8r.com) using the remote MCP server at `https://orc8r.com/mcp`. The plugin also includes a short skill for finding operations, inspecting their inputs, and reporting results.

## Install

### Claude.ai or Claude Desktop

1. Open **Customize → Plugins → Add → Add marketplace**.
2. Enter `https://github.com/admte/orc-claude-plugin`.
3. Add the **ORC8R** plugin from that marketplace.
4. Open the plugin's **Connectors** tab. Add or connect **orc8r**, then sign in to ORC8R and approve the OAuth scopes you want to grant. On Team and Enterprise plans, an Owner may need to add the connector for the organization first.

### Claude Code

```sh
claude plugin marketplace add admte/orc-claude-plugin
claude plugin install orc8r@orc-claude-plugin
```

Start a new Claude Code session, run `/mcp`, and authenticate `plugin:orc8r:orc8r` when prompted. You can then ask Claude about your ORC8R resources or run `/orc8r:manage-orc8r`.

## Access

ORC8R asks each user to sign in and approve access. The consent page always grants `orc:read`, which allows reads; tick `orc:write` to allow changes. ORC8R also applies the user's existing organization permissions. The plugin contains no API keys or user credentials.

See [ORC8R's MCP documentation](https://orc8r.com/docs/mcp) for available tools, scopes, and how to revoke a connection.

## Privacy

[Privacy](https://orc8r.com/privacy) explains how ORC8R handles data sent through its service.

## Self-hosted ORC8R

This plugin connects to ORC8R Cloud at `https://orc8r.com/mcp`. For a self-hosted ORC8R server, add `https://<your-server>/mcp` as a custom connector instead.

## Repository layout

- `plugins/orc8r/` — installable Claude plugin, including its MCP configuration and skill
- `.claude-plugin/marketplace.json` — marketplace catalog for installation from this repository

This public repository is a plugin source. It is not an Anthropic directory listing.
