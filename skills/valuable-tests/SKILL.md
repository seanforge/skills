---
name: valuable-tests
description: "Use when the requested deliverable creates, changes, or reviews automated tests for implementations, bug fixes, refactors, regressions, or test-suite cleanup. Optimize tests for behavioral confidence, diagnostic value, refactoring resistance, and maintenance cost across languages and test frameworks. Skip tasks limited to test framework installation or CI configuration, and production-only work when tests are not part of the deliverable."
---

# Valuable Tests

Maximize confidence per maintenance cost. Treat tests as maintained code; justify each one by the regression, contract, or failure it can detect.

Resolve conflicts in this order:

1. Correctness, explicit requirements, and preserved behavior
2. Repository validation requirements and public contracts
3. Valuable Tests heuristics

Never remove required validation or weaken a guarantee because a test appears low-value.

## Test behavior

- Make tests sensitive to behavior changes and insensitive to implementation refactors within the chosen boundary. Treat failure under a behavior-preserving change as structural coupling; remove that coupling unless the test intentionally guards a structural or non-functional contract.
- Assert observable outcomes through the chosen boundary's contract: returned values, state transitions, emitted effects, and required interactions.
- Verify an interaction only when the interaction itself is contractual or the required effect has no stable observable state. Keep the expectation no stricter than that contract.
- Choose the smallest boundary that preserves the behavior and failure model under test. Do not equate a unit with a class or assume one test size is universally correct.
- Derive cases from contracts, equivalence partitions, ordered boundaries, decision tables, state transitions, invariants, failure modes, and regressions.
- Apply equivalence partitioning and boundary value analysis at ordered contract boundaries. A case covers a boundary only when that boundary determines the outcome. For formulas, target the closest reachable values around rounding or quantization thresholds; add combinations only when input interactions can change the outcome.
- Capture escaped defects as regression tests at the lowest boundary that reproduces them.
- For stateful behavior, exercise transition sequences and isolation between independent identities when history or shared state can change outcomes.
- Pin the state each failure path leaves behind: what a failed operation must not have consumed, persisted, counted, charged, or advanced.
- Combine test scales when isolated tests cannot predict the relevant production behavior. Do not simulate away the semantics being verified.

## Shape the suite

- A broader test is justified only when it establishes boundary behavior, wiring, serialization, integration, or emergent behavior that narrower tests cannot establish.
- Keep end-to-end tests focused on critical journeys and system properties unavailable at narrower boundaries.
- Pin cross-team and third-party interfaces with contract tests or recorded real responses; do not treat a handwritten fake as evidence of their behavior.

## Preserve signal

- Balance regression sensitivity, refactoring resistance, feedback speed, readability, and maintenance cost. Do not maximize one by silently sacrificing the others.
- Keep tests deterministic and order-independent. Control clocks, randomness, concurrency, ambient state, and external effects at explicit boundaries. Do not mask nondeterminism with retries, arbitrary sleeps, widened timeouts, or execution order; control the cause or wait on a deterministic observable condition.
- Keep each test focused on one behavior; use multiple assertions when they jointly describe that behavior. Report expected, actual, and the minimal triggering context so the cause is local and specific.
- Keep test oracles independent and trivially inspectable. Do not derive expected results with the production algorithm or equivalent branching.
- Keep intent-relevant setup visible and hide only incidental construction. Share helpers only when they preserve each test's meaning and diagnostic independence.
- Treat coverage and test counts as diagnostics, never proof of quality. Do not count code execution as evidence unless the test distinguishes a meaningful outcome; do not add redundant, assertion-free, or implementation-copying tests to move a metric.

## Choose doubles by role

- Prefer real managed dependencies and other real collaborators when they are practical, deterministic, controlled, and their real semantics matter.
- When behavior depends on a dependency's real constraints, transactions, serialization, ordering, concurrency, or failure semantics, test that implementation at the nearest practical boundary. Do not use a fake that reimplements expected dependency behavior as evidence of the real dependency's semantics.
- Use a dummy, fake, stub, spy, or mock only for the role the test needs. Do not adopt mock-everything or mock-nothing doctrine.
- Use doubles to control unavailable, slow, nondeterministic, destructive, or externally owned boundaries; retain broader tests where double fidelity cannot establish production confidence.
- Treat a fake that accumulates stateful, domain, or production-like failure behavior as a fidelity and design warning; use the real implementation when those semantics matter, or move owned behavior into production code instead of enriching the fake.
- Do not verify calls used only to supply test inputs. Verify commands and protocols only when their occurrence, payload, ordering, or cardinality is observable behavior.
- Avoid mocking internal implementation graphs by default. Treat interaction-heavy tests that break under behavior-preserving refactors as coupled to structure.

## Read design feedback

- Treat difficult setup, broad mocking, nondeterminism, global mutation, and test-only hooks as design feedback, not invitations for more scaffolding.
- Improve ownership, interfaces, state boundaries, or effect isolation when the task authorizes it. Do not widen production APIs, fragment cohesive code, or add indirection solely to satisfy a test.
- Use testability only as a negative indicator: inspect hard-to-test code; do not treat easy-to-test code as proof of good design.
