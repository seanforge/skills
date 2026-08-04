# Ongoing maintenance

## 1. Reconstruct current state

- Resolve the target host's instruction-discovery root, ancestor traversal boundary, recognized filenames, per-directory selection, and precedence rules. For targeted work, read each effective file within that boundary through the target directory. For hierarchy-wide work, enumerate recognized files within the boundary, distinguish effective files from shadowed ones, and reconstruct all effective parent-child chains.
- Inspect the repository sources that can confirm any rule affected by the requested change.
- Refresh relevant external evidence when affected behavior, interfaces, or practices may have changed.
- Check recent structural, toolchain, platform, command, documentation, testing, CI, and release changes.
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

- Keep `MUST-FOLLOW RULES` prominent and permanent in each effective root instruction file, but remove rules that no longer meet its admission threshold. In nested files, remove the section when no local hard rule qualifies.
- Separate verified facts, inference, engineering judgment, and unresolved uncertainty. Do not preserve a rule merely because it matches model memory.
- Use `CODING AND MAINTENANCE STANDARDS` only to name canonical standards and required skills. Keep behavioral guidance in its relevant engineering, testing, or review section. Keep named skills only when the repository requires them and target agents can load them.
- Do not choose a default position on legacy compatibility, deliberately unsupported or self-inflicted behavior, or responsibility for externally owned failures. Preserve or add such policy only when the repository explicitly defines it.
- Avoid duplicating a policy across `MUST-FOLLOW RULES`, standards, engineering guidance, or nested files.

## 4. Recheck relevant policy sections

When the affected file contains engineering, logging, testing, review, or PR policy, verify that each rule remains accurate, consequential, non-duplicative, and correctly scoped. Preserve an intentional repository decision unless current evidence or the user requires changing it.

Do not add an absent optional section merely to match the template. Update only policy affected by repository evidence or the user's requested maintenance.

## 5. Finish the maintenance pass

- Use [hierarchy.md](hierarchy.md) when a rule may belong at another directory level.
- Confirm every referenced path and command against the current worktree.
- Read the complete changed instruction chain in precedence order.
- Resolve duplication and accidental contradictions instead of relying on the reader to infer intent.
- Report unresolved policy separately instead of encoding a guess.
