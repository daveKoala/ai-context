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
| `CHANGELOG.md` | Versions, the reasoning behind this repo, and the variables that affect results. |
| `FINDINGS.md` | Record of whether the instructions are followed and whether they help. |
| `templates/project-CLAUDE.md` | Starting point for a project-level `CLAUDE.md`. Fill it in inside the private project repo. |

## Proportionality

Match the depth of investigation, documentation, planning and verification to the complexity, uncertainty and consequences of the task. Apply enough rigour to produce a reliable result, but avoid process, exploration or documentation that doesn't materially improve the outcome.

## Keeping it current

This is not a finished document. It needs regular assessment, because models change: a newer model may already do some of this by default, or may respond differently to the same instruction.

The question now is not what else to put in it. It is whether agents consistently follow it, and whether following it produces better results. Add a rule when an agent repeatedly does something unwanted, remove rules that make no observable difference, and test a change by comparing results with and without it.

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
