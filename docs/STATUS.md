# Kraul Engine — implementation status

This page separates project intent from verified implementation.

| Area | Initial status | What is needed to verify |
|---|---|---|
| Relationship to Arakul Studio | Documented | Confirm integration details from source |
| Public API inventory | Needs source audit | Inspect actual exports and call sites |
| Input image formats | Unverified | Inspect decoders and tests |
| Background removal | Intended scope; implementation unverified | Locate implementation and runnable tests |
| Foreground isolation | Intended scope; implementation unverified | Locate implementation and runnable tests |
| Alpha / transparent-edge handling | Intended scope; implementation unverified | Inspect output pipeline and visual tests |
| Error behavior | Needs source audit | Inspect errors, result types and tests |
| Performance limits | Needs measurement | Add reproducible benchmarks |

Update this table as the repository develops. Do not mark a feature implemented until source code or a reproducible test demonstrates it.
