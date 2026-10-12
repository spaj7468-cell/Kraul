# Kraul Engine — implementation status

This page distinguishes repository evidence from project intent. It must be updated when runtime source and tests are added.

## Repository-level status

| Area | Current status | Evidence / next action |
|---|---|---|
| Documentation website | Present | index.html and Markdown docs are tracked |
| Docker/Jekyll documentation build | Configured | GitHub Actions workflow builds the docs site |
| GitHub Pages deployment | Configured in workflow | Confirm the latest run has both successful build and deploy jobs |
| Relationship to Arakul Studio | Documented at project level | Verify exact integration calls from future source |
| Engine runtime source | Not present in current tracked tree | Add implementation and supported runtime |
| Public API inventory | Unverified | Inspect actual exports and call sites after source is added |
| Input image formats | Unverified | Inspect decoders and tests |
| Background removal | Intended scope; implementation unverified | Add code and runnable tests |
| Foreground isolation | Intended scope; implementation unverified | Add code and runnable tests |
| Alpha / transparent-edge handling | Intended scope; implementation unverified | Add output pipeline and visual tests |
| Error behavior | Design guidance documented; runtime behavior unverified | Implement and test exact errors |
| Performance limits | Not measured | Add reproducible benchmarks |
| Engine automated tests | Not present in current tree | Add test runner and fixtures |
| Security review | Guidance documented; implementation review pending | Audit input handling and network behavior |

## Status definitions

- **Implemented:** current source and repeatable tests prove the behavior.
- **In progress:** implementation exists but is incomplete or not fully verified.
- **Planned:** intended future work.
- **Unverified:** insufficient source or test evidence.

## Important distinction

A green Docker/Jekyll build proves that the documentation site can be built. It does not prove that Kraul performs image processing. A successful Pages deployment proves the docs were published, not that the engine runtime exists.

## Next verification steps

1. Add the actual runtime source tree and define the supported environment.
2. Implement one small vertical slice with a documented input and output contract.
3. Add valid, invalid and boundary tests.
4. Replace API placeholders with exact exports and executable examples.
5. Verify the Arakul integration against the actual interface.
6. Add performance, resource and privacy evidence.
7. Update this table only when the corresponding evidence exists.
