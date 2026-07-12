# Vertiso Memory for Cursor

Official Cursor plugin for Vertiso Memory: add the remote, user-owned memory MCP
server plus the session skills in one step. Durable recall, hybrid search, and
cross-session handoffs and checkpoints, with browser OAuth and no API key to
paste.

> This repository is **generated** and published automatically from the Vertiso
> Memory source repository. The `vertiso-memory/` plugin and
> `.cursor-plugin/marketplace.json` are overwritten on every publish, so do not
> hand-edit them. This `README.md` and `LICENSE` are seeded once and then
> maintained here by hand.

## Install

Add the remote server directly:

```json
{ "mcpServers": { "vertiso-memory": { "url": "https://memory.vertiso.ai/mcp" } } }
```

A bare URL is sufficient: Cursor reads the protected-resource metadata, runs
Dynamic Client Registration, and prompts the browser sign-in. The install page
at https://memory.vertiso.ai/docs/install carries an "Add to Cursor" deeplink.

The bundled `vertiso-memory/` plugin (MCP config + the four session skills) is
for the Cursor marketplace / Open Plugins path.

## License

MIT. See [LICENSE](LICENSE). Copyright (c) 2026 Vertiso Corporation.

## Documentation

Full install and connection docs: https://memory.vertiso.ai/docs/install
