# Architecture – Progree Task 3

## Event Flow

```text
                    ┌─────────────────────┐
                    │     Amazon S3       │
                    │                     │
                    │  Upload: test.txt   │
                    └──────────┬──────────┘
                               │
                               │ Object Created Event
                               ▼
                    ┌─────────────────────┐
                    │     AWS Lambda      │
                    │                     │
                    │ Python Function     │
                    │ Reads S3 Event      │
                    └──────────┬──────────┘
                               │
                               │ Execution Logs
                               ▼
                    ┌─────────────────────┐
                    │   Amazon CloudWatch │
                    │                     │
                    │ S3 Event Received!  │
                    │ Bucket: ...         │
                    │ File: test.txt      │
                    └─────────────────────┘
```

## Components

### Amazon S3
The S3 bucket stores objects. An Object Created event is configured to invoke the Lambda function.

### AWS Lambda
The serverless Python function receives the S3 event and prints the bucket name and uploaded object key.

### Amazon CloudWatch
CloudWatch Logs provides evidence that the Lambda function was invoked and processed the S3 event successfully.

## Trigger Configuration

- Event type: All object create events
- Prefix: None
- Suffix: None

## Test

Uploading `test.txt` triggered the Lambda function successfully, and the expected event information appeared in CloudWatch Logs.
