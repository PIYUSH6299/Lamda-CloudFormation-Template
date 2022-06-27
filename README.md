# cloud formation template to deploy a lambda function with the following

1. An SQS queue which subscribes to a SNS topic based on a particular message type
2. A lambda function which is listening to the SQS Queue (in point 1) events and writing the
messages body to s3
3. S3 bucket configured with versioning and lifecycle polices for that data
4. Necessary policies and roles required for this use-case


Template will invoke the following:-

Parameters:

* Parameter for SQS queue which subscribes to a SNS topic

Resouces:

* Create a IAM role for Lamda function with the AWS Managed policy allowLambdaLogs, allowSqs
* Create a SQS subcription based on  particular message type
* Create a LambdaFunction in that we mentioned S3 bucket with versioning and lifecycle polices
* Create a LambdaExecutionRole in S3 bucket
* create a LambdaFunctionEventSourceMapping for events
* Create a Resource for VisibilityTimeout