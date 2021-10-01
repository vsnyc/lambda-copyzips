This application creates a Lambda function that can be invoked from another template responsible for copying files to an Amazon S3 bucket in local Region for use with AWS Lambda.

## SAM build, package, and deploy
1. Ensure that you have [SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) installed.

2. To build the package, from the project root:

   `sam build -t templates/copy-zips.template.yaml`
3. To package:

   `sam package --s3-bucket aws-cfn-samples --s3-prefix serverless-survey --output-template-file packaged.yaml`

4. Deploy using SAM

   `sam deploy --template-file packaged.yaml --stack-name <YOUR STACK NAME>`

5. Publish to Serverless Application Repository
   `sam publish --template packaged.yaml --region us-east-1`