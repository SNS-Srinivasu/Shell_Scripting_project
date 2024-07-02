# AWS S3 Event Triggering

NOTE: REPLACE YOUR AWS ACCOUNT ID IN THE LAMBDA FUNCTION CODE.

1-Objective:
 Automate the setup of AWS resources to handle events in an S3 bucket using Lambda functions and SNS notifications.
 
2-Script Type: 
Bash script (#!/bin/bash) for automation tasks.

3-AWS Account Setup:
Retrieves AWS account ID using aws sts get-caller-identity.Prints AWS account ID for verification.

4-AWS Resources Configuration:
Sets AWS region (us-east-1), bucket name (your bucket name), Lambda function name (s3-lambda-function), IAM role name (s3-lambda-sns), and email address for notifications (yourgmail@gmail.com).

5-IAM Role Creation:
Creates an IAM role (s3-lambda-sns) with permissions (AWSLambda_FullAccess, AmazonSNSFullAccess) for Lambda, S3, and SNS services. 

6-S3 Bucket Creation:
Creates an S3 bucket (your bucket name) in the specified AWS region (us-east-1).

7-File Upload:
Copies an example file (example_file.txt) to the newly created S3 bucket for testing purposes.

8-Lambda Function Deployment:
Zips the contents of s3-lambda-function directory into s3-lambda-function.zip.
Creates a Lambda function (s3-lambda-function) with Python 3.8 runtime, specified handler, memory size, timeout, IAM role, and uploaded zip file.

9-S3 Event Trigger Configuration:
Configures the S3 bucket (your bucket name) to trigger the Lambda function (s3-lambda-function) upon s3:ObjectCreated:* events.

10-SNS Topic Creation:
Creates an SNS topic (s3-lambda-sns) and retrieves the topic ARN.

11- Subscription:
Subscribes the Lambda function (s3-lambda-function) to the SNS topic (s3-lambda-sns) using email protocol and specified endpoint (yourgmail@gmail.com).

12-Notification:
Publishes a notification message ("script is successfully running") to the SNS topic (s3-lambda-sns) to verify functionality.

13-Error Handling:
Uses -x flag for script debugging and error detection during execution.

14-Adjustments:
Requires adjusting variables (bucket_name, aws_region, etc.) based on specific AWS environment and project requirements.

15-Execution:
Executed as a Bash script (./script.sh) on a local machine or AWS environment with appropriate AWS CLI configured.


