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
# step 5
Cold start:
-REPORT RequestId: 58f6a705-f086-4cba-87df-94cc1c75eccf       Duration: 47.64 ms      Billed Duration: 48 ms  Memory Size: 512 MB        Max Memory Used: 95 MB
