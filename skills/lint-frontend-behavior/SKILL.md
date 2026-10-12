---
name: lint-frontend-behavior
description: Review frontend complexity, unnecessary React effects, test lint defects, and accessibility. Use when this specific concern is requested in a frontend project, especially TypeScript and React.
license: MIT
metadata:
  author: Prashant Singhal
---

# Lint frontend behavior

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Use existing tooling to find excessive complexity, identical branches, accidental nested control flow, and suspicious duplication. In React, remove effects used only to derive values or synchronize redundant state; retain effects that synchronize with external systems. Check assertion-free tests, focused tests, missing awaits in end-to-end assertions, and accessible markup. Relevant examples include SonarJS, effect-focused React linting, Vitest and Playwright ESLint plugins, and jsx-a11y. Respect existing conventions for exported return types, type definitions, filenames, and import aliases rather than imposing style rules as universal defect fixes. Complement static accessibility checks with rendered or composed UI checks when applicable.

Baseline existing failures. Start noisy or broad new rules as warnings, focus cleanup on changed code, and track old debt separately. Promote checks that catch real bugs and tune or remove noise. Do not weaken sound project-wide typechecking merely to limit a scan to changed files.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
