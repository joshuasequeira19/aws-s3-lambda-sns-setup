# AWS S3, Lambda, and SNS Setup Automation

This repository contains a shell script that automates the setup of various AWS resources, including an IAM role, Lambda function, S3 bucket, and SNS topic. The script performs the following steps:

1. Creates an IAM role named `s3-lambda-sns` and attaches the `AWSLambda_FullAccess` and `AmazonSNSFullAccess` policies to it.
2. Creates a unique S3 bucket named `ghost-cutie-bucket`.
3. Uploads a dummy file to the S3 bucket.
4. Compresses the Lambda function files using `zip -r`.
5. Creates a Lambda function using the compressed file and attaches the `s3-lambda-sns` role.
6. Configures Lambda permissions to allow execution.
7. Creates an SNS topic.
8. Subscribes the specified email to the SNS topic.
9. Sets up an S3 event trigger on the `ghost-cutie-bucket` to invoke the Lambda function when a new object is added.

## Prerequisites

Before running the script, make sure you have:

- AWS CLI installed and configured with appropriate credentials.
- The necessary permissions to create IAM roles, Lambda functions, S3 buckets, and SNS topics.

## Usage

1. Clone this repository:

   ```sh
   git clone https://github.com/your-username/aws-s3-lambda-sns-setup.git

## Ec2 Instance, commands

   ```sh
   sudo su
   
   apt-get upgrade -y && apt-get update -y
   
   apt install zip unzip -y
   
   vim s3-notification-trigger.sh
   
   chmod 777 s3-notification-trigger.sh
   
   mkdir s3-lambda-function
   
   cd s3-lambda-function
   
   vim s3-lambda-function.py
   
   vim requirements.txt
   
   cd ..
   
   vim example_file.txt
   
   ls
   
   apt install awscli -y
   
   aws configure
   
   sh 's3-notification-trigger'

   ```
## Cleanup Instructions

Before proceeding with cleanup, make sure you've backed up any important data or configurations. These steps will delete the resources you've set up using the script.

1. **IAM Role Cleanup:**

   - Go to AWS Management Console.
   - Navigate to IAM (Identity and Access Management).
   - Click on "Roles" in the left-hand menu.
   - Find and select the role named `s3-lambda-sns`.
   - Click on "Delete role."
   - Confirm the deletion.

2. **S3 Bucket Cleanup:**

   - Go to AWS Management Console.
   - Navigate to S3 (Simple Storage Service).
   - Find and click on the bucket named `ghost-cutie-bucket`.
   - If there are any files inside the bucket, delete them first.
   - Once the bucket is empty, click on "Delete bucket."
   - Follow the prompts to confirm the deletion.

3. **Lambda Function Cleanup:**

   - Go to AWS Management Console.
   - Navigate to Lambda.
   - Find and select the function named `s3-lambda-function`.
   - Click on "Actions" button.
   - Choose "Delete function."
   - Confirm the deletion.

4. **SNS Topic Cleanup:**

   - Go to AWS Management Console.
   - Navigate to SNS (Simple Notification Service).
   - Find and select the topic named `s3-lambda-sns`.
   - Click on "Actions" button.
   - Choose "Delete topic."
   - Confirm the deletion.

By following these steps, you'll be cleaning up the resources that were created by the script. Make sure to double-check that you're deleting the correct resources, as these actions cannot be undone.

