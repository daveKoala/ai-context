# ai-context

My personal context and skills for AI coding tools.

## Contents

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Core context, loaded in every session: role, working style, expectations, safety, communication. |
| `skills/investigate/` | Debugging and root-cause investigation workflow. |
| `skills/feature-change/` | Feature and change workflow with a Draft, Ready, Done change document. |
| `skills/security-review/` | Security review method with confidence levels for findings. |
| `skills/writing/` | Messages, tickets and documents for other people. |
| `templates/project-CLAUDE.md` | Starting point for a project-level `CLAUDE.md`. Fill it in inside the private project repo. |

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
