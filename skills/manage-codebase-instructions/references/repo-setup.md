# Repository setup

1. Resolve the root instruction file. If an override or fallback is already effective, use [maintenance.md](maintenance.md); migrate only when the user asks. Do not create nested files unless hierarchy design is requested.
2. Read code and configuration first. Locate command entry points and canonical domain, platform, or release sources; refresh external evidence only for freshness-sensitive non-code policy.
3. Ask only about undiscoverable mandatory rules or canonical context sources; never ask to fill the template.
4. Copy [root-instruction.md.template](../assets/root-instruction.md.template). Keep its sections as the required baseline; add concise repository-specific sections when needed.
5. Keep root `MUST-FOLLOW RULES` even when empty. Remove unused placeholders, validate every path, and report unresolved policy instead of guessing.
