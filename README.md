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
