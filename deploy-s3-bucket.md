# AWS S3 CloudFormation Deployment Steps

1. Save the CloudFormation template as `s3-bucket.yaml`.
2. Validate the template locally:
   ```bash
   aws cloudformation validate-template --template-body file://s3-bucket.yaml
   ```
3. Deploy the stack with a stack name and required parameters:
   ```bash
   aws cloudformation deploy \
     --stack-name my-s3-bucket-stack \
     --template-file s3-bucket.yaml \
     --parameter-overrides BucketName=my-unique-bucket-name EnableVersioning=true BlockPublicAccess=true \
     --capabilities CAPABILITY_NAMED_IAM
   ```
4. Confirm stack creation:
   ```bash
   aws cloudformation describe-stacks --stack-name my-s3-bucket-stack
   ```
5. Verify the bucket exists and inspect outputs:
   ```bash
   aws s3api get-bucket-location --bucket my-unique-bucket-name
   ```

> Note: Replace `my-unique-bucket-name` with a globally unique S3 bucket name.
