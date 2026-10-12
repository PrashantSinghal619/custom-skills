---
name: enforce-layer-boundaries
description: Review dependency direction and prevent frontend architectural drift. Use when this specific concern is requested in a frontend project, especially TypeScript and React.
license: MIT
metadata:
  author: Prashant Singhal
---

# Enforce layer boundaries

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Infer the intended dependency direction before enforcing it. Typical boundaries keep services independent of UI, shared utilities free of domain-specific behavior, design-system components independent of application state and API calls, production code free of test mocks, and routing focused on route-to-page mapping. Check framework conventions before applying these examples. Use the existing boundary tool or a suitable one, such as dependency-cruiser or ESLint boundaries. Diagnostics should explain the reason and where the dependency belongs.

Baseline existing failures. Start noisy or broad new rules as warnings, focus cleanup on changed code, and track old debt separately. Promote checks that catch real bugs and tune or remove noise. Do not weaken sound project-wide typechecking merely to limit a scan to changed files.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
