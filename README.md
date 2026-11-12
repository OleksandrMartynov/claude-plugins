# martynov-plugins

A Claude Code plugin marketplace.

## Install

```
/plugin marketplace add OleksandrMartynov/claude-plugins
/plugin install commit-helper@martynov-plugins
```

## Update

Manually:

```
/plugin marketplace update martynov-plugins
```

Then run `/reload-plugins` (or restart Claude Code) to apply the new version.

Automatically: in Claude Code run `/plugin`, open the **Marketplaces** tab, select
`martynov-plugins` and choose **Enable auto-update**. Third-party marketplaces have it off by default.

## Plugins

| Plugin | Description |
|---|---|
| [commit-helper](plugins/commit-helper) | Writes Conventional Commits messages from your staged git changes. |

## Releasing a new version (maintainers)

1. Change the plugin under `plugins/<name>/`.
2. Bump `version` in `plugins/<name>/.claude-plugin/plugin.json`.
3. Commit, push to `main`, and optionally tag it (e.g. `commit-helper-v0.2.0`).
