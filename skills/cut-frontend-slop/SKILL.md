---
name: cut-frontend-slop
description: Audit and reduce maintenance risks in frontend codebases, especially TypeScript and React, including guessed API shapes, unnecessary effects, architectural drift, weak tests, dead code, and duplicate logic. Use for frontend slop reviews, targeted cleanup, or gradual quality-check rollout; not visual redesign or copywriting.
---

# Cut frontend slop

Make frontend code safer to trust and cheaper to review. Prevent unsupported assumptions, find accumulated waste, and enforce checks that catch real defects. Apply the categories to the project's stack; TypeScript and React are the primary context.

## Establish scope

Read project instructions, package scripts, compiler and lint configuration, API contracts, tests, and CI. Inspect the requested files or diff first; for a general invocation, audit representative entry points and important data flows. Search for existing helpers before introducing replacements.

Follow the requested mode: a review produces findings; a cleanup implements scoped fixes; a tooling request adds appropriate safeguards. If no mode is given, start with an audit and prioritized recommendations. Keep behavior and the project's architecture intact unless the requested fix requires a change. Do not install the entire tool list or rewrite the repository to satisfy it.

## Ten checks

1. **API contracts.** Prefer an authoritative, current OpenAPI specification and generated types/client/runtime schemas over independently handwritten response shapes. Hey API and Zod are examples, not dependencies required by this skill. Validate untrusted responses at runtime; compile-time types cannot establish their actual shape. Regenerate clients rather than editing generated files. If no trustworthy contract exists, report the gap and inspect actual responses or backend definitions; never invent fields or a supposedly authoritative spec.

2. **Type assumptions.** Assess `strict`, `noUncheckedIndexedAccess`, and `exactOptionalPropertyTypes`. Handle absent array entries and optional values explicitly. Replace unjustified `any`, non-null assertions, and casts that hide uncertainty with accurate types or checks. Introduce compiler changes gradually when the existing backlog is large.

3. **Lint as a behavior filter.** Use existing tooling to find excessive complexity, identical branches, accidental nested control flow, and suspicious duplication. In React, remove effects used only to derive values or synchronize redundant state; retain effects that synchronize with external systems. Check assertion-free tests, focused tests, missing awaits in end-to-end assertions, and accessible markup. Relevant examples include SonarJS, effect-focused React linting, Vitest and Playwright ESLint plugins, and jsx-a11y. Respect existing conventions for exported return types, type definitions, filenames, and import aliases rather than imposing style rules as universal defect fixes. Complement static accessibility checks with rendered or composed UI checks when applicable.

4. **Layer boundaries.** Infer the intended dependency direction before enforcing it. Typical boundaries keep services independent of UI, shared utilities free of domain-specific behavior, design-system components independent of application state and API calls, production code free of test mocks, and routing focused on route-to-page mapping. Check framework conventions before applying these examples. Use the existing boundary tool or a suitable one, such as dependency-cruiser or ESLint boundaries. Diagnostics should explain the reason and where the dependency belongs.

5. **Rules backed by evidence.** Add a custom rule only for a demonstrated recurring mistake or a concrete incident. Capture the rationale and corrective action, and test both violations and legitimate cases. For example, double rounding may justify keeping calculation precision in services and rounding only at presentation boundaries; it does not justify a global ban on rounding.

6. **Guidance during generation.** Keep important project constraints in the agent's project rules and relevant skills. Where the project supports it, use changed-file lint feedback in the working loop. Written guidance reduces mistakes but does not replace executable checks. Treat aggregate diagnostics as clues, never objectives to optimize.

7. **Tests that detect broken behavior.** Inspect assertions for observable outcomes, meaningful arguments, boundary conditions, and independently derived expectations. Flag unchecked snapshots, shape-only assertions that miss wrong content, tests that repeat implementation logic, and assertions against the mock instead of the code under test. Use mutation testing, such as Stryker, selectively on important or changed logic when useful. Investigate surviving mutants, including equivalent ones; do not add a mutation-score threshold or meaningless tests merely to improve a number. Scope runs to control cost.

8. **Dead code and stale mocks.** Use an existing detector or Knip to identify unused files, exports, and dependencies. Review ignored paths and verify entry points, dynamic imports, framework discovery, generated files, and public exports before deleting anything. Check mock paths and factory exports against real modules, accounting for partial mocks. Add a repository-specific reachability or mock detector only for a demonstrated gap. Test custom detectors with known positive and negative fixtures, including aliases and a deliberately unreachable file.

9. **Duplicate logic.** Search for both textual and semantic copies of business rules. jscpd can help with textual duplication but cannot prove semantic uniqueness. Treat repeated markup, fixtures, and business logic differently. Consolidate when copies represent the same rule and could diverge; do not create premature abstractions just to remove similar-looking JSX.

10. **CI enforcement.** For settled checks, provide separately visible formatting/lint, typecheck, unit-test, and build results, with appropriately scoped mutation analysis where adopted. Required checks should gate merging and deployment; a workflow alone does not configure branch protection. Mutation analysis should fail for execution errors when appropriate, not an arbitrary score. Report external branch-protection or deployment settings still needed rather than claiming local configuration enforces them.

## Roll out proportionately

Baseline existing failures. Start new lint rules as warnings and focus cleanup on changed code; track historical debt separately. Run typechecking with the scope needed to remain sound. Promote rules that catch real bugs, tune or remove noisy ones, and add CI gates after the checks stabilize. Never silence violations or expand ignore lists simply to get green results.

Review disables, ignores, and stale rules periodically. Explain why each rule exists and how to fix its failures. Match investment to code lifetime, team size, and consequences of defects. When starting small, prioritize a trustworthy API contract, meaningful tests with selective mutation analysis, and enforcement of the checks the project adopts.

## Verify and report

Run the relevant existing checks after changes and add behavioral tests for meaningful fixes. State what ran, what failed, and what remains unverified. For each actionable finding, give a file location, concrete risk or behavior, evidence, and the smallest useful fix; separate observed defects from tooling suggestions. Summarize applied changes and remaining decisions.

Human review still owns feature correctness, state placement, premature abstractions, and competing implementations of the same idea. A green suite proves only that its checks found no targeted failures; it does not prove understanding or product correctness.

## Provenance

Condensed and adapted from the user-provided writeup beginning “Ten thousand lines of code in a week used to mean a team.” The source author and public URL were not supplied. Tool names are examples from that writeup; verify current compatibility against official documentation before adding them to a project.
