# Ongoing maintenance

## 1. Reconstruct current state

- For targeted work, read every applicable `AGENTS.md` from the repository root through the target directory. For hierarchy-wide work, enumerate every file in scope and reconstruct all parent-child chains.
- Inspect the repository sources that can confirm any rule affected by the requested change.
- Refresh relevant external evidence when affected behavior, interfaces, or practices may have changed.
- Check recent structural, toolchain, platform, command, documentation, testing, CI, and release changes.
- Preserve unrelated policies and user edits.

## 2. Classify instructions

Assign each affected instruction one disposition:

- **Keep** when it remains accurate, scoped, consequential, and clear.
- **Update** when its policy remains valid but its facts, paths, commands, wording, or trigger changed.
- **Move** when it belongs at a broader or narrower directory scope.
- **Remove** when it is obsolete, duplicated, contradictory, unverifiable, or no longer consequential.

Do not preserve an obsolete structure by adding adapters, exceptions, or explanatory patches around it.

## 3. Maintain policy quality

- Keep the root `MUST-FOLLOW RULES` section prominent and permanent, but remove rules that no longer meet its admission threshold. In nested files, remove the section when no local hard rule qualifies.
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
