# Repository setup

Use this workflow when no effective root instruction file exists or the user explicitly requests a fresh setup or migration to canonical `AGENTS.md`. When migrating an effective override or configured fallback, also use [maintenance.md](maintenance.md) and preserve its intentional policies. Do not create nested files during setup unless the user explicitly includes hierarchy design in scope.

## 1. Inspect repository evidence

Read the smallest sufficient set of current sources:

- Top-level structure, README, contribution guide, manifests, lockfiles, runtime-version files, task runners, and build or packaging configuration.
- Test, lint, formatting, type-checking, CI, release, and PR configuration.
- Architecture, design, domain-vocabulary, platform, security, migration, and operational documents.
- Existing deferred-work or technical-debt policy.
- Repository-declared coding standards and required agent skills or workflows that the target agents can actually load.
- Current external evidence needed for version-sensitive behavior, external interfaces, or applicable practice: official documentation, standards, upstream source, relevant reference implementations, or other credible current sources.

Do not traverse dependencies, generated output, vendored source, snapshots, or build artifacts beyond identifying their role.

## 2. Build an evidence sheet

Record facts before drafting:

- Repository purpose, primary users, actual operating scale, and proven current workflows.
- Languages, frameworks, runtime and package-manager versions, IDE recommendations, build and packaging tools, and exact commands.
- Supported platforms or environments, explicitly unsupported scope, primary release gates, and best-effort targets.
- Canonical vocabulary, architecture, design, deferred-work, platform, and other trigger-specific guidance.
- Decisions that require fresh evidence and the authoritative repository, official, standards, upstream, or implementation sources for each.

Mark every item as verified, inferred, or unresolved. Never substitute model memory for current evidence that can be inspected.

## 3. Ask only unresolved high-impact questions

Ask a small batch at a time:

1. What workflows and environments are officially supported, primary, best effort, or out of scope?
2. Which tools, frameworks, build systems, packaging systems, coding standards, maintenance standards, or available agent skills are mandatory or prohibited?
3. Which decisions require fresh external evidence, and which current sources are authoritative?
4. Which tests, platforms, checks, or approvals block merge and release, and what PR accounting or size policy applies?
5. Which violations would cause rejected work, architectural damage, data risk, broken delivery, or substantial rework?

Do not ask a policy question merely to fill the template. Omit irrelevant modules.

## 4. Establish standards and hard rules

Use `CODING AND MAINTENANCE STANDARDS` to name canonical standards documents and the skills required for code, test, architecture, planning, or review work. List a named skill only when the repository intentionally requires it and the target agent environment provides it; otherwise link or state the portable standard. Put behavioral guidance in its relevant engineering, testing, or review section instead of duplicating it here.

Keep `MUST-FOLLOW RULES` permanently in the effective root instruction file, even when no rule qualifies. Do not duplicate its rules in other sections.

Always retain the template's evidence-first rule. Retain its other `ENGINEERING APPROACH` guidance when the repository adopts it. Record evidence sources and verification triggers only when they guide future decisions. State when an explicit repository decision overrides conflicting generic tool or skill recommendations.

Do not choose a default position on legacy compatibility, deliberately unsupported or self-inflicted behavior, or responsibility for externally owned failures. Add such a policy only when the target repository explicitly defines it and the rule is consequential to supported work.

## 5. Fill the root template

Copy [root-AGENTS.md.template](../assets/root-AGENTS.md.template), then:

- Replace placeholders with verified facts and explicit decisions.
- Convert README commands and version declarations into concise workflow instructions instead of copying explanatory prose.
- Link canonical documents rather than duplicating their contents.
- Include deferred-work policy only when a canonical destination and admission criteria exist. Include logging only when repository evidence or an explicit decision adopts it.
- Include human-realistic guidance whenever user-facing E2E applies. Include other platform, testing, and PR policy only when relevant.
- Add a concise repository-specific section when a verified consequential policy has no existing slot.
- Remove every unused section and placeholder except the permanent `MUST-FOLLOW RULES` heading.

Validate each command against executable configuration and each referenced path against the worktree. If a fact remains unresolved, report it separately instead of encoding a guess.
