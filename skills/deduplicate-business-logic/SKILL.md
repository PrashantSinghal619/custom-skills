---
name: deduplicate-business-logic
description: Find textual and semantic copies of business rules that could diverge. Use when this specific concern is requested in a frontend project, especially TypeScript and React.
license: MIT
metadata:
  author: Prashant Singhal
---

# Deduplicate business logic

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Search for both textual and semantic copies of business rules. jscpd can help with textual duplication but cannot prove semantic uniqueness. Treat repeated markup, fixtures, and business logic differently. Consolidate when copies represent the same rule and could diverge; do not create premature abstractions just to remove similar-looking JSX.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
