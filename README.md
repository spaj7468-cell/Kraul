# Kraul Engine

**The engine behind Arakul Studio.** A dedicated project for image-processing workflows, engine architecture, and a documented API.

- **Product / workspace:** [Arakul Studio](https://spaj7468-cell.github.io/Arakul/)
- **Repository:** [spaj7468-cell/Kraul](https://github.com/spaj7468-cell/Kraul)
- **Ecosystem:** [OuRi Corp](https://spaj7468-cell.github.io/ouri-corp/)

> **Documentation status:** initial foundation. The exact public API, runtime behavior, supported formats, and implementation status must be confirmed against source code before being described as stable or available.

## What Kraul is

Kraul Engine is the engine layer associated with Arakul Studio. Arakul Studio is the user-facing workspace; Kraul is the separate technical project that can provide reusable image-processing capabilities and its own API.

The intended domain includes image processing and transformation, background removal and foreground isolation, handling transparent edges and alpha channels, reusable processing operations exposed through a documented API, and integration of engine capabilities into Arakul Studio and potentially other clients. These describe the project direction, not a guarantee that every workflow is already implemented.

## Documentation map

| Document | Purpose |
|---|---|
| [Engine overview](./docs/OVERVIEW.md) | Role, scope, terminology, and system boundaries |
| [API reference](./docs/API.md) | Public API inventory, signatures, parameters, results, and errors |
| [Architecture](./docs/ARCHITECTURE.md) | Modules, data flow, and runtime boundaries |
| [Roadmap and status](./docs/STATUS.md) | Implemented, in-progress, planned, and unverified features |

## API documentation policy

Kraul has its own API. Public API documentation should be derived from the actual implementation and include exact exported names and signatures; accepted input types and supported image formats; parameter defaults and validation rules; return values and output formats; error cases and recovery guidance; runnable examples; and compatibility, performance, and security notes where relevant.

No method names, endpoint URLs, package names, or output guarantees are invented in this starter documentation. They should be added after inspecting the real implementation.

## Suggested repository structure

```text
Kraul/
├── README.md
├── index.html
└── docs/
    ├── OVERVIEW.md
    ├── API.md
    ├── ARCHITECTURE.md
    └── STATUS.md
```

## Relationship to other OuRi projects

- **Arakul Studio** is the creative workspace built around the Kraul engine.
- **Kraul Engine** owns its engine architecture and API documentation.
- **QKC Engine** is a separate JavaScript quiz engine and is not part of Kraul's implementation.
- **OuRi Corp** is the wider project ecosystem.

## Contributing to the documentation

When documenting a capability, label it accurately as **implemented**, **in progress**, **planned**, or **unverified**. Prefer source-backed examples over speculative signatures. When a public API changes, update the API reference and examples together.

---

© 2026 OuRi project ecosystem. License and package distribution details should be stated according to the license and metadata actually present in this repository.
