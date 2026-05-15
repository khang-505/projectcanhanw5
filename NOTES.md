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

# step 4
- $API = aws cloudformation describe-stacks --stack-name khangsam --region us-west-2 --query "Stacks[0].Outputs[?OutputKey=='ApiUrl'].OutputValue" --output text
- echo $API
- curl.exe $API
- curl.exe "$API/api/hello/Lan"
- Invoke-RestMethod -Uri "$API/api/echo" -Method POST -ContentType "application/json" -Body '{"hi":"there"}'
