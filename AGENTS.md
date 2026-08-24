# AGENTS.md

Instructions for any agent working **in** this repo.

## What this repo is

A personal plugins repo of reusable **skills** for coding agents, published as a plugin
for **Claude Code** and **Codex**. Each skill is a self-contained module the agent loads
on demand.

Skills here are atomic and composable. Higher-level development flows, review
orchestration, and automation belong in other plugins.

## Agent model

Write skills for staff-engineer-level coding agents that already know how to design,
implement, and test software. They need reminders where defaults matter, not textbooks,
common-term explanations, framework tutorials, or examples of familiar techniques.

A skill provides decision criteria, invariants, boundaries, and stop conditions; it does
not replace the agent's judgment.

- Define the desired agent behavior, not only prohibitions.
- Scale specificity to risk; prescribe procedures only when deviation creates a concrete
  correctness, safety, or operational failure.
- Brevity is a design goal, not a defect.
- Do not add guidance merely because some knowledge is absent.
- Include only instructions that materially change decisions, prevent plausible
  high-probability errors, or establish ownership.
- Prefer precise, unambiguous professional terms.
- Do not add tutorials, case catalogs, framework-specific recipes, or exhaustive
  checklists.
- Do not add rules for speculative edge cases.
- Add hierarchy or supporting references only for substantial, genuinely conditional
  content.
- Keep skills independent and atomic — no cross-skill imports. Multiple skills may
  compose orthogonally in the same task.
- Assign each domain decision to one owning skill; compose skills instead of duplicating
  its policy.
- Do not expand a high-level invariant when a staff-level agent can reliably derive the
  concrete action.

Do not invent work to make a skill or review appear thorough.

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

## Skill change standard

Validate skills against realistic agent decisions and failure modes, not wording or
topical completeness.

Evolve skills from observed agent failures; generalize each into the narrowest reusable
invariant.

Treat guidance as missing only when all of the following are true:

1. A staff-level agent cannot reliably infer it.
2. Its absence causes a plausible, high-probability failure.
3. It belongs to this skill's ownership.
4. It can be expressed as a brief, unambiguous invariant.
5. Its value exceeds its token and maintenance cost.

If any condition is unmet, do not add it.

When revising wording:

- Prefer replacement to addition.
- Keep new wording equal in length or shorter unless fixing a clear correctness gap.
- Identify the concrete misreading the change prevents.
- Do not replace a local issue with a large rewrite.

## Conventions

- Skill names are kebab-case and match their directory.
- Descriptions state when to use; add exclusions only when they prevent plausible false triggers.
- Keep README and plugin manifests generic and stable. Do not list individual skills,
  skill counts, repository layout, or implementation details there; the filesystem and
  skill frontmatter are the source of truth.
