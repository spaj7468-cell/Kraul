# Kraul Engine roadmap

This roadmap is a proposed sequence for developing the project. It is not a promise that a feature is implemented or scheduled for a specific release.

## Stage 0 — Repository and docs foundation
- [x] Documentation landing page and initial project boundary.
- [x] Docker/Jekyll build and GitHub Pages deployment workflow.
- [x] Expanded engineering guides and terminology.
- [ ] Add engine source files and define the supported runtime.
- [ ] Add a minimal automated test command.

## Stage 1 — Define the public contract
- [ ] Decide the runtime and distribution format.
- [ ] Define input/output ownership and supported formats.
- [ ] Define validation and structured error behavior.
- [ ] Add one small, working, source-backed end-to-end example.
- [ ] Establish compatibility/versioning policy.

## Stage 2 — Implement and test a vertical slice
- [ ] Select one operation and implement it end-to-end.
- [ ] Add positive, negative and boundary tests.
- [ ] Test transparency and output encoding where relevant.
- [ ] Document actual performance and resource limits.
- [ ] Connect the verified operation to Arakul Studio through a clear adapter.

## Stage 3 — Reliability and integration
- [ ] Add cleanup and cancellation tests where supported.
- [ ] Add regression fixtures and repeatable benchmarks.
- [ ] Document privacy/network behavior and dependency inventory.
- [ ] Verify integration failure handling.
- [ ] Add CI checks for code, tests, docs and deployment.

## Stage 4 — Stabilization
- [ ] Publish versioned API documentation.
- [ ] Define supported environments and compatibility guarantees.
- [ ] Establish release notes and deprecation policy.
- [ ] Audit documentation against the released source.

## Release rule

Do not move a feature to “implemented” or “stable” until its code exists, its behavior is covered by repeatable tests, and its public contract matches the current release.
