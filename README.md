# Kraul Engine

**Monochrome engineering identity (QKC design system). The engine project associated with Arakul Studio.**

Kraul Engine is intended to own reusable image-processing workflows, engine architecture and its technical API. Arakul Studio is the user-facing workspace; Kraul is a separate technical project.

- **Documentation site:** https://spaj7468-cell.github.io/Kraul/
- **Arakul Studio:** https://spaj7468-cell.github.io/Arakul/
- **QKC Engine:** https://spaj7468-cell.github.io/qkc-engine/
- **OuRi Corp:** https://spaj7468-cell.github.io/ouri-corp/
- **Repository:** https://github.com/spaj7468-cell/Kraul

> **Important implementation status:** the current repository tree contains the documentation site and its Docker/Jekyll Pages workflow, but no engine runtime source files. Image-processing capabilities described below are project scope and design guidance, not claims that an operational API is already implemented.

## Project boundaries

| Project | Role |
|---|---|
| **Kraul Engine** | Intended image-processing engine, processing contracts and technical API |
| **Arakul Studio** | User-facing creative workspace associated with Kraul |
| **QKC Engine** | Separate dependency-free JavaScript quiz/test engine |
| **OuRi Corp** | Wider project ecosystem |

## Intended domain

The project direction includes image transformations, background removal and foreground isolation, alpha-channel and transparent-edge handling, reusable processing operations, integration with Arakul Studio, and an API documented from actual source code.

These areas must be individually verified before being labelled implemented. No model, processing algorithm, endpoint, package entry point or method signature is assumed by these docs.

## Documentation handbook

| Document | What it covers |
|---|---|
| [Getting started](./docs/GETTING_STARTED.md) | Repository map, contributor workflow and readiness criteria |
| [Overview](./docs/OVERVIEW.md) | Purpose, scope, boundaries and status vocabulary |
| [API reference](./docs/API.md) | Exact exports, signatures, inputs, outputs and errors |
| [Architecture](./docs/ARCHITECTURE.md) | Module boundaries, data flow and runtime decisions |
| [Image workflows](./docs/IMAGE_WORKFLOWS.md) | Input/output contracts, alpha, masks and acceptance criteria |
| [Arakul integration](./docs/INTEGRATION.md) | Adapter boundaries, ownership and compatibility |
| [Error model](./docs/ERROR_MODEL.md) | Proposed taxonomy, validation and safe recovery |
| [Testing strategy](./docs/TESTING.md) | Unit, integration, visual, resource and deployment tests |
| [Security and privacy](./docs/SECURITY.md) | Untrusted input, memory, network and metadata risks |
| [Performance](./docs/PERFORMANCE.md) | Benchmarking, memory estimates and profiling |
| [Contributing](./docs/CONTRIBUTING.md) | Source-backed changes and review requirements |
| [Roadmap](./docs/ROADMAP.md) | Staged path toward a tested runtime |
| [Glossary](./docs/GLOSSARY.md) | Shared technical terminology |
| [FAQ](./docs/FAQ.md) | Current status, Docker, deployment and API questions |
| [Status](./docs/STATUS.md) | Verified vs unverified implementation areas |

## How to read the status labels

- **Implemented** — current source and repeatable tests demonstrate the behavior.
- **In progress** — implementation exists, but is incomplete or not fully verified.
- **Planned** — proposed future work.
- **Unverified** — insufficient source or test evidence.

Do not promote a feature to implemented based only on a design document, a UI mock-up or a green documentation deployment.

## Documentation deployment

The documentation site is built with Docker and Jekyll and published through GitHub Pages using GitHub Actions. A successful Jekyll build proves that the docs build step completed; publication additionally requires the Pages artifact upload and deploy job to succeed.

- [Actions runs](https://github.com/spaj7468-cell/Kraul/actions)
- [Pages settings](https://github.com/spaj7468-cell/Kraul/settings/pages)
- [Live docs](https://spaj7468-cell.github.io/Kraul/)

## Next engineering milestone

The next substantive engine milestone is not another marketing page: add the actual runtime source, select the supported runtime/distribution model, expose one small verified operation, and test it end-to-end. Then replace the API placeholders with exact signatures and executable examples.

© 2026 OuRi project ecosystem.
