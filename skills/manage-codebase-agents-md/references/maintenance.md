# Ongoing maintenance

## 1. Reconstruct current state

- Resolve the target host's instruction-discovery root, ancestor traversal boundary, recognized filenames, per-directory selection, and precedence rules. For targeted work, read each effective file within that boundary through the target directory. For hierarchy-wide work, enumerate recognized files within the boundary, distinguish effective files from shadowed ones, and reconstruct all effective parent-child chains.
- Read code and executable configuration to identify instructions they make redundant.
- Inspect current non-code sources only for mandatory policy or repository-map pointers.
- Refresh external evidence only when a consequential non-code policy is freshness-sensitive.
- Preserve unrelated policies and user edits.

## 2. Classify instructions

Assign each affected instruction one disposition:

- **Keep** when it remains accurate, scoped, consequential, and clear.
- **Update** when its policy remains valid but its facts, paths, commands, wording, or trigger changed.
- **Move** when it belongs at a broader or narrower directory scope.
- **Remove** when evidence shows it is obsolete, duplicated or contradictory after resolution, no longer consequential, or the user authorizes removal.

Do not preserve an obsolete structure by adding adapters, exceptions, or explanatory patches around it.
Treat an unverifiable consequential policy as unresolved: preserve and report it or ask the user instead of deleting it.

## 3. Maintain policy quality

- Keep `MUST-FOLLOW RULES` prominent and permanent in each effective root instruction file; retain only mandatory, consequential rules that code or tooling does not already enforce. In nested files, remove the section when no local rule qualifies.
- Keep `REPOSITORY MAP` pointer-only. Retain entries only for non-code domain-modeling context, development-command entry points, platform or release policy, or comparable context that code cannot explain.
- Remove architecture, technology, workflow, directory, behavior, command, testing, review, and delivery explanations that an agent can recover from the repository.
- Prefer enforcement in code or tooling over prose.
- Preserve unresolved consequential policy; do not replace it with model inference.

## 4. Recheck relevant policy sections

Verify that every remaining rule is mandatory, consequential, unencoded, current, and correctly scoped. Verify that every map entry is only a stable pointer. Preserve an intentional repository decision unless current evidence or the user requires changing it.

## 5. Finish the maintenance pass

- Use [hierarchy.md](hierarchy.md) when a rule may belong at another directory level.
- Confirm every referenced path against the current worktree.
- Read the complete changed instruction chain in precedence order.
- Resolve duplication and accidental contradictions instead of relying on the reader to infer intent.
- Report unresolved policy separately instead of encoding a guess.
