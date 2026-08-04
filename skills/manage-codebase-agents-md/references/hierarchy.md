# Hierarchy and scope

## Determine the instruction chain

For targeted work, identify the repository root, target directory, and every applicable instruction file between them. For hierarchy-wide work, enumerate every `AGENTS.md` in scope and classify its parent-child chain. Follow the host agent's documented loading and precedence semantics; do not assume identical behavior across tools when it affects the result.

Treat the standard directory model as:

- A root `AGENTS.md` governs repository-wide work.
- A nested `AGENTS.md` governs its directory subtree.
- A deeper file adds local guidance or deliberately overrides a broader rule.
- Work outside that subtree must not depend on its local instructions.

## Place each rule

1. Put a rule at the root when it is true across the repository.
2. Put a local rule in the nearest directory whose full subtree satisfies it.
3. Put a rule shared by sibling modules at their nearest common ancestor.
4. Keep an override narrow and state which broader rule differs and why.
5. Move or deduplicate copied rules instead of maintaining multiple sources of truth.

## Decide whether a nested file is justified

Create one only for stable differences in module responsibility, architecture, toolchain, commands, tests, ownership, safety, generated-code policy, or delivery workflow. Do not create one merely because a directory is large, important, or independently named.

Use [nested-AGENTS.md.template](../assets/nested-AGENTS.md.template) for a justified file. State its scope explicitly, retain `MUST-FOLLOW RULES` only when a local rule qualifies, list standards or required skills only when they differ from the parent, remove unused sections, and avoid restating root guidance.

## Audit the hierarchy

- Verify that every rule is reachable from the work it governs.
- Verify that moving work between directories activates the intended instruction chain.
- Check parent and child files for incompatible commands, terminology, support policy, and quality gates.
- Prefer a single broader rule when multiple children contain the same instruction.
- Prefer a narrow child rule when a root rule has accumulated module-specific exceptions.
