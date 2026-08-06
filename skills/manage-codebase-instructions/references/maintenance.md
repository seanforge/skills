# Maintenance

1. Read the effective instruction chain and verify affected content against current code, configuration, and policy sources.
2. Preserve valid rules, update stale details, and remove duplication or content excluded by the shared boundary.
3. Move each remaining rule to the highest hierarchy level where it stays true.
4. Preserve and report unverifiable consequential policy; never replace it with a guess.
5. Keep root `MUST-FOLLOW RULES` even when empty; remove it from nested files with no local rule. Validate links, scope, precedence, and conflicts.
