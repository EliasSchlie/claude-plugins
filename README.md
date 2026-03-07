# Claude Plugins Marketplace

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugin marketplace for session management and productivity tools.

## Plugins

| Plugin | Description |
|--------|-------------|
| [open-cockpit](https://github.com/EliasSchlie/open-cockpit) | Session intention tracking, idle detection, and PID mapping for the Open Cockpit app |
| [sub-claude](https://github.com/EliasSchlie/sub-claude) | Session-oriented pool of persistent Claude TUI slots backed by tmux |
| [claude-next-idle](https://github.com/EliasSchlie/claude-next-idle) | Detects idle Claude sessions for keyboard-shortcut cycling |

## Install

### Add the marketplace

```bash
claude plugin marketplace add EliasSchlie/claude-plugins
```

### Install individual plugins

```bash
# Open Cockpit — session tracking for the Open Cockpit desktop app
claude plugin install open-cockpit@elias-tools

# Sub-Claude — tmux-backed pool of persistent Claude sessions
claude plugin install sub-claude@elias-tools

# Claude Next Idle — cycle to the next idle Claude session
claude plugin install claude-next-idle@elias-tools
```

## Contributing

Want to add a plugin to this marketplace? Open a PR that adds your plugin entry to `.claude-plugin/marketplace.json`.

Each plugin entry needs:
- `name` — unique plugin identifier
- `source` — `{ "source": "github", "repo": "owner/repo" }`
- `description` — short one-liner
- `version` — semver string matching the version in your plugin's `.claude-plugin/plugin.json`

## License

[MIT](LICENSE)
