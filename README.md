# Elias's Claude Plugins

My personal collection of [Claude Code](https://docs.anthropic.com/en/docs/claude-code) plugins. I built these to make working with multiple Claude sessions less painful - managing pools, tracking intentions, cycling between idle sessions. They've become essential to my daily workflow and I'm sharing them in case they're useful to others.

## What is a plugin marketplace?

Claude Code's plugin system lets tools add hooks, skills, and configuration to your sessions. A marketplace is a registry that Claude Code can pull from — you point it at a GitHub repo, then install individual plugins by name. This repo is one such registry.

## Plugins

| Plugin | What it does |
|--------|-------------|
| [Open Cockpit](https://github.com/EliasSchlie/open-cockpit) | Electron app + plugin for orchestrating Claude sessions through a shared pool. Sidebar, intention tracking, idle detection, agent API. |
| [Sub-Claude](https://github.com/EliasSchlie/sub-claude) | Tmux-backed pool of persistent Claude sessions. Fire-and-forget parallel work from the terminal. |
| [Claude Next Idle](https://github.com/EliasSchlie/claude-next-idle) | Keyboard shortcut to jump to your next idle Claude session. LIFO stack, works with iTerm + Cursor. |
| [Claude Term](https://github.com/EliasSchlie/claude-term) | Persistent terminal management — spawn, read, write, and kill terminals that survive session disconnects. |
| [Claude Pool](https://github.com/EliasSchlie/claude-pool) | Managed pools of Claude Code sessions — spawn, offload, restore, prompt, attach. Standalone daemon, no Electron required. |

## Install

Add the marketplace, then install whichever plugins you need:

```bash
# Add this marketplace
claude plugin marketplace add EliasSchlie/claude-plugins

# Pick what you need
claude plugin install open-cockpit@elias-tools
claude plugin install sub-claude@elias-tools
claude plugin install claude-next-idle@elias-tools
```

## Troubleshooting

**"Permission denied (publickey)" during install**

Claude Code clones plugin repos via SSH by default. If you don't have SSH keys set up for GitHub, installation will fail. Fix by telling git to use HTTPS:

```bash
git config --global url."https://github.com/".insteadOf git@github.com:
```

To revert later (e.g., after setting up SSH keys):

```bash
git config --global --unset url."https://github.com/".insteadOf
```

## Contributing

Want to add a plugin? Open a PR that adds your entry to `.claude-plugin/marketplace.json` with a `name`, `source`, `description`, and `version`.

## License

[MIT](LICENSE)
