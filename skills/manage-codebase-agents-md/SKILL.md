---
name: manage-codebase-agents-md
description: "Use when the user wants to create, audit, update, reorganize, or maintain root-level or nested AGENTS.md, AGENTS.override.md, or other host-recognized repository instruction files. Manage repository setup, configured fallback files, instruction hierarchy, directory scope, inheritance, precedence, rule placement, templates, and ongoing repository-specific guidance. Do not use for orchestrating AI agents or editing unrelated documentation."
---

# Manage Codebase AGENTS.md

## Shared workflow

1. Find the filesystem repository root and target path. Resolve the target agent host's instruction-discovery root, ancestor traversal boundary, recognized filenames, per-directory selection, and precedence rules. For targeted work, read each effective instruction file within that boundary through the target path. For hierarchy-wide work, enumerate recognized instruction files within the boundary, distinguish effective files from shadowed ones, and read each complete effective parent-child chain.
2. Inspect current repository evidence and proactively obtain relevant current external evidence before asking questions or editing. Never work from remembered model knowledge alone. Preserve unrelated user changes.
3. Ask only about consequential policy that cannot be established from current files. Never ask the user to repeat discoverable facts.
4. Within each effective instruction boundary, write rules at the broadest directory where they remain true. Keep narrower files focused on local additions or deliberate overrides.
5. Re-read every changed file and validate its paths, commands, scope, precedence, and consistency.

## Choose the workflow

- When no effective root instruction file exists, or the user explicitly requests a fresh setup, read [repo-setup.md](references/repo-setup.md) and use [root-AGENTS.md.template](assets/root-AGENTS.md.template).
- When a noncanonical override or configured fallback is already effective, use [maintenance.md](references/maintenance.md). Create and migrate to canonical `AGENTS.md` only when the user explicitly requests that migration.
- For an audit, correction, extension, or cleanup of existing instructions, read [maintenance.md](references/maintenance.md).
- For nested instructions, hierarchy audits, or moving rules between directories, also read [hierarchy.md](references/hierarchy.md). Use [nested-AGENTS.md.template](assets/nested-AGENTS.md.template) only when a nested file is justified.
- For a full rebuild, read both workflow references and the hierarchy reference when nested files exist.

## Editing constraints

- Preserve an existing intentional policy unless the user authorizes changing it or repository evidence proves it stale.
- Do not invent commands, supported environments, architectural boundaries, release gates, evidence requirements, or hard rules.
- Keep `MUST-FOLLOW RULES` in each effective root instruction file even when empty. In nested files, retain it only when a local rule qualifies. Remove every other unused section and all placeholders from final files.
- Use emphatic language only for durable rules whose violation would cause unsupported behavior, architectural damage, data risk, broken delivery, or substantial rework.
- Do not create nested `AGENTS.md` files speculatively. Require stable local differences that cannot be expressed clearly at a broader scope.

Report which files changed, which policies were established or moved, and which unresolved decision prevented a concrete rule.
