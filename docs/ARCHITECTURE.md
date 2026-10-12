# Kraul Engine architecture

> **Status: target architecture and audit checklist.** The current repository tree does not contain engine runtime modules. This document records boundaries and questions to answer, not a fabricated description of existing implementation internals.

## 1. System boundary

Kraul is intended to be the reusable engine layer associated with Arakul Studio. Arakul owns the user-facing workspace and interaction patterns. Kraul should own engine-level processing contracts and the behavior exposed to callers. QKC Engine is a separate project and must not be treated as a Kraul dependency.

## 2. Proposed conceptual layers

These are conceptual responsibilities, not existing source folders:

1. **Public facade** — stable entry points and API validation.
2. **Input adapters** — accepted image source types and format decoding.
3. **Processing operations** — concrete algorithms that actually exist in the implementation.
4. **Output adapters** — result encoding and export.
5. **Runtime coordination** — asynchronous work, cancellation and resource lifecycle if supported.
6. **Diagnostics** — structured safe errors and measurable operation stages.
7. **Integration adapter** — mapping between Arakul UI actions and engine contracts.
8. **Tests and fixtures** — reproducible verification of contracts and image output.

Do not create abstractions before a real operation requires them. The architecture should follow working behavior, not the reverse.

## 3. Data-flow record

For every operation, trace:
- where input originates;
- where type, format and dimension checks occur;
- how decoding and normalization work;
- which processing stages run and in what order;
- whether intermediate buffers are copied or transferred;
- how output is encoded;
- which component owns cleanup;
- how failure and cancellation propagate.

## 4. Runtime decisions that need evidence

Record the actual runtime and module system; browser or server requirements; external dependencies; whether processing is local or remote; use of workers or services; supported file formats; build and distribution outputs; and version compatibility. Do not infer these from the documentation site's Dockerfile.

## 5. Resource ownership

Every buffer, worker, object URL, temporary file and processing job should have a clearly defined owner. Ownership should remain clear after errors, cancellation, repeated user actions and component teardown.

## 6. Arakul integration boundary

The studio should call Kraul through a documented adapter rather than scattering undocumented engine-specific assumptions across UI components. Integration must define input/output ownership, error translation, version expectations and cancellation behavior. Exact calls remain unverified until source exists.

## 7. Quality attributes

### Correctness
The same documented input should obey the declared contract. Determinism should be claimed only when tested.

### Reliability
Malformed inputs and environmental failures should fail predictably without corrupting unrelated state.

### Performance
Measure decode, process and encode stages separately. Avoid unsupported speed claims.

### Privacy
State whether inputs remain local or leave the device. Never promise local-only behavior without inspecting runtime and network behavior.

### Maintainability
Keep the public facade small, internal operations testable and docs tied to actual exports.

## 8. Architecture decision records

For every significant design decision, record the context, options considered, chosen option, trade-offs, status and date. Revisit decisions when the actual runtime or processing approach changes.

## 9. Current evidence gap

The current tracked tree contains README, documentation Markdown, the HTML documentation page and a Docker/Jekyll workflow. No processing modules, package manifest or engine tests are present. The architecture is therefore documented as a target and audit framework until implementation is committed.
