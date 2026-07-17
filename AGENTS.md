# AGENTS.md

Instructions for any agent working **in** this repo.

## What this repo is

A personal plugins repo of reusable **skills** for coding agents, published as a plugin
for **Claude Code** and **Codex**. Each skill is a self-contained module the agent loads
on demand.

## Structure

- `skills/<name>/SKILL.md` — one skill per directory. Frontmatter (`name`, `description`)
  declares the trigger; the body holds the instructions.
- `.claude-plugin/` — Claude Code manifests (`marketplace.json`, `plugin.json`).
- `.codex-plugin/plugin.json` — Codex manifest.

## Adding a skill

1. Create `skills/<kebab-name>/SKILL.md`.
2. Frontmatter: `name` (matches the dir), `description` — lead with the concrete trigger
   ("Use when the user wants to …") since that's what the agent matches against.
3. Body: the steps/guidance. Keep it focused; add supporting files in the same dir if needed.
4. Bump the `version` in both `.claude-plugin/plugin.json` and `.codex-plugin/plugin.json`.

## Conventions

- Skill names are kebab-case and match their directory.
- Descriptions state when to use **and** when not to, to avoid false triggers.
- Keep skills self-contained — no cross-skill imports.
- Keep README and plugin manifests generic and stable. Do not list individual skills,
  skill counts, repository layout, or implementation details there; the filesystem and
  skill frontmatter are the source of truth.
