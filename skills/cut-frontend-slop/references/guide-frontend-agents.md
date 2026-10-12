# Guide frontend agents

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

Keep important project constraints in the agent's project rules and relevant skills. Where the project supports it, use changed-file lint feedback in the working loop. Written guidance reduces mistakes but does not replace executable checks. Treat aggregate diagnostics as clues, never objectives to optimize.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
