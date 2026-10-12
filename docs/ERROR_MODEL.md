# Error model and recovery

> This is a proposed error-documentation contract. It must be mapped to the actual implementation before being described as the runtime's current behavior.

## 1. Principles

Errors should be predictable, actionable and safe to display. A caller should be able to distinguish invalid user input from unsupported capability, environmental failure, resource exhaustion and an internal defect without parsing a fragile human-readable sentence.

Do not expose stack traces, private paths, image contents, credentials or raw third-party service responses in user-facing messages.

## 2. Suggested categories

| Category | Meaning | Typical caller response |
|---|---|---|
| Invalid input | Missing or malformed value | Ask for corrected input |
| Unsupported input | Format or operation not supported | Explain supported alternatives |
| Limit exceeded | Size or resource limit reached | Ask for a smaller input or safer settings |
| Decode/encode failure | Input or output could not be decoded or encoded | Keep the original and report failure |
| Processing failure | A processing stage failed | Offer retry when safe; retain privacy-safe diagnostics |
| Cancelled | Caller or user requested cancellation | Stop progress UI without treating it as a crash |
| Environment unavailable | Required browser feature, worker or dependency is unavailable | Explain the requirement or use a supported fallback |
| Internal error | Unexpected implementation failure | Report a generic message and provide a correlation ID if available |

These labels are a proposed taxonomy, not confirmed exception names exported by Kraul.

## 3. Error object fields

If structured errors are implemented, document the real fields and types. A useful design may include a stable code, safe message, optional cause, retryability, and stage. Never document fields until the implementation returns them.

## 4. Validation order

Validate cheaply before expensive work: required argument presence; type and shape; supported format; declared size and dimensions; environmental capability; processing-specific constraints. This order reduces avoidable allocations and gives callers clearer feedback.

## 5. Retry safety

Retry only when the failure is plausibly transient and the operation is safe to repeat. Do not automatically retry invalid input. Avoid infinite retry loops. If work may have side effects, define idempotency before recommending retries.

## 6. Logging and privacy

Diagnostics should include operation stage, stable error code, duration and safe metadata where useful. They should not include image bytes, base64 data, full local paths, authentication material or unnecessary user-identifying data.

## 7. Verification requirements

Tests should cover each public error category, malformed inputs, resource limits, cleanup after partial failure and stable user-facing messages. When actual Kraul source exists, replace this proposal with exact error codes, thrown values, return shapes and tested examples.
