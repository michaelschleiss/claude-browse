# claude-browse

Browse Claude Code conversation history from your terminal.

## Install

```bash
# Clone and symlink
git clone https://github.com/michaelschleiss/claude-browse.git
ln -s "$(pwd)/claude-browse/claude-browse" ~/.local/bin/claude-browse

# Or just copy the script
curl -o ~/.local/bin/claude-browse https://raw.githubusercontent.com/michaelschleiss/claude-browse/main/claude-browse
chmod +x ~/.local/bin/claude-browse
```

Requires Python 3.7+ (no dependencies).

## Usage

```bash
claude-browse              # pick from conversations in current project
claude-browse --all        # pick from all projects
claude-browse file.jsonl   # browse a specific conversation file
```

## Controls

| Key | Action |
|-----|--------|
| `j` | Older message |
| `k` | Newer message |
| `d` | Scroll down (half page) |
| `u` | Scroll up (half page) |
| `q` | Quit |

## How it works

Claude Code stores conversation transcripts as JSONL files in `~/.config/claude/projects/`. This tool reads those files and presents user/assistant message pairs in an interactive TUI.

The project directory is automatically resolved from your current working directory, with fuzzy matching to handle path encoding differences.
