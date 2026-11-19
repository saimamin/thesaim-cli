<div align="center">

# The Saim CLI

**An AI coding agent — your own fork, your own backend, your own data.**

Powered by [The Saim](https://thesaim.xyz)

</div>

---

The Saim CLI is a rebranded fork of the MIT-licensed [OpenCode](https://github.com/anomalyco/opencode) project. It is feature-identical to upstream: terminal agent (CLI/TUI), web app, and desktop app, backed by your own locally hosted service and SQLite database.

## Why this fork

- **Your name, your tool** — the command is `thesaim`, and product branding is "The Saim CLI".
- **Your own backend** — runs a local background service that owns sessions, configuration, plugins, permissions, and tool execution.
- **Your own database** — all state lives in `~/.local/share/thesaim/`, fully isolated from any upstream OpenCode installation.
- **Your own hosting** — the web and desktop surfaces connect to the service you run yourself.
- **MIT licensed** — fork, modify, and distribute freely (keep the license notice).

## Data locations

All paths are namespaced to `thesaim` (see `packages/util/src/global.ts`):

| Kind | Path |
| --- | --- |
| Database | `~/.local/share/thesaim/opencode.db` |
| Config | `~/.config/thesaim/` |
| Cache | `~/.cache/thesaim/` |
| State | `~/.local/state/thesaim/` |
| Logs | `~/.local/share/thesaim/log/` |

Set `THESAIM_DB` to override the database filename/path (alias of `OPENCODE_DB`).

## Run locally

Prerequisites: [Bun](https://bun.sh) 1.4.4+ (the workspace package manager).

```bash
bun install

# Terminal agent
./bin/thesaim --help
./bin/thesaim

# Web app (dev server)
bun run dev:web

# Desktop app (dev)
bun run dev:desktop
```

The first CLI run starts the shared background service automatically. Check it with `./bin/thesaim service status`.

## Upstream attribution

This project is derived from [anomalyco/opencode](https://github.com/anomalyco/opencode), MIT licensed:

```
MIT License
Copyright (c) 2025 opencode
```

Rebranding changes: product name, command name, package metadata, user-facing strings, and the global data-path namespace. Internal workspace package scopes (`@opencode/*`) and `OPENCODE_*` constants are intentionally preserved to keep the upstream build and generated clients sound.

See [LICENSE](./LICENSE) for the full license text.

---

© 2026 The Saim — https://thesaim.xyz
