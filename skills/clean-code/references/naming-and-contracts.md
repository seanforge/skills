# Naming and contracts

Use these checks when names or interfaces carry correctness, boundary, or performance semantics.

## Information

- Replace empty operations with the mechanism: `get` -> `fetch`, `download`, `compute`, `load`, or the domain operation.
- Replace generic values with the represented concept: `retval` -> `sum_squares`; `size` -> `height`, `node_count`, or `memory_bytes`.
- Encode units and representation when confusion changes behavior: `delay_secs`, `size_bytes`, `html_utf8`, `hex_id`.
- Encode trust and transformation state across security boundaries: `untrusted_url` -> `validated_url`; `plaintext_password` -> `password_hash`.
- Scale name specificity to scope. Permit conventional short names only when role and lifetime are locally obvious.
- Remove redundant words and retain established abbreviations only when unambiguous in the repository.

## Misinterpretation

- Replace direction-ambiguous operations: `filter` -> `select` or `exclude`; `clip` -> `truncate(max_chars)`.
- Match verb connotation to reversibility and operational weight: irreversible `Kill()` vs resumable `Pause()`, never a vague `Stop()`.
- State booleans positively: `disable_ssl = false` -> `use_ssl = true`.
- Use `max_` and `min_` for inclusive limits.
- Use `first`/`last` for inclusive ranges and `begin`/`end` for half-open ranges unless local idiom encodes the boundary more clearly.
- Reject noun/verb ambiguity when it changes the apparent operation: `Count(value)` -> `Add(value)`.

## Interfaces

- Finalize public names and signatures before implementing.
- Name parameters at the callee's abstraction level, not a single caller's use case.
- Name flags and options by their effect, not a caller's circumstance: `run_locally` -> `extra_logging` + `use_local_database`.
- Encode preconditions and invalid states in types or construction boundaries where the language permits.
- Prefer named arguments, option objects, enums, or domain types over opaque positional literals and boolean parameters.
- Preserve public compatibility unless the task authorizes migration; improve semantics internally or introduce a compatible boundary when renaming is unsafe.
