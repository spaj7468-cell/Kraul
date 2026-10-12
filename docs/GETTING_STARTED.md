# Kraul Engine — getting started

> Status: contributor guide for the repository as it currently exists. This is not a claim that a distributable engine package or stable runtime API already exists.

## 1. Understand the project boundary

Kraul Engine is the engine project associated with [Arakul Studio](https://spaj7468-cell.github.io/Arakul/). Arakul is the user-facing workspace. Kraul is intended to own reusable image-processing logic, processing contracts, technical implementation and API documentation.

The current repository contains a documentation website and Markdown documents. Before treating Kraul as an installable library, first locate or add the actual runtime source, package metadata, tests and a reproducible build.

## 2. Repository map

- index.html — documentation landing page.
- README.md — project entry point and documentation map.
- docs/OVERVIEW.md — purpose, terminology and boundaries.
- docs/ARCHITECTURE.md — architecture decision record and target module boundaries.
- docs/API.md — rules for recording verified public APIs.
- docs/IMAGE_WORKFLOWS.md — image-processing contracts and workflow design.
- docs/INTEGRATION.md — integration boundary with Arakul Studio.
- docs/ERROR_MODEL.md — error taxonomy and recovery principles.
- docs/TESTING.md — verification strategy.
- docs/SECURITY.md — input, privacy and resource-safety considerations.
- docs/PERFORMANCE.md — benchmark methodology and performance investigation.
- docs/STATUS.md — implementation evidence and status labels.
- docs/ROADMAP.md — staged engineering roadmap.
- docs/CONTRIBUTING.md — contribution and documentation rules.
- docs/GLOSSARY.md — shared terminology.
- docs/FAQ.md — common questions and current limitations.

## 3. First-time contributor checklist

1. Read the overview and status table.
2. Inspect the complete repository tree before adding implementation claims.
3. Identify the runtime language, entry points, package/build files and existing tests.
4. Write down the exact public exports and call sites before changing the API reference.
5. Add a minimal reproducible test for each new behavior.
6. Update the API reference, examples, changelog and status table together.
7. Run the relevant tests and record the exact command and result.
8. Verify the documentation build and deployed Pages URL.

## 4. What a real quick-start needs

A production quick-start should specify a supported installation method, runtime requirements, the exact import or script URL, one minimal working example, expected output, error handling and cleanup. Those details must be added only after the actual runtime entry point and distribution strategy exist.

Do not copy a speculative snippet into an application and assume it works. This repository's documentation is intentionally explicit about the difference between a design contract and verified executable code.

## 5. Current limitations

- The repository currently has no engine source files in its tracked tree; its present contents are documentation and the Pages workflow.
- Exact API names, supported formats, runtime dependencies and processing behavior therefore remain unverified here.
- Background removal, foreground isolation and alpha-channel workflows are project scope, not verified implementation claims.
- Docker/Jekyll is used to build the documentation site; it is not itself the image-processing engine.

## 6. Definition of ready

A feature is ready to document as implemented when a reviewer can find its source, invoke it through a documented interface, run a repeatable test, inspect the result and understand its failure behavior. A landing page or successful documentation build alone does not satisfy this requirement.
