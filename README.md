# AWS CloudFormation - S3 Event Trigger SQS

This CloudFormation stack deploys an AWS SNS which will have a message in a sns topi whenever a new file is uploaded to an S3 bucket.

## Features
- Automatically triggers a new message in SQS on S3 `ObjectCreated` events.
- SNS & events are managed by AWS CloudFormation.
- Permissions to access the S3 bucket and invoke the SNS:Publish are managed via IAM roles/ TopicPolicy.

## Architecture
The stack consists of:
1. **S3 Bucket**: The source of the file uploads.
2. **SNS**: Contain messages for files uploaded to the S3 bucket.
3. **S3 Bucket Notifications**: Configured to invoke the SNS when a new file is uploaded.


## Prerequisites
- AWS CLI configured or access to AWS Management Console.

## Deployment Instructions

### 1. Create the CloudFormation Stack

#### Using AWS CLI
1. aws cloudformation create-stack --stack-name S3EventToSNSStack --template-body file://cftemplate.json --capabilities CAPABILITY_NAMED_IAM --profile  my-profile

** You can replace profile with your profile
