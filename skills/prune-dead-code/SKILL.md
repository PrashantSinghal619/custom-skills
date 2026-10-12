---
name: prune-dead-code
description: Find unreachable frontend code, unused exports and dependencies, and stale test mocks. Use when this specific concern is requested in a frontend project, especially TypeScript and React.
license: MIT
metadata:
  author: Prashant Singhal
---

# Prune dead code

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Use an existing detector or Knip to identify unused files, exports, and dependencies. Review ignored paths and verify entry points, dynamic imports, framework discovery, generated files, and public exports before deleting anything. Check mock paths and factory exports against real modules, accounting for partial mocks. Add a repository-specific reachability or mock detector only for a demonstrated gap. Test custom detectors with known positive and negative fixtures, including aliases and a deliberately unreachable file.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
