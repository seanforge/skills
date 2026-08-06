# Repository setup

Use this workflow when no effective root instruction file exists or the user explicitly requests a fresh setup or migration to canonical `AGENTS.md`. When migrating an effective override or configured fallback, also use [maintenance.md](maintenance.md) and preserve its intentional policies. Do not create nested files during setup unless the user explicitly includes hierarchy design in scope.

## 1. Inspect repository evidence

Read enough code and executable configuration to avoid documenting what they already explain:

- Inspect source, manifests, task runners, build configuration, tests, and CI directly.
- Locate domain-modeling context, development-command entry points, and platform or release policy only to provide stable pointers.
- Identify explicit mandatory rules that code or tooling does not already enforce.
- Obtain current external evidence only when a consequential non-code policy is freshness-sensitive.

Do not traverse dependencies, generated output, vendored source, snapshots, or build artifacts beyond identifying their role.

## 2. Classify candidate content

Exclude anything an agent can recover from code or executable configuration, including architecture, technology stack, workflows, directory structure, commands, tests, and behavior.

Admit only:

- A one- or two-sentence repository description covering users or operating scale when code cannot make it clear.
- Mandatory, consequential rules that are not already enforced by code or tooling.
- Concise, essential, self-contained supporting context that cannot be recovered from code.
- Pointers to non-code domain-modeling context or platform and release policy.
- Pointers to the files that define development commands, without copying the commands.

## 3. Ask only unresolved high-impact questions

Ask only when the answer cannot be discovered:

1. Which unencoded rules are mandatory enough that violating them would reject the work or cause substantial damage?
2. Which non-code source is authoritative for domain modeling?
3. Which non-code source is authoritative for platform or release policy?

Do not ask merely to fill the template.

## 4. Draft only irreducible instructions

- Keep `MUST-FOLLOW RULES` permanently in the effective root instruction file, even when empty.
- Put every qualifying rule there. Include its trigger, scope, and source when available.
- Use `REPOSITORY MAP` only for stable pointers; do not add explanations that duplicate the target files.
- Prefer adding an enforceable check to code or tooling over documenting a prose rule.
- Do not add generic engineering, architecture, testing, logging, review, or PR advice.

## 5. Fill the root template

Copy [root-AGENTS.md.template](../assets/root-AGENTS.md.template), then:

- Replace placeholders with verified facts and explicit decisions.
- Point to command entry-point files instead of copying commands.
- Keep concise, essential, self-contained supporting context inline.
- Point to larger or independently maintained context without restating or summarizing it.
- Put any additional mandatory, unencoded policy in `MUST-FOLLOW RULES`; do not create another section.
- Remove every unused section and placeholder except the permanent `MUST-FOLLOW RULES` heading.

Validate every referenced path against the worktree. If a policy remains unresolved, report it separately instead of encoding a guess.
