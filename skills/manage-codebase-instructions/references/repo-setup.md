# Repository setup

1. Resolve the root instruction file. If an override or fallback is already effective, use [maintenance.md](maintenance.md); migrate only when the user asks. Do not create nested files unless hierarchy design is requested.
2. Read code and configuration first. Locate command entry points and canonical domain, platform, or release sources; refresh external evidence only for freshness-sensitive non-code policy.
3. Draft only concise mandatory rules, small essential context, and links to larger non-code context. Omit code-explainable facts and generic advice.
4. Ask only about undiscoverable mandatory rules or canonical context sources; never ask to fill the template.
5. Copy [root-instruction.md.template](../assets/root-instruction.md.template). Keep root `MUST-FOLLOW RULES` even when empty, remove unused placeholders, validate every path, and report unresolved policy instead of guessing.
