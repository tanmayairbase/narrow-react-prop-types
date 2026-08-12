# Agent Memory: Narrow React Component Props

Standing feedback for future `Agent: Narrow React Component Props` runs.

## Guidance

- Inspect the complete prop list at every live JSX call site. A search for `propName=` only proves that some caller supplies the prop.
- When a display flag and handler are linked, use a union for the valid prop combinations. Accept a dynamic production boolean with its required handler, while preserving the no-control variant.
- For controls that are interactive unless explicitly read-only, use a union that requires the handler in the interactive variant and models the read-only variant with `disabled: true`; omit the handler property there unless it must be explicitly forbidden.
- Treat a missing-prop typecheck error from a live caller as evidence of a supported runtime state. Revise the contract to model that state.
- Keep adjacent helpers at their established contracts unless live callers require a change; a generic type that defaults to `any` is not evidence for widening.
- When narrowing a component into discriminated modes, verify whether mode-specific flags affect rendered classes or markup. Update support snapshots only when that rendered change is intentional; do not preserve a loose prop solely to avoid snapshot changes.
