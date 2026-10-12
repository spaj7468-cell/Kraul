# Image-processing workflows and contracts

> This document defines what must be specified and verified for image workflows. It does not claim that these processing features are already implemented.

## 1. Workflow model

A reliable image-processing workflow can be documented as a sequence of explicit stages:

1. **Acquire** — receive a file, blob, byte buffer, URL or decoded image, depending on what the implementation actually supports.
2. **Validate** — reject missing, malformed, oversized or unsupported inputs before expensive work begins.
3. **Normalize** — establish a documented pixel representation, color space, orientation policy and alpha convention.
4. **Process** — run the selected operation using the real implementation and its declared dependencies.
5. **Compose** — combine the processed foreground, mask or other intermediate data only when the operation requires it.
6. **Encode** — serialize the result into a supported output representation.
7. **Return** — deliver a typed result, progress information if supported, and actionable error details.
8. **Release** — free object URLs, temporary buffers, workers or other resources owned by the workflow.

The actual Kraul implementation may use a different sequence. Update this description after source code and tests establish the real data flow.

## 2. Input contract checklist

Every operation should define accepted input types and ownership; supported formats and detection behavior; whether MIME type, file extension or decoded content is authoritative; maximum file size and dimensions where limits exist; handling for animated images, metadata, color profiles and orientation; behavior for corrupt files; and whether remote URLs are allowed.

Do not silently equate a filename extension with validated content.

## 3. Alpha and transparency

Transparency must be described precisely. Record whether alpha is straight or premultiplied at each boundary, whether RGB values under fully transparent pixels are preserved or normalized, and how antialiased edges are represented.

Visual tests should include:
- opaque foreground against a contrasting background;
- fine hair, fur, leaves or other thin edges;
- semi-transparent glass or soft edges;
- dark foreground on dark background and light foreground on light background;
- transparent output opened over both light and dark canvases;
- repeated encode/decode cycles to expose halos or color shifts.

Do not claim edge quality, losslessness or support for a particular format without reproducible tests.

## 4. Masks and foreground isolation

If the implementation produces a mask, document its data type, dimensions, channel layout, value range and interpretation. State whether white means keep or remove, how soft boundaries are encoded, and how mask dimensions map to the source image.

If a foreground-isolation operation returns a cutout, specify whether the result contains an alpha channel, a separate mask, or both. Do not invent an API shape before inspecting the implementation.

## 5. Output contract

For each output type, record exact MIME type and extension; pixel dimensions and color-space behavior; alpha-channel preservation; metadata retention or stripping; compression settings and quality controls; output size limits; and whether the returned object is a file, blob, URL, buffer or another structure.

## 6. Repeatability and cancellation

If an operation is deterministic, test identical inputs across repeated runs and supported environments. If it is nondeterministic, document the source of variation.

Cancellation and progress must be documented only if the implementation exposes them. Specify cancellation timing, cleanup behavior, and whether partial output can be returned. A UI spinner is not proof that processing progress is measurable.

## 7. Workflow acceptance criteria

A workflow is accepted only when valid inputs produce a documented output; invalid inputs fail predictably; limits are enforced before unbounded allocation; alpha and color behavior are tested; resource cleanup is tested; examples use the actual public interface; and status documentation points to evidence.

## 8. Known status

The current Kraul repository documents image processing, background removal, foreground isolation and alpha-channel handling as intended scope. The actual engine source is not present in the current repository tree, so none of these workflows should be marked implemented on documentation alone.
