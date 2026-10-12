---
name: tighten-typescript
description: Find unsafe TypeScript assumptions, weak compiler settings, and uncertainty hidden by casts. Use when this specific concern is requested in a frontend project, especially TypeScript and React.
---

# Tighten TypeScript

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Assess `strict`, `noUncheckedIndexedAccess`, and `exactOptionalPropertyTypes`. Handle absent array entries and optional values explicitly. Replace unjustified `any`, non-null assertions, and casts that hide uncertainty with accurate types or checks. Introduce compiler changes gradually when the existing backlog is large.

Baseline existing failures. Start noisy or broad new rules as warnings, focus cleanup on changed code, and track old debt separately. Promote checks that catch real bugs and tune or remove noise. Do not weaken sound project-wide typechecking merely to limit a scan to changed files.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.

## Provenance

Adapted from the user-provided frontend quality writeup beginning “Ten thousand lines of code in a week used to mean a team.” The source author and public URL were not supplied.
