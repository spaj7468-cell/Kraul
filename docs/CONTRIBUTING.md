# Contributing to Kraul Engine

## 1. Start with evidence

Before implementing or documenting a feature, inspect the current repository tree and open related source and tests. Do not assume the design has already been implemented because it appears in a roadmap or landing page.

## 2. Keep changes focused

A change should have one clear purpose. Update related API docs, examples, tests, changelog and status records in the same change when public behavior changes.

## 3. API change checklist

- [ ] Confirm the actual exported symbol and signature.
- [ ] Define input validation and output shape.
- [ ] Define failure and cancellation behavior.
- [ ] Add a runnable test.
- [ ] Add a source-verified example.
- [ ] Update compatibility notes.
- [ ] Mark the implementation status with evidence.

## 4. Documentation style

Use direct language. Distinguish **implemented**, **in progress**, **planned** and **unverified**. Prefer exact types, examples and constraints over marketing language. Never describe an intended feature as available without a test or source reference.

## 5. Code quality expectations

For implementation changes, include relevant tests, avoid unnecessary dependencies, consider resource ownership and cleanup, and preserve backward compatibility unless a breaking change is explicitly intended.

## 6. Review checklist

Reviewers should be able to answer what behavior changes, what evidence proves it works, what happens on invalid input, whether there are memory/performance/privacy/security implications, whether docs match code, and whether the change can be reproduced from a clean checkout.

## 7. Releases

A release should identify the commit, runtime/package requirements, tested behavior, known limitations and any breaking changes. Do not publish package installation instructions until a real package manifest and distributable entry point exist.
