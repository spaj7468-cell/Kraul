# Testing and quality strategy

## 1. Purpose

Testing must demonstrate actual engine behavior rather than only verify that the documentation site builds. A green Jekyll/Docker build means the documentation pipeline completed; it does not prove that image-processing features work.

## 2. Test layers

### Static and repository checks
- Confirm expected source, package and workflow files exist.
- Run language-specific lint and type checks if configured.
- Verify documentation links and Markdown formatting.
- Ensure examples do not refer to invented exports.

### Unit tests
- Validate input normalization and boundary conditions.
- Test each pure transformation independently.
- Test error mapping and deterministic behavior where applicable.

### Integration tests
- Exercise the public API from the supported runtime.
- Verify Arakul adapter behavior and ownership rules.
- Test successful and failing processing paths.

### Visual regression tests
For image outputs, compare representative fixtures and inspect edge cases. Use explicit tolerances when exact pixel equality is not appropriate; explain why those tolerances are valid.

### Resource tests
Test repeated processing, cancellation, cleanup, large files at the documented limit and failure paths that allocate temporary resources.

### Documentation and deployment tests
- Build the Pages site.
- Confirm every internal documentation link resolves.
- Confirm the uploaded artifact contains the expected landing page and docs.
- Verify the live URL after deployment.

## 3. Fixture design

Keep a small, legally usable fixture set with known expected properties. Include opaque and transparent images, varied dimensions, challenging boundaries and corrupt or unsupported files. Avoid embedding private user images in the repository.

## 4. Reproducibility

Record the command, runtime version, environment and expected result for every documented test. Benchmarks should specify machine/runtime conditions and warm-up policy. Avoid reporting a performance number without a repeatable procedure.

## 5. Release gates

A release candidate should pass source and package integrity checks; unit and integration tests; image-output regression checks; resource and error-path tests; documentation build and link checks; and deployment verification.

The repository currently has no engine source or test suite in its tree. Do not claim these gates pass until they exist and are executed.
