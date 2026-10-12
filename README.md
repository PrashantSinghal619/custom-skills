# Custom Skills

A growing collection of reusable AI skills by [Prashant Singhal](https://github.com/PrashantSinghal619).

## Available skills

Use `/cut-frontend-slop` to run the full frontend quality set, or choose an individual concern below. With no mode specified, each invocation starts with an audit; add a scope and `review`, `cleanup`, or a tooling request to guide the work.

| Command | Purpose |
| --- | --- |
| [/cut-frontend-slop](skills/cut-frontend-slop/SKILL.md) | Coordinate all ten concerns and consolidate findings |
| [/verify-api-contracts](skills/verify-api-contracts/SKILL.md) | Verify API contracts |
| [/tighten-typescript](skills/tighten-typescript/SKILL.md) | Tighten TypeScript |
| [/lint-frontend-behavior](skills/lint-frontend-behavior/SKILL.md) | Lint frontend behavior |
| [/enforce-layer-boundaries](skills/enforce-layer-boundaries/SKILL.md) | Enforce layer boundaries |
| [/codify-recurring-bugs](skills/codify-recurring-bugs/SKILL.md) | Codify recurring bugs |
| [/guide-frontend-agents](skills/guide-frontend-agents/SKILL.md) | Guide frontend agents |
| [/strengthen-test-behavior](skills/strengthen-test-behavior/SKILL.md) | Strengthen test behavior |
| [/prune-dead-code](skills/prune-dead-code/SKILL.md) | Prune dead code |
| [/deduplicate-business-logic](skills/deduplicate-business-logic/SKILL.md) | Deduplicate business logic |
| [/gate-frontend-quality](skills/gate-frontend-quality/SKILL.md) | Gate frontend quality |

Slash commands work in clients that support skill slash invocation. This repository also routes these literal requests through `AGENTS.md`. Codex supports explicit `$skill-name` invocation after installation; command-menu behavior depends on the client.

For Codex, copy all eleven populated skill folders from `skills/` into `~/.agents/skills/`, or into `.agents/skills/` in a target project. Keep them as siblings so the coordinator can resolve its dependencies. For an individual concern, install just that skill; it is self-contained. Leave the empty planned placeholders uninstalled. Reload skills or restart the session if needed. See the [official skill documentation](https://learn.chatgpt.com/docs/build-skills).

## Planned skills

- `skills/humanize-copy/SKILL.md` — Humanize AI copywriting.
- `skills/project-grill/SKILL.md` — Test project knowledge, brainstorm use cases and edge cases, clarify direction, and identify gaps.

The planned skill files are intentionally empty and are not usable skills yet. Additional skill content will be added only with the owner's explicit approval.

Distribution through npm skills is planned. Nothing has been published to npm yet.

## Reuse and credit

Licensed under the [MIT License](LICENSE). Retain the copyright and license notice when redistributing. If this collection helps you, a link back to this repository is appreciated.
