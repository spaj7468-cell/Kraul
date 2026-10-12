# Arakul Studio integration

## 1. Product boundary

Arakul Studio is the user-facing workspace. Kraul Engine is the separate engine project intended to provide reusable image-processing capabilities. QKC Engine is unrelated to image processing and remains a separate quiz/test engine.

A clean boundary keeps interface decisions in Arakul and reusable processing contracts in Kraul. The precise integration mechanism is not yet verified from source.

## 2. Integration questions to answer from implementation

Before choosing an adapter, determine whether Kraul is imported as a JavaScript module, loaded as a browser script, called through a worker, or exposed through a service; which side owns the source file and returned output; how large binary payloads cross the boundary; how errors and cancellation are represented; whether work runs on the main thread; whether any remote service or network request is involved; and how version compatibility is enforced.

These are investigation questions, not claims about the current architecture.

## 3. Recommended adapter responsibilities

An Arakul-side adapter should, when applicable, validate UI state before invoking the engine; translate UI options into the documented engine contract; keep engine-specific details out of unrelated UI components; map structured engine errors to useful user-facing messages; track operation lifecycle and prevent stale results replacing newer selections; release temporary resources when a workflow is cancelled or a component is removed; and make integration tests possible without requiring a real user interaction for every case.

## 4. Data ownership

Document who owns each input and output. If object URLs are created, state which layer revokes them. If buffers are copied, document where copying occurs and why. If a worker is used, define message payloads and transfer semantics explicitly.

Avoid retaining full-resolution source images longer than necessary. Do not place raw image bytes, private file paths or other user content in routine diagnostic logs.

## 5. Version compatibility

When Kraul exposes a public package or stable interface, record the engine version or contract version expected by Arakul. If the interface changes, update both repositories in the same change window and include a compatibility test.

## 6. Integration test matrix

At minimum, verify successful input-to-output flow; unsupported and corrupt input; cancellation and rapid repeated actions; missing engine or failed initialization; large input at the documented limit; output display and export; cleanup after success and failure; and graceful behavior when the engine version is incompatible.

## 7. Current status

The relationship between Arakul Studio and Kraul Engine is documented at the project level. Exact import paths, method names, message formats and production integration behavior require source evidence and should remain marked unverified until confirmed.
