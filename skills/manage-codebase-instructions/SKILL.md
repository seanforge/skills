---
name: manage-codebase-instructions
description: "Use when the user wants to create, audit, or maintain repository instruction files. Determine whether the repository uses AGENTS.md, CLAUDE.md, or another host-recognized filename, then manage its hierarchy, overrides, fallbacks, and directory scope. Do not use for agent orchestration or unrelated documentation."
---

# Manage Codebase Instructions

## Shared workflow

**Keep concise mandatory rules and small essential context inline; group longer non-code information by topic in Markdown files and leave only links; omit anything code or configuration explains.**

1. Read the effective instructions, code, and configuration.
2. Apply the content boundary above at the broadest valid scope.
3. Preserve unrelated changes and validate the result.

## Choose the workflow

- When no effective root instruction file exists, or the user explicitly requests a fresh setup, read [repo-setup.md](references/repo-setup.md) and use [root-instruction.md.template](assets/root-instruction.md.template).
- When a noncanonical override or configured fallback is already effective, use [maintenance.md](references/maintenance.md). Migrate to the canonical root instruction file only when the user explicitly requests it.
- For an audit, correction, extension, or cleanup of existing instructions, read [maintenance.md](references/maintenance.md).
- For nested instructions, hierarchy audits, or moving rules between directories, also read [hierarchy.md](references/hierarchy.md).
- For a full rebuild, read both workflow references and the hierarchy reference when nested files exist.
