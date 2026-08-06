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

Create one only for mandatory local rules or non-code context pointers that differ from the parent and cannot be enforced or recovered from code and executable configuration. Do not create one for architecture, toolchain, commands, tests, directory structure, or other facts the subtree already explains.

For a justified nested file, state its scope explicitly, include `MUST-FOLLOW RULES` only when a local rule qualifies, keep `REPOSITORY MAP` pointer-only when local non-code context differs, and avoid restating effective-root guidance.

## Audit the hierarchy

- Verify that every rule is reachable from the work it governs.
- Verify that moving work between directories activates the intended instruction chain.
- Check parent and child files for incompatible mandatory rules or policy pointers.
- Prefer a single broader rule when multiple children contain the same instruction.
- Prefer a narrow child rule when an effective-root rule has accumulated module-specific exceptions.
