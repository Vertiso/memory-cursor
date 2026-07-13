# Vertiso Memory for Cursor

Official Cursor plugin for Vertiso Memory: add the remote, user-owned memory MCP
server plus the session skills in one step. Durable recall, hybrid search, and
cross-session handoffs and checkpoints, with browser OAuth and no API key to
paste.

> This repository is **generated** and published automatically from the Vertiso
> Memory source repository. The `vertiso-memory/` plugin and
> `.cursor-plugin/marketplace.json` are overwritten on every publish. The root
> `README.md` and `LICENSE` are generated too, so make changes upstream.

## Install the full plugin

After marketplace publication, open Cursor and run:

```text
/add-plugin vertiso-memory
```

This installs the remote MCP configuration and all four session skills:
`checkpoint`, `handoff`, `handoff-resume`, and `wrap-up`.

For pre-publication testing from a fresh clone of this repository, copy the
plugin payload into Cursor's local plugin directory:

```bash
mkdir -p ~/.cursor/plugins/local
cp -R vertiso-memory ~/.cursor/plugins/local/vertiso-memory
```

Use a physical copy. Cursor rejects a symlink whose target is outside its local
plugin directory. Restart Cursor or run **Developer: Reload Window**.

## Manifest compatibility

Cursor reads `vertiso-memory/.cursor-plugin/plugin.json`. The matching
`vertiso-memory/.plugin/plugin.json` file is a compatibility copy for tooling
that implements the vendor-neutral Open Plugins layout. The two files are
intentionally byte-for-byte identical, and the upstream release checks reject
any drift between them. Make manifest changes only in the canonical source
repository; both generated copies are overwritten on publish.

## Memory and privacy

Vertiso Memory stores information you choose to preserve for future recall. When
you invoke `checkpoint`, `handoff`, or `wrap-up`, you ask your AI client to
send selected conversation and work context to Vertiso Memory. Captures may
include attributed verbatim excerpts when exact wording matters.

The marketplace plugin does not automatically upload complete conversations and
does not install a pre-compaction transcript hook. After you invoke a memory
skill, it completes the requested capture without asking you to approve each
individual excerpt.

You can review, export, archive, and permanently delete stored memories at
https://memory.vertiso.ai. Memory skills are instructed to strip detected
secrets before composing a capture and never echo them back, but automated
detection can miss sensitive material. Do not share passwords, API keys,
authentication tokens, payment information, illegal or illicit materials, or
information you are not authorized to store. Use appropriate judgment before
including confidential, private, sensitive, or third-party information.

Full memory-handling and control details:
https://memory.vertiso.ai/trust

## MCP-only fallback

MCP only; bundled skills not included. Put this configuration in
`~/.cursor/mcp.json` for your user or `.cursor/mcp.json` for one project:

```json
{ "mcpServers": { "vertiso-memory": { "url": "https://memory.vertiso.ai/mcp" } } }
```

A bare URL is sufficient: Cursor reads the protected-resource metadata, runs
Dynamic Client Registration, and prompts the browser sign-in. The "Add to
Cursor" deeplink at https://memory.vertiso.ai/docs/install is this same
MCP-only fallback.

## Availability

Available worldwide except where prohibited by applicable law or unsupported
by our service providers.

## License

MIT. See [LICENSE](LICENSE). Copyright (c) 2026 Vertiso Corporation.

## Documentation

Full install and connection docs: https://memory.vertiso.ai/docs/install

## Support

Account, authentication, and deletion help:
https://memory.vertiso.ai/support

Security policy and private vulnerability reporting:
https://memory.vertiso.ai/security
