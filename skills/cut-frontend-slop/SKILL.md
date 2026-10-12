---
name: cut-frontend-slop
description: Audit and reduce maintenance risks in frontend codebases, especially TypeScript and React, including guessed API shapes, unnecessary effects, architectural drift, weak tests, dead code, and duplicate logic. Use for frontend slop reviews, targeted cleanup, or gradual quality-check rollout; not visual redesign or copywriting.
---

# Cut frontend slop

Make frontend code safer to trust and cheaper to review. Prevent unsupported assumptions, find accumulated waste, and enforce checks that catch real defects. Apply the categories to the project's stack; TypeScript and React are the primary context.

## Establish scope once

Read project instructions, package scripts, compiler and lint configuration, API contracts, tests, and CI. Inspect the requested files or diff first; for a general invocation, audit representative entry points and important data flows. Search for existing helpers before introducing replacements.

Follow the requested mode: a review produces findings; a cleanup implements scoped fixes; a tooling request adds appropriate safeguards. If no mode is given, start with an audit and prioritized recommendations. Keep behavior and the project's architecture intact unless the requested fix requires a change. Do not install the entire tool list or rewrite the repository to satisfy it.

## Run the set

This is the coordinator for ten independently reusable skills. Apply all ten concerns to the requested frontend scope. Inspect project context once, then read each linked skill and perform its relevant checks in the order below. Carry the same requested mode and scope through every skill; do not silently turn an audit into implementation. Run sequentially in the current session; separate agents are not required.

The coordinator and these skill folders must be installed together as siblings. Resolve links relative to this file, not the target project's working directory. If a dependency is missing, report which concern could not run rather than claiming a complete audit.

| Individual command | Concern | Instructions |
| --- | --- | --- |
| `/verify-api-contracts` | Verify API contracts | [verify-api-contracts](../verify-api-contracts/SKILL.md) |
| `/tighten-typescript` | Tighten TypeScript | [tighten-typescript](../tighten-typescript/SKILL.md) |
| `/lint-frontend-behavior` | Lint frontend behavior | [lint-frontend-behavior](../lint-frontend-behavior/SKILL.md) |
| `/enforce-layer-boundaries` | Enforce layer boundaries | [enforce-layer-boundaries](../enforce-layer-boundaries/SKILL.md) |
| `/codify-recurring-bugs` | Codify recurring bugs | [codify-recurring-bugs](../codify-recurring-bugs/SKILL.md) |
| `/guide-frontend-agents` | Guide frontend agents | [guide-frontend-agents](../guide-frontend-agents/SKILL.md) |
| `/strengthen-test-behavior` | Strengthen test behavior | [strengthen-test-behavior](../strengthen-test-behavior/SKILL.md) |
| `/prune-dead-code` | Prune dead code | [prune-dead-code](../prune-dead-code/SKILL.md) |
| `/deduplicate-business-logic` | Deduplicate business logic | [deduplicate-business-logic](../deduplicate-business-logic/SKILL.md) |
| `/gate-frontend-quality` | Gate frontend quality | [gate-frontend-quality](../gate-frontend-quality/SKILL.md) |

Skip only concerns that do not apply to the target stack or scope, and explain those exclusions. Deduplicate overlapping findings and recommendations. Prefer a trustworthy API contract, meaningful behavioral tests, and enforcement of adopted checks when resources are limited. Do not install every example tool.

## Roll out proportionately

Baseline existing failures. Start new lint rules as warnings and focus cleanup on changed code; track historical debt separately. Run typechecking with the scope needed to remain sound. Promote rules that catch real bugs, tune or remove noisy ones, and add CI gates after the checks stabilize. Never silence violations or expand ignore lists simply to get green results.

Review disables, ignores, and stale rules periodically. Explain why each rule exists and how to fix its failures. Match investment to code lifetime, team size, and consequences of defects. When starting small, prioritize a trustworthy API contract, meaningful tests with selective mutation analysis, and enforcement of the checks the project adopts.

## Verify and report

Run the relevant existing checks after changes and add behavioral tests for meaningful fixes. State what ran, what failed, and what remains unverified. For each actionable finding, give a file location, concrete risk or behavior, evidence, and the smallest useful fix; separate observed defects from tooling suggestions. Summarize applied changes and remaining decisions.

Human review still owns feature correctness, state placement, premature abstractions, and competing implementations of the same idea. A green suite proves only that its checks found no targeted failures; it does not prove understanding or product correctness.

## Provenance

Condensed and adapted from the user-provided writeup beginning “Ten thousand lines of code in a week used to mean a team.” The source author and public URL were not supplied. Tool names are examples from that writeup; verify current compatibility against official documentation before adding them to a project.
