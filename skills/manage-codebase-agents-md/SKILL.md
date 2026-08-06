---
name: manage-codebase-agents-md
description: "Use when the user wants to create, audit, update, reorganize, or maintain root-level or nested AGENTS.md, AGENTS.override.md, or other host-recognized repository instruction files. Manage repository setup, configured fallback files, instruction hierarchy, directory scope, inheritance, precedence, rule placement, templates, and ongoing repository-specific guidance. Do not use for orchestrating AI agents or editing unrelated documentation."
---

# Manage Codebase AGENTS.md

## Shared workflow

1. Read the instruction files effective for the target path, then inspect its code and configuration.
2. Add only mandatory rules or non-code pointers; ask only when they cannot be discovered.
3. Put each rule at the broadest valid scope, preserve unrelated changes, and validate the result.

## Choose the workflow

- When no effective root instruction file exists, or the user explicitly requests a fresh setup, read [repo-setup.md](references/repo-setup.md) and use [root-AGENTS.md.template](assets/root-AGENTS.md.template).
- When a noncanonical override or configured fallback is already effective, use [maintenance.md](references/maintenance.md). Create and migrate to canonical `AGENTS.md` only when the user explicitly requests that migration.
- For an audit, correction, extension, or cleanup of existing instructions, read [maintenance.md](references/maintenance.md).
- For nested instructions, hierarchy audits, or moving rules between directories, also read [hierarchy.md](references/hierarchy.md).
- For a full rebuild, read both workflow references and the hierarchy reference when nested files exist.

## Editing constraints

- Preserve an existing intentional policy unless the user authorizes changing it or repository evidence proves it stale.
- Include only mandatory rules and consequential context that code or executable configuration cannot express. Prefer enforcement in code or tooling over prose.
- Use `REPOSITORY MAP` only for pointers to domain-modeling context, development-command entry points, platform or release policy, or comparable non-code context. Do not inventory or summarize architecture, technology stack, workflows, directory structure, or behavior.
- Keep `MUST-FOLLOW RULES` in each effective root instruction file even when empty. In nested files, retain it only when a local rule qualifies. Remove every other unused section and all placeholders from final files.
- Use emphatic language only for durable rules whose violation would cause unsupported behavior, architectural damage, data risk, broken delivery, or substantial rework.
- Do not create nested `AGENTS.md` files speculatively. Require stable local differences that cannot be expressed clearly at a broader scope.

Report which files changed, which policies were established or moved, and which unresolved decision prevented a concrete rule.
