# martynov-plugins

A Claude Code plugin marketplace.

## Install

```
/plugin marketplace add OleksandrMartynov/claude-plugins
/plugin install commit-helper@martynov-plugins
```

## Update

```
/plugin marketplace update martynov-plugins
```

## Plugins

| Plugin | Description |
|---|---|
| [commit-helper](plugins/commit-helper) | Writes Conventional Commits messages from your staged git changes. |

## Releasing a new version (maintainers)

1. Change the plugin under `plugins/<name>/`.
2. Bump `version` in `plugins/<name>/.claude-plugin/plugin.json`.
3. Commit, push to `main`, and optionally tag it (e.g. `commit-helper-v0.2.0`).
