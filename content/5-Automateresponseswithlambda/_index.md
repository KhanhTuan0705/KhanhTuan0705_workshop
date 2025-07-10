--- 
title : "Automate Responses with AWS Lambda"
date: 2025-07-06
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

{{% notice info %}}
AWS Lambda helps you automate responses when events occur in AWS. You can use Lambda to trigger automated actions when GuardDuty detects threats.
{{% /notice %}}

## Introduction to AWS Lambda

**AWS Lambda** is a serverless computing service from AWS that allows you to run code without managing servers. Lambda helps you process events in real-time and perform automated actions when events occur from other AWS services like GuardDuty, S3, and SNS.

---

**Benefits**:
- **No server management required**: Lambda runs code automatically when an event occurs without requiring you to manage servers.
- **Automatic scalability**: Lambda automatically scales to handle requests, saving resources and costs.
- **Integration with AWS services**: Lambda can easily integrate with AWS services like GuardDuty to perform actions when a threat is detected.

### Content
  - [Create Lambda Function](5.1-createlambdafunction/)
  - [Create EventBridge Rule to Connect GuardDuty with Lambda](5.2-createeventbridgerule/)

