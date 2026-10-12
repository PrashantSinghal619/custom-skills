# Custom Skills

A growing collection of reusable AI skills by [Prashant Singhal](https://github.com/PrashantSinghal619).

## Available skills

Install `cut-frontend-slop` to run the full frontend quality set, or choose an individual concern below. With no mode specified, each invocation starts with an audit; add a scope and `review`, `cleanup`, or a tooling request to guide the work.

| Skill | Purpose |
| --- | --- |
| [cut-frontend-slop](skills/cut-frontend-slop/SKILL.md) | Coordinate all ten concerns and consolidate findings |
| [verify-api-contracts](skills/verify-api-contracts/SKILL.md) | Verify API contracts |
| [tighten-typescript](skills/tighten-typescript/SKILL.md) | Tighten TypeScript |
| [lint-frontend-behavior](skills/lint-frontend-behavior/SKILL.md) | Lint frontend behavior |
| [enforce-layer-boundaries](skills/enforce-layer-boundaries/SKILL.md) | Enforce layer boundaries |
| [codify-recurring-bugs](skills/codify-recurring-bugs/SKILL.md) | Codify recurring bugs |
| [guide-frontend-agents](skills/guide-frontend-agents/SKILL.md) | Guide frontend agents |
| [strengthen-test-behavior](skills/strengthen-test-behavior/SKILL.md) | Strengthen test behavior |
| [prune-dead-code](skills/prune-dead-code/SKILL.md) | Prune dead code |
| [deduplicate-business-logic](skills/deduplicate-business-logic/SKILL.md) | Deduplicate business logic |
| [gate-frontend-quality](skills/gate-frontend-quality/SKILL.md) | Gate frontend quality |

## Structure and installation

This collection follows the [Agent Skills specification](https://agentskills.io/specification), used by the [skills CLI](https://github.com/vercel-labs/skills). Each skill has YAML frontmatter (`name` and `description`) followed by agent instructions in `SKILL.md`. Supporting instructions live in `references/` only where needed. The coordinator bundles all ten concerns and can be installed alone; every individual skill is self-contained.

```text
skills/
  cut-frontend-slop/
    SKILL.md
    references/
      verify-api-contracts.md
      ...
  verify-api-contracts/
    SKILL.md
  ...
planned/
  humanize-copy/SKILL.md
  project-grill/SKILL.md
```

List the available skills:

```sh
npx skills add PrashantSinghal619/custom-skills --list
```

Install the full workflow, or one concern:

```sh
npx skills add PrashantSinghal619/custom-skills --skill cut-frontend-slop
npx skills add PrashantSinghal619/custom-skills --skill verify-api-contracts
```

Invocation is provided by the receiving agent. Use `/cut-frontend-slop` where skill slash commands are supported, or the client's equivalent skill invocation. The Agent Skills format itself does not register slash commands.

## Planned skills

- `planned/humanize-copy/SKILL.md` — Humanize AI copywriting.
- `planned/project-grill/SKILL.md` — Test project knowledge, brainstorm use cases and edge cases, clarify direction, and identify gaps.

The planned skill files are intentionally empty and are not usable skills yet. Additional skill content will be added only with the owner's explicit approval.

The GitHub collection is compatible with the npm-distributed `skills` CLI. This repository has not been published as a separate npm package.

See [SOURCES.md](SOURCES.md) for the provenance of the frontend guidance.

## Reuse and credit

Licensed under the [MIT License](LICENSE). Retain the copyright and license notice when redistributing. If this collection helps you, a link back to this repository is appreciated.
