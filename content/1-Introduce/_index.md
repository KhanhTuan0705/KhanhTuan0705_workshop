---
title: "Introduction"
date: 2024-06-16
weight: 1
chapter: false
pre: " <b>1.</b> "
---


### Objective  
In today's digital era, security threats to cloud infrastructure are becoming increasingly common and sophisticated. This project is designed to build a system that **automatically detects and responds** to suspicious activities on EC2 instances, helping to minimize security risks and enhance overall system protection.

### System Overview  
The system leverages a combination of AWS services to ensure monitoring and response processes are performed automatically and efficiently:

- **Amazon GuardDuty**: Detects abnormal behaviors on EC2 such as port scans, unauthorized access, etc.
- **Amazon EventBridge**: Captures events from GuardDuty and triggers automated responses.
- **AWS Lambda**: Handles GuardDuty findings, performs actions such as stopping EC2 instances or sending alerts.
- **Amazon SNS**: Sends alerts to administrators via email or SMS.

These services work together to form a tightly integrated system for monitoring, automated response, and alerting.

### Use Cases  

- **Detecting and responding to port scanning attacks.**
- **Stopping EC2 instances** when suspicious activity is detected.
- **Instantly notifying administrators** of security-related events.
- **Automating the entire incident response process.**

> The system not only enables timely detection of threats but also minimizes damage by proactively executing preventive actions — ensuring cloud infrastructure safety and resilience.
