# Performance and resource management

## 1. Measure before optimizing

Do not publish performance claims from intuition. A useful benchmark identifies the input dimensions, format, operation, runtime, hardware, warm-up, number of iterations, and the statistic reported, such as median and tail latency.

## 2. What to measure

Depending on the actual implementation, measure input decode duration; processing duration by stage; output encode duration; total wall-clock duration; peak memory or a defensible proxy; output file size; cancellation latency; and behavior under repeated and concurrent operations.

Do not add unsupported metrics merely because they look impressive on a dashboard.

## 3. Image memory estimates

An uncompressed RGBA buffer uses approximately four bytes per pixel before accounting for extra copies, masks, model memory, decoder overhead or intermediate buffers. For example, a 4000 × 3000 RGBA image requires about 48,000,000 bytes (roughly 45.8 MiB) for one buffer alone. Multiple full-size copies can multiply that cost.

Use this estimate to motivate input limits and ownership discipline, not as a claim about Kraul's measured memory consumption.

## 4. User experience

Long operations should not block the interface unnecessarily. If the implementation supports workers or asynchronous processing, document where work runs and how progress/cancellation are communicated. Do not claim progress reporting if only start/end events exist.

## 5. Optimization order

1. Reproduce the slow case.
2. Profile stages independently.
3. Reduce unnecessary decode/encode cycles and copies.
4. Bound concurrency and intermediate storage.
5. Consider workers, streaming or tiled processing only if the runtime and algorithm support them.
6. Re-run correctness and visual regression tests after every optimization.

## 6. Benchmark reporting template

For each result record the commit/version; environment and runtime; source dimensions and format; operation and options; number of repetitions; median and p95 if sample size is sufficient; memory measurement method; and known caveats.

## 7. Current status

No Kraul runtime source or benchmark suite is present in the current repository tree. No speed, latency, memory or throughput claims should be published until measurements are made.
