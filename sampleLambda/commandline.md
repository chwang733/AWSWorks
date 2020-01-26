# Reference for some SAM commands
## Package the application and copy the package to S3 bucket
sam package --template-file template.yaml --output-template-file deploy.yaml --s3-bucket cw-code-upload

## Deploy the application using cloud formation
sam deploy --template-file deploy.yaml --stack-name mySamSampleLambda  --capabilities CAPABILITY_IAM

## Run local unit tests
npm install
npm test

# Run local invocation (requires docker + admin privilege)
sam local invoke --event events/event-cloudwatch-event.json