# Kraul Engine API reference

> Initial reference structure. The exact API must be populated from the implementation; do not guess exported names or signatures.

## API inventory

For every public export or callable method, document the exact name and signature, purpose and status, accepted input types and image formats, parameters and defaults, return type and output format, errors and recovery behavior, a runnable example, and compatibility/performance notes where verified.

## Image-processing contracts to document

If supported by the implementation, document the actual contracts for source image input and decoding; background removal/foreground isolation; alpha channel and transparent-edge handling; output encoding and export; cancellation, progress, and error reporting.

These topics are a documentation checklist, not a statement that each API is implemented.

## Examples

Add only source-verified examples here. Each example should run against the current version and identify any required runtime, dependencies, or browser capabilities.
