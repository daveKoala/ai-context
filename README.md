# ai-context

My personal context and skills for AI coding tools.

## Contents

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Core context, loaded in every session: role, working style, expectations, safety, communication. |
| `skills/investigate/` | Debugging and root-cause investigation workflow. |
| `skills/feature-change/` | Feature/change workflow with a Draft → Ready → Done change document. |

## Install (Claude Code)

```bash
git clone <this-repo-url> ~/ai-context
mkdir -p ~/.claude/skills
ln -s ~/ai-context/CLAUDE.md ~/.claude/CLAUDE.md
ln -s ~/ai-context/skills/* ~/.claude/skills/
```

Symlinks mean a `git pull` updates everything.

## Other tools

For Codex, Cursor and other tools that read `AGENTS.md`, symlink or copy `CLAUDE.md` as `AGENTS.md`.
