# astra-marketplace

Central registry for the astra family of Claude Code plugins.

This repo contains exactly one source of truth — `.claude-plugin/marketplace.json` — listing every plugin and pointing at its own source repo. Plugin code lives elsewhere.

## Install

```
/plugin marketplace add astragenie/astra-marketplace
/plugin install crew@astra
/plugin install runner@astra
/plugin install memory@astra
```

Add only the plugins you want.

## Current plugins

| Plugin   | Repo                                                       | Purpose |
|----------|------------------------------------------------------------|---------|
| `crew`   | [astragenie/dev-team](https://github.com/astragenie/dev-team)     | Lead-guided engineering workflow, bounded subagents, quality gates |
| `runner` | [astragenie/runner-plugin](https://github.com/astragenie/runner-plugin)               | Spec-driven agentic dev engine — PM-triaged backlog, slice-scoped specs, parallel waves, phase-gate quality + review + validation |
| `memory` | [astragenie/memory-plugin](https://github.com/astragenie/memory-plugin) | Slash commands + auto-capture hooks bridging Claude Code to the AstraMemory service |

## Releasing a new plugin version

1. Cut a release in the plugin's source repo (e.g. bump `plugin.json`).
2. Open a PR here updating `version` in `.claude-plugin/marketplace.json`.
3. Merge → users see the new version on next `/plugin marketplace update`.

## Adding a new plugin

1. Push the plugin to its own GitHub repo with a `plugin.json` at root.
2. Add a new entry to `plugins[]` in `.claude-plugin/marketplace.json` with `name`, `description`, `version`, `source.repo`, and `author`.
3. Merge.
