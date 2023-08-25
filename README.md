# Provision S3 bucket and DynamoDB table for Terraform remote backend.

The cloudformation template in /backend-infrastructure/code/backend.yaml will create the CloudFormation stack for you. To create the stack, run the command


```bash
aws cloudformation create-stack --stack-name terraform-backend
   --template-body file:///backend-infrastructure/code/backend.yaml
   --parameters ParameterKey=StateBucketName,ParameterValue=<bucket_name_to_create> ParameterKey=LockTableName,ParameterValue=<lock_table_name_to_create>
```
- Replace ```<bucket_name_to_create>``` with your bucket name
- Replace ```<lock_table_name_to_create>``` with your DynamoDB lock table name

You'll need to make sure your AWS CLI credentials have the appropriate permissions to create the S3 bucket and DynamoDB table.
 
And, that's it! You should now have the resources provisioned in AWS.