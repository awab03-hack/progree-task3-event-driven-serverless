# Progree Cloud Computing – Task 3

## Event-Driven Serverless Architecture with AWS

This project demonstrates an event-driven serverless workflow using Amazon S3, AWS Lambda, and Amazon CloudWatch.

### Architecture

**Amazon S3 → S3 Object Created Event → AWS Lambda → Amazon CloudWatch Logs**

### Project Objective

The objective of this project is to build a serverless, event-driven workflow where uploading a file to an Amazon S3 bucket automatically triggers an AWS Lambda function.

### AWS Services Used

- Amazon S3 – Stores uploaded objects.
- AWS Lambda – Executes Python code automatically when an S3 object is created.
- Amazon CloudWatch – Stores and displays Lambda execution logs.
- AWS IAM – Provides the permissions required for Lambda execution and logging.

### How It Works

1. A file is uploaded to the S3 bucket.
2. Amazon S3 generates an Object Created event.
3. The S3 event triggers the Lambda function.
4. Lambda reads the event and extracts the bucket name and uploaded file name.
5. Lambda writes the result to Amazon CloudWatch Logs.
6. CloudWatch confirms that the event was processed successfully.

### Lambda Function

The Lambda function is written in Python and processes the S3 event.

### Test Result

A file named `test.txt` was uploaded to the S3 bucket after the trigger was configured.

CloudWatch Logs confirmed:

- `S3 Event Received!`
- The S3 bucket name
- `File: test.txt`
- Successful Lambda execution

### Result

The project successfully demonstrates:

**S3 upload → automatic Lambda execution → CloudWatch logging**

### Key Learning

This project provided practical experience with:

- Event-driven architecture
- Serverless computing
- AWS Lambda
- Amazon S3 event notifications
- CloudWatch monitoring and logging
- Python on AWS
- IAM permissions

### Project Status

**Completed and tested successfully.**

> Never upload AWS Access Keys, Secret Keys, passwords, or other sensitive credentials to GitHub.
