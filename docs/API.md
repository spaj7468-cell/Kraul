# Kraul Engine API reference

> **Status: source audit required.** The current repository contains no engine runtime source exports. This document defines the inventory that must be completed when the implementation is added; it does not invent method names or claim a stable API exists.

## 1. API design goals

A public API should be explicit, small enough to understand, consistent across operations and testable without depending on the UI. It should make input ownership, asynchronous behavior, output shape, error behavior and resource cleanup clear.

Do not add public methods solely because they appear in a documentation example. The source code is the authority.

## 2. Export inventory template

For every actual public export, record:

| Field | Required detail |
|---|---|
| Exact name | Case-sensitive exported identifier |
| Availability | Implemented, in progress, planned or unverified |
| Runtime | Supported environments and requirements |
| Signature | Exact parameters and return type |
| Input | Accepted shapes, formats, limits and ownership |
| Defaults | Real defaults and option precedence |
| Output | Exact type, dimensions, encoding and alpha behavior |
| Errors | Actual error codes, thrown values or result variants |
| Lifecycle | Cleanup, cancellation and resource ownership |
| Example | Minimal example verified against the current source |
| Compatibility | Version introduced, changed or deprecated |
| Evidence | Source path and tests proving the contract |

## 3. Contracts to document if implemented

### Input acquisition and decoding
Document whether callers provide a File, Blob, byte buffer, URL or decoded pixels. State supported formats, MIME behavior, size limits, metadata policy and malformed-input behavior.

### Background removal and foreground isolation
Document the actual entry point, required options, result representation, mask semantics, alpha convention, limitations and tested edge cases. Do not claim a particular model or quality level without evidence.

### Alpha and transparent edges
Specify straight versus premultiplied alpha, color-space assumptions, antialiasing behavior and whether RGB values beneath transparent pixels are preserved.

### Encoding and export
List actual formats, MIME types, compression controls, metadata behavior, output dimensions and the exact return type.

### Async work, progress and cancellation
Document promise/callback behavior, progress granularity, cancellation timing and cleanup only if the runtime implements these capabilities.

## 4. Validation contract

Every public operation should document required arguments, type/shape checks, supported format checks, resource limits and behavior when validation fails. Validation should happen before expensive allocations where possible.

## 5. Error contract

Use the actual implementation's error representation. For each error, record a stable identifier if one exists, a safe user-facing message, whether retry is appropriate and what resources have already been released. The proposed categories in [Error model](./ERROR_MODEL.md) are guidance, not current Kraul exception names.

## 6. Example policy

Every example must:
1. run against the current checked-in implementation;
2. identify its runtime and import path;
3. show realistic input;
4. handle failure;
5. explain output ownership and cleanup;
6. avoid depending on undeclared external services.

Examples that have not been executed must be marked illustrative rather than runnable.

## 7. API compatibility

When a real public API is introduced, define a versioning policy before consumers depend on it. Document breaking changes, deprecations and migration paths. Keep Arakul integration tests aligned with any interface change.

## 8. Completion checklist

- [ ] Runtime source exists and exports are inventoried.
- [ ] Every signature matches source.
- [ ] Inputs, defaults, outputs and errors are specified.
- [ ] Examples run in CI or a documented reproducible environment.
- [ ] Resource ownership and cleanup are covered.
- [ ] Compatibility notes match the release.
- [ ] Status labels are evidence-backed.
