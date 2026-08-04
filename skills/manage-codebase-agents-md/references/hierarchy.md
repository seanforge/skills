# Hierarchy and scope

## Determine the instruction chain

Identify the filesystem repository root and target directory. Resolve the target host's instruction-discovery root, ancestor traversal boundary, recognized filenames, per-directory selection, and precedence rules. For targeted work, resolve every effective instruction file within that boundary through the target. For hierarchy-wide work, enumerate recognized files within the boundary, distinguish effective files from shadowed ones, and classify every effective parent-child chain. Do not assume identical behavior across hosts.

Within one effective instruction boundary:

- The effective root instruction file governs all work reachable within that boundary.
- A nested effective instruction file governs its directory subtree.
- A deeper file adds local guidance or deliberately overrides a broader rule.
- Work outside that subtree must not depend on its local instructions.

When one filesystem repository spans multiple instruction boundaries, maintain each effective chain separately or report that no single instruction file can govern the entire repository.

## Place each rule

1. Put a rule in the effective root instruction file when it is true across that boundary.
2. Put a local rule in the nearest directory whose full subtree satisfies it.
3. Put a rule shared by sibling modules at their nearest common ancestor.
4. Keep an override narrow and state which broader rule differs and why.
5. Move or deduplicate copied rules instead of maintaining multiple sources of truth.

## Decide whether a nested file is justified

Create one only for stable differences in module responsibility, architecture, toolchain, commands, tests, ownership, safety, generated-code policy, or delivery workflow. Do not create one merely because a directory is large, important, or independently named.

Use [nested-AGENTS.md.template](../assets/nested-AGENTS.md.template) for a justified file. State its scope explicitly, retain `MUST-FOLLOW RULES` only when a local rule qualifies, list standards or required skills only when they differ from the parent, remove unused sections, and avoid restating effective-root guidance.

## Audit the hierarchy

- Verify that every rule is reachable from the work it governs.
- Verify that moving work between directories activates the intended instruction chain.
- Check parent and child files for incompatible commands, terminology, support policy, and quality gates.
- Prefer a single broader rule when multiple children contain the same instruction.
- Prefer a narrow child rule when an effective-root rule has accumulated module-specific exceptions.
