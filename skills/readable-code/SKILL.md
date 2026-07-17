---
name: readable-code
description: "Use whenever the requested deliverable creates or modifies code: implementations, bug fixes, refactors, scripts, services, endpoints, tests, or cleanup. Apply language-agnostic readable-code rules for naming, structure, state, comments, scope, and tests. Skip read-only explanation, review, diagnosis, command execution, and prose-only work."
---

# Readable Code

Minimize time-till-understanding. Understanding is sufficient only when the code can be modified safely, likely defects can be identified, and interactions with surrounding code can be traced.

Resolve conflicts in this order:

1. Correctness, explicit requirements, and preserved behavior
2. Repository conventions and public compatibility
3. Language and framework idioms
4. Readable Code heuristics

Leave clear code unchanged. Keep every change within the requested scope.

## Names and contracts

- Encode domain meaning, role, units, representation, trust state, boundary semantics, and non-obvious cost where relevant.
- Replace generic or overloaded names with the concrete operation or value. Eliminate names with plausible conflicting interpretations.
- Use positive, unambiguous boolean semantics. Split orthogonal effects instead of hiding them behind one flag.
- Reserve accessor-like names such as `get` and `size` for operations whose cost matches local expectations; expose expensive work in the name.
- Make public interfaces hard to misuse. Encode contracts in names, types, structure, and tests.
- Preserve established project and language vocabulary unless it misrepresents semantics.

For naming-heavy work or public API design, read [references/naming-and-contracts.md](references/naming-and-contracts.md).

## Structure and state

- When semantics do not determine order, choose a stable meaningful order and preserve it across corresponding declarations, reads, writes, cases, and tests.
- Derive code structure from the domain model, invariants, cases, and operations. Resolve undefined semantics before implementation.
- Keep each region at one level of abstraction and one task at a time. Separate normalization, policy, effects, and presentation when interleaving obscures their boundaries.
- Extract self-contained incidental subproblems when extraction reduces local complexity; stop when indirection costs more than it isolates.
- Wrap awkward external interfaces and isolate glue, conversion, serialization, and ambient dependencies at boundaries.
- Re-derive clause-heavy logic from its complement, decision table, state model, or algebraic form instead of extending the existing condition. Prefer the formulation with fewest negations: enumerate allowed cases positively, end with one fallback rejection.
- Decompose dense expressions and call chains with named intermediate concepts.
- Prefer guard clauses and early exits over nesting.
- Minimize live mutable state: scope, lifetime, write sites, aliases, and ambient state.
- Eliminate control-flow flags and carried intermediate results when structured control flow can complete the operation immediately.
- After editing, re-read the complete changed unit. Remove branching, duplication, and abstraction drift introduced by the edit.

## Comments

- Write no prose comments or docstrings in new code or refactors, regardless of existing style, except explicitly required public API documentation, known unresolved issues (`TODO`/`FIXME`/`HACK`), or warnings against plausible harmful changes.
- Preserve semantically active directives, suppressions, code-generation markers, licenses, and generated-file notices; they are code, not comments.

## Scope and complexity

- Implement no speculative behavior, extension point, configuration, abstraction, or recovery path.
- Preserve explicit and existing guarantees; never simplify by silently narrowing requirements.
- Prefer existing language, standard-library, framework, and repository primitives over new machinery.
- Delete only task-scoped dead code whose removal is behavior-preserving.
- Start constraint-heavy design with the simplest correct model. Optimize against demonstrated constraints; quantify time, space, precision, and failure-mode trade-offs.
- Pay for new complexity only with correctness, explicit requirements, demonstrated constraints, or reduced per-unit complexity — never with speculative flexibility.

## Tests

- Expose only intent-relevant setup and values at each test's top level; hide incidental construction behind focused helpers.
- Use the smallest clean input that distinguishes the behavior. Separate independent behaviors and failure causes.
- Name tests by behavior and situation. Make failures report expected, actual, and the minimal triggering context.
- Cover boundaries, empty states, duplicates, extremes, invalid transitions, and relevant failure modes without mega-cases.
- Control ambient state and nondeterminism through explicit boundaries.
- Preserve production design quality and repository coverage requirements; do not add test-only distortion.

For deep restructuring or test work, read [references/structure-and-tests.md](references/structure-and-tests.md).
