# Kraul Engine — overview

## Mission

Kraul Engine is the separate engine project associated with Arakul Studio. The project direction is to provide reusable image-processing capabilities behind a clear, documented technical interface.

Arakul Studio is the workspace people interact with. Kraul is intended to own engine-level processing contracts and implementation. QKC Engine is a separate JavaScript quiz/test engine.

## Intended scope

The intended domain includes image transformations, background removal and foreground isolation, alpha-channel and transparent-edge handling, reusable processing operations, and integration into Arakul Studio. These are project goals; actual availability must be proven by source code and repeatable tests.

## Current repository reality

The current tracked repository contains the documentation website, Markdown documentation and the GitHub Pages workflow that builds the docs with Docker/Jekyll. It does not currently contain engine runtime source files. Therefore there are no source-backed public method names, package entry points, verified processing operations or measured performance results to report yet.

## Project boundaries

- **Kraul Engine:** intended processing implementation, API contracts, technical architecture and engine tests.
- **Arakul Studio:** user-facing workspace, interaction design and product workflow.
- **QKC Engine:** separate quiz/test engine with its own API and documentation.
- **OuRi Corp:** wider project ecosystem.

## Documentation status vocabulary

- **Implemented:** verified in current source and repeatable tests.
- **In progress:** implementation exists but is incomplete or not fully verified.
- **Planned:** future work that has not been implemented.
- **Unverified:** evidence is not sufficient to confirm the behavior.

## Design principles

1. **Evidence before claims.** Source and tests determine what is implemented.
2. **Explicit contracts.** Inputs, outputs, limits, errors and ownership are documented.
3. **Safe resource use.** Image sizes and temporary allocations require deliberate limits.
4. **Clear boundaries.** UI, engine, documentation build and deployment are different concerns.
5. **Reproducibility.** Examples, tests and benchmarks must be repeatable.
6. **Honest status.** Planned capabilities must not be marketed as completed behavior.

## What “ready” means

A capability is ready to call implemented only when source code exists, a public interface is defined, valid and invalid cases are tested, outputs are inspectable, resource cleanup is understood and documentation matches the current implementation.

## Related projects

- [Arakul Studio](https://spaj7468-cell.github.io/Arakul/)
- [QKC Engine](https://spaj7468-cell.github.io/qkc-engine/)
- [OuRi Corp](https://spaj7468-cell.github.io/ouri-corp/)
