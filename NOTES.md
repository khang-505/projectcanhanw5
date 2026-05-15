# Lambda Strategy

Chosen strategy: serverless-http adapter.

Reasons:
- It keeps `app.js` framework-pure and unchanged.
- It requires only one new entrypoint file (`lambda.js`) and one npm dependency.
- It is the simplest adapter that maps Express to Lambda without adding complex custom plumbing.
- It matches the workshop guidance for a minimal adapter and low code-change cost.

Implementation details:
- Added `serverless-http` to `package.json` dependencies.
- Created `lambda.js` exporting `handler`.
- Updated `template.yaml` handler to `lambda.handler`.
cold start:
2026/05/15/[$LATEST]26110e03ac3247e8829a4f05d3d72a1c 2026-05-15T08:12:43.039000+00:00 REPORT RequestId: 58f6a705-f086-4cba-87df-94cc1c75eccf       Duration: 47.64 ms      Billed Duration: 48 ms  Memory Size: 512 MB        Max Memory Used: 95 MB
XRAY TraceId: 1-6a06d57a-53f23bea7a70dbec27af7faa       SegmentId: 37a584f0bf881ece     Sampled: true
2026/05/15/[$LATEST]26110e03ac3247e8829a4f05d3d72a1c 2026-05-15T08:12:57.609000+00:00 START RequestId: 775d2f09-3e77-46a9-b4a3-f2a8e8a619da Version: $LATEST
2026/05/15/[$LATEST]26110e03ac3247e8829a4f05d3d72a1c 2026-05-15T08:12:57.617000+00:00 END RequestId: 775d2f09-3e77-46a9-b4a3-f2a8e8a619da
2026/05/15/[$LATEST]26110e03ac3247e8829a4f05d3d72a1c 2026-05-15T08:12:57.617000+00:00 REPORT RequestId: 775d2f09-3e77-46a9-b4a3-f2a8e8a619da       Duration: 6.66 ms       Billed Duration: 7 ms   Memory Size: 512 MB        Max Memory Used: 95 MB
XRAY TraceId: 1-6a06d589-597c20290316e04350998d09       SegmentId: 5eae450da1cc4cd0     Sampled: true