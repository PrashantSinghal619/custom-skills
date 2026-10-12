# Gate frontend quality

## Working approach

Read project instructions and the relevant files, configuration, and existing scripts. Follow the requested scope and mode: report findings for a review, implement scoped fixes for cleanup, and add safeguards for a tooling request. With no mode specified, audit first. Preserve intended behavior and existing conventions; use existing tools before adding dependencies. Search for existing implementations before introducing new ones.

## Concern

For settled checks, provide separately visible formatting/lint, typecheck, unit-test, and build results, with appropriately scoped mutation analysis where adopted. Required checks should gate merging and deployment; a workflow alone does not configure branch protection. Mutation analysis should fail for execution errors when appropriate, not an arbitrary score. Report external branch-protection or deployment settings still needed rather than claiming local configuration enforces them.

Baseline existing failures. Start noisy or broad new rules as warnings, focus cleanup on changed code, and track old debt separately. Promote checks that catch real bugs and tune or remove noise. Do not weaken sound project-wide typechecking merely to limit a scan to changed files.

Review accumulating disables, ignored paths, and stale rules. Keep rationale and corrective action clear. Green checks detect only their targeted failures; human review still owns feature correctness, state placement, and architectural judgment.

## Verification and output

For findings, provide a file location, evidence, concrete risk, and the smallest useful fix. Separate observed defects from tooling suggestions. After changes, run relevant existing checks and add behavioral tests for meaningful fixes; state failures and anything unverified. Avoid blanket rewrites or suppressions to make checks green. Match effort to project lifetime and defect consequences. Verify current official tool documentation before adding a dependency.
