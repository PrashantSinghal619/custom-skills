# Custom Skills

A growing collection of reusable AI skills by [Prashant Singhal](https://github.com/PrashantSinghal619).

## Available skills

- [cut-frontend-slop](skills/cut-frontend-slop/SKILL.md) — Audit frontend assumptions, architectural drift, weak tests, dead code, and duplicate logic; roll out useful safeguards gradually.

Invoke `/cut-frontend-slop` in an agent that supports skill slash commands. This repository also routes that literal request through `AGENTS.md`. Codex supports explicit invocation as `$cut-frontend-slop` after installation; command-menu behavior depends on the client.

For Codex, copy `skills/cut-frontend-slop` into your user-level `~/.agents/skills/` directory, or into `.agents/skills/` in a target project. Reload skills or restart the session if needed. See the [official skill documentation](https://learn.chatgpt.com/docs/build-skills).

## Planned skills

- `skills/humanize-copy/SKILL.md` — Humanize AI copywriting.
- `skills/project-grill/SKILL.md` — Test project knowledge, brainstorm use cases and edge cases, clarify direction, and identify gaps.

The planned skill files are intentionally empty and are not usable skills yet. Additional skill content will be added only with the owner's explicit approval.

Distribution through npm skills is planned. Nothing has been published to npm yet.

## Reuse and credit

Licensed under the [MIT License](LICENSE). Retain the copyright and license notice when redistributing. If this collection helps you, a link back to this repository is appreciated.
