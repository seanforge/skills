---
name: code-review
description: Use when the user asks for a read-only, defect-first review of uncommitted changes, a base-branch diff, a commit, a pull request, or another specified target.
---

# Code Review

Inspect the requested target directly. Do not modify files, create commits, push branches, post
review comments, or delegate the review.

## Choose the profile

Use `high` unless the user requests another profile:

- `light`: report P0 and P1 findings.
- `medium`: report P0 through P2 findings.
- `high`: report P0 through P3 findings.

Profiles change reporting scope, not the evidence required for a finding. Inspect the complete
requested change in every profile and do not report findings outside the selected severity range.

## Review the change

1. Read the applicable repository instructions.
2. Inspect the complete requested change and enough surrounding code to understand each changed path.
3. Identify concrete regressions introduced by the change. Return every qualifying finding within
   the selected profile; do not stop after the first issue.
4. Check relevant tests and call sites to confirm that each finding is real and actionable.

## Qualify findings

Report an issue only when all of these are true:

- It meaningfully affects correctness, performance, security, or maintainability.
- It is discrete and actionable.
- Fixing the bug does not demand a level of rigor that is not present in the rest of the codebase.
- It was introduced by the reviewed change.
- The author would likely fix it if they knew about it.
- It does not rely on unstated assumptions about the codebase or the author's intent.
- The affected scenario or call path is demonstrable from the code.
- It is clearly not an intentional change.

Ignore speculative concerns, pre-existing problems, and trivial style unless it obscures meaning or
violates documented standards. Review independently and deduplicate findings by defect and remedy.

Apply all applicable repository instructions to each changed file; more-specific guidance wins on
conflict. Treat a finding as rule-supported only when an applicable rule materially contributes
repository-specific scope, an invariant, a remedy, a convention, or confirmation behavior. For
each rule-supported finding, cite the applicable instruction file and its smallest supporting line
range. Do not omit ordinary findings or invent findings solely because a rule file exists.

## Report findings

Present findings first, ordered by severity, with one entry per distinct issue. Label each finding
P0 through P3. Cite the smallest line range that explains the issue and overlaps the diff. In one
short, matter-of-fact paragraph, explain why it is wrong and which inputs, environments, or
scenarios trigger it. State severity accurately and make the issue immediately understandable.

- `P0`: Drop everything to fix. Blocking release, operations, or major usage. Use only for universal
  issues that do not depend on any assumptions about the inputs.
- `P1`: Urgent. Should be addressed in the next cycle.
- `P2`: Normal. To be fixed eventually.
- `P3`: Low. Nice to have.

If nothing qualifies, say `No P0-P1 findings.` for `light`, `No P0-P2 findings.` for `medium`, or
`No findings.` for `high`. Do not invent a finding. End with a brief assessment and any material
test gaps or residual risks within the selected profile. Never claim the patch is correct after a
partial review.
