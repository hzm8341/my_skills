# Global Configuration Files

This directory contains global configuration files for Claude Code and OpenCode AI assistants.

## Files

| File | Description |
|------|-------------|
| `CLAUDE.md` | Global behavior configuration for Claude Code (also works with OpenCode) |
| `config.json` | OpenCode default model configuration |
| `opencode.json` | OpenCode MCP servers, plugins, and provider settings |
| `oh-my-opencode.json` | OpenCode agent model configurations (Sisyphus, Oracle, etc.) |

## Usage

### Syncing to Local Machine

To apply these configurations to your local machine:

```bash
# Copy CLAUDE.md (works for both Claude Code and OpenCode)
cp global_configs/CLAUDE.md ~/.claude/CLAUDE.md

# Copy OpenCode configs
cp global_configs/config.json ~/.config/opencode/config.json
cp global_configs/opencode.json ~/.config/opencode/opencode.json
cp global_configs/oh-my-opencode.json ~/.config/opencode/oh-my-opencode.json
```

Or use symlinks:

```bash
# As symlinks (changes propagate automatically)
ln -s $(pwd)/global_configs/CLAUDE.md ~/.claude/CLAUDE.md
ln -s $(pwd)/global_configs/config.json ~/.config/opencode/config.json
ln -s $(pwd)/global_configs/opencode.json ~/.config/opencode/opencode.json
ln -s $(pwd)/global_configs/oh-my-opencode.json ~/.config/opencode/oh-my-opencode.json
```

## Notes

- **CLAUDE.md**: OpenCode has undocumented compatibility with Claude Code's CLAUDE.md - it reads `~/.claude/CLAUDE.md` automatically
- **OpenCode Configs**: These JSON files configure models, agents, and plugins
- The configs in this repo are the authoritative source - edit here, then sync to local machine
