# Structure and tests

## Decomposition

- Separate essential domain logic from incidental mechanisms.
- Isolate parsing, normalization, validation, policy, mutation, I/O, and presentation when their interleaving obscures invariants.
- Extract cohesive subproblems; avoid function confetti, pass-through layers, and utility junk drawers.
- Design wrappers around caller needs while keeping boundary mechanics isolated.
- Prefer semantic cohesion over reuse as the extraction criterion.

## Logic and state

- Model complex branching as guards, decision tables, state transitions, pattern matching, algebraic data types, or equivalent idiomatic structures.
- Reformulate expanding conditions through complements, invariants, or normalized representations.
- Do not fuse assignment, conditions, and side effects into a single expression: `assert(!(bucket = find(key)) || !bucket.busy())` -> assign, then branch, then assert.
- Keep the dominant execution path locally traceable. Isolate concurrency, callbacks, exceptions, dynamic dispatch, reflection, and other hidden transfer when they obscure effects.
- Minimize mutable state and aliasing. Prefer explicit data flow, immutability, and narrow ownership where idiomatic.
- Inject clocks, randomness, environment, global configuration, and external effects at controlled boundaries.

## Design evolution

- Bound resource growth where the domain requires it.
- Compare alternatives by correctness, semantic complexity, time, space, precision, failure modes, and operational cost.
- Decompose interacting state by responsibility only when the resulting dependency graph remains simpler than the original unit.

## Tests

- Keep Arrange/Act/Assert or the local equivalent semantically visible without ceremonial structure.
- Use parameterization only when cases retain independent diagnostic value.
- Select values that distinguish boundaries and semantics; avoid arbitrary noisy fixtures.
- Generate stress volume programmatically.
- Use framework-native diagnostic assertions. Add triggering context only when expected and actual are insufficient.
- Treat difficult setup, nondeterminism, global mutation, and broad mocking as design feedback, not an invitation for more scaffolding.
- Do not weaken encapsulation, widen production APIs, or add branches solely for tests.
