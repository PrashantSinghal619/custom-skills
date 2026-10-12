# Strengthen test behavior

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Inspect assertions for observable outcomes, meaningful arguments, boundary conditions, and independently derived expectations. Flag unchecked snapshots, shape-only assertions that miss wrong content, tests that repeat implementation logic, and assertions against the mock instead of the code under test. Use mutation testing, such as Stryker, selectively on important or changed logic when useful. Investigate surviving mutants, including equivalent ones; do not add a mutation-score threshold or meaningless tests merely to improve a number. Scope runs to control cost.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
