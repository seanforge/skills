---
name: solution-design
description: "Use when a software change has unresolved technical design decisions, material alternatives, or consequential feasibility uncertainty before implementation. Skip routine changes and implementation from an already settled design."
---

# Solution Design

Converge a non-trivial software change into one evidence-backed technical direction and a decision-complete implementation outline. Design for today's reality without making tomorrow's credible changes expensive.

## Investigate

- Build an accurate model of the relevant behavior, architecture, conventions, constraints, scale, and failure model from repository evidence and available context.
- Search broadly across current primary sources, mature prior art, and failure reports before inventing. Verify decision-shaping claims against the strongest available evidence; model memory supplies search terms, not evidence.
- Evaluate comparable implementations for fit, maintenance, licensing, integration cost, and operational cost. Reuse proven work when justified; do not inherit complexity required only at another system's scale.
- Run a disposable spike when reading cannot establish feasibility. Keep it out of production code.

## Converge

- Identify consequential technical uncertainty and viable alternatives. Investigate information gaps instead of filling them with invented architecture.
- Evaluate alternatives against the intended behavior, codebase fit, current scale and failure model, operational cost, and credible evolution.
- Prefer the simplest well-supported direction that preserves coherent ownership boundaries and locality of change. Treat the current architecture as evidence, not an immutable constraint; propose the smallest root-cause refactor when it would otherwise force cross-boundary coupling or layered workarounds.
- Define responsibilities, contracts, data and state, and end-to-end data and control flow before naming patterns. Use a design pattern only when it fits that shape.
- Resolve user-owned trade-offs with the user rather than burying them in technical assumptions.

## Outline

- Describe the expected code shape and end-to-end flow: ownership across affected areas, material contract and data or state changes, external effects and error propagation, prerequisite refactoring, and the decisions and trade-offs that shaped the direction. Name significant files, interfaces, types, or symbols when they carry a consequential design decision.
- State what each named area owns, how the pieces interact, and why the boundaries belong there. Preserve evidence only where it explains a decision.
- Leave local, reversible implementation details to the implementer. Do not produce a task checklist, exhaustive file inventory, pseudocode, exact edits, or speculative architecture.
- Produce the outline in the current context. Create a persistent artifact only when requested.

Stop when a capable engineer can begin implementation without rediscovering any consequential design decision. Leave only local implementation judgment unresolved.
