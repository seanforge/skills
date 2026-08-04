---
name: manage-codebase-agents-md
description: "Use when the user wants to create, audit, update, reorganize, or maintain root-level or nested AGENTS.md files for a codebase. Manage repository setup, instruction hierarchy, directory scope, inheritance, rule placement, templates, and ongoing repository-specific guidance. Do not use for orchestrating AI agents or editing unrelated documentation."
---

# Manage Codebase AGENTS.md

## Shared workflow

1. Find the repository root and target path. For targeted work, read every `AGENTS.md` from the root through that path. For hierarchy-wide work, enumerate every `AGENTS.md` in scope and read each complete parent-child chain.
2. Inspect current repository evidence and proactively obtain relevant current external evidence before asking questions or editing. Never work from remembered model knowledge alone. Preserve unrelated user changes.
3. Ask only about consequential policy that cannot be established from current files. Never ask the user to repeat discoverable facts.
4. Write rules at the broadest directory where they remain true. Keep narrower files focused on local additions or deliberate overrides.
5. Re-read every changed file and validate its paths, commands, scope, precedence, and consistency.

## Choose the workflow

- For a missing root `AGENTS.md` or an explicitly requested fresh repository setup, read [repo-setup.md](references/repo-setup.md) and use [root-AGENTS.md.template](assets/root-AGENTS.md.template).
- For an audit, correction, extension, or cleanup of existing instructions, read [maintenance.md](references/maintenance.md).
- For nested instructions, hierarchy audits, or moving rules between directories, also read [hierarchy.md](references/hierarchy.md). Use [nested-AGENTS.md.template](assets/nested-AGENTS.md.template) only when a nested file is justified.
- For a full rebuild, read both workflow references and the hierarchy reference when nested files exist.

## Editing constraints

- Preserve an existing intentional policy unless the user authorizes changing it or repository evidence proves it stale.
- Do not invent commands, supported environments, architectural boundaries, release gates, evidence requirements, or hard rules.
- Keep the root `MUST-FOLLOW RULES` section even when empty. In nested files, retain it only when a local rule qualifies. Remove every other unused section and all placeholders from final files.
- Use emphatic language only for durable rules whose violation would cause unsupported behavior, architectural damage, data risk, broken delivery, or substantial rework.
- Do not create nested `AGENTS.md` files speculatively. Require stable local differences that cannot be expressed clearly at a broader scope.

Report which files changed, which policies were established or moved, and which unresolved decision prevented a concrete rule.
