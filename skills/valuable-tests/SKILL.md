---
name: valuable-tests
description: "Use when creating, changing, or reviewing maintained automated tests. Optimize for regression value, precision, determinism, and maintenance cost. Skip manual validation and test-infrastructure-only work."
---

# Valuable Tests

Maximize confidence per maintenance cost.

Preserve explicit validation requirements and public contracts.

## Select tests

- Use risk-based test selection. Each test must protect against a distinct, in-scope regression.
- Stop when an additional test would duplicate an existing failure signal or address only speculative risk.

## Choose scope

Choose the narrowest scope that preserves the failure semantics. Add another scope only when it protects a distinct failure class.

- **Unit:** Verify a local behavioral contract without real collaboration semantics. Test a function directly only when it owns an independent contract; exercise private behavior through that contract.
- **Integration:** Verify behavior that arises from real collaboration or dependency semantics.
- **E2E:** Define the SUT explicitly; enter through its supported external interface and traverse its in-scope production path to an observable result. Reserve E2E for critical behavior unavailable at narrower scopes.

## Design cases

Treat one representative as sufficient for an equivalence partition. Add boundary values, combinations, or transition sequences only when they change the expected outcome or protect against a selected regression risk.

## Assert contracts

- Assert the smallest observable contract that distinguishes the behavior. Multiple assertions are valid only when they jointly define that contract.
- Derive expected results independently; do not reproduce production logic.
- Assert interactions, side effects, and post-failure state only when they are contractual.

## Control dependencies

- Use the real implementation for every dependency whose behavior the test claims to verify. Replace only dependencies outside the chosen test boundary. A test double cannot validate the implementation it replaces.
- Do not widen production interfaces or add indirection solely for testing.

## Preserve signal

- Tests must be deterministic and order-independent. Control nondeterminism at its source; do not compensate with retries, arbitrary sleeps, widened timeouts, or execution order.
- Make failures identify the violated contract and minimal triggering context.
- Treat coverage metrics and test counts as diagnostics, never targets.
