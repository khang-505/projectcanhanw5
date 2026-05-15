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
