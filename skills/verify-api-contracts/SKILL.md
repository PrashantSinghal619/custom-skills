---
name: verify-api-contracts
description: Find guessed frontend API fields, contract drift, and missing runtime response validation. Use when this specific concern is requested in a frontend project, especially TypeScript and React.
---

# Verify API contracts

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Prefer an authoritative, current OpenAPI specification and generated types/client/runtime schemas over independently handwritten response shapes. Hey API and Zod are examples, not dependencies required by this skill. Validate untrusted responses at runtime; compile-time types cannot establish their actual shape. Regenerate clients rather than editing generated files. If no trustworthy contract exists, report the gap and inspect actual responses or backend definitions; never invent fields or a supposedly authoritative spec.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.

## Provenance

Adapted from the user-provided frontend quality writeup beginning “Ten thousand lines of code in a week used to mean a team.” The source author and public URL were not supplied.
