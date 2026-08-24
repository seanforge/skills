---
name: anti-tdd
description: "Use when implementing or refactoring production code. Implement first, exercise and stabilize behavior, then write new tests for behavior introduced or changed by the implementation."
---

# Anti-TDD

Own the implementation as a coherent whole. Tests follow stabilized behavior; they do not drive it.

## Implement

- Implement the intended change from the available context. Do not write new tests to drive implementation.
- Treat the requested change as one implementation boundary; explicitly separated, independently shippable subtasks are separate boundaries.
- Resolve local, reversible details autonomously. Surface gaps that change behavior, scope, or public contracts.
- Handle reachable, in-scope edge cases in supported use and at owned boundaries.
- Treat resource ownership, lifetime, concurrency, and failure semantics as part of correctness when affected by the change.

## Stabilize

Exercise the affected behavior through the nearest executable boundary that preserves its semantics. Fix in-scope defects and integration gaps until observed behavior matches the intended behavior.

When execution is infeasible, use the strongest available validation and report the gap.

## Test

Existing validation may run at any time; new tests follow stabilization.

Add new tests only for behavior introduced or changed by the implementation. Run the final relevant test portfolio.
