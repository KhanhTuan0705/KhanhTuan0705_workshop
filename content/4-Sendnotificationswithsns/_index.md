---
title : "Send Notifications with SNS Topic"
date: 2025-07-06
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

{{% notice info %}}
Amazon Simple Notification Service (SNS) is a powerful cloud messaging service from AWS that helps send notifications to systems or users through various channels such as email, SMS, HTTP/HTTPS endpoints, or other services. SNS supports real-time notifications, is highly scalable, and is easy to integrate with other AWS services like Lambda and GuardDuty.
{{% /notice %}}

## Introduction to SNS

**SNS** is an AWS service that helps you send notifications to systems or users via email, SMS, HTTP/HTTPS endpoints, or other AWS services. SNS enhances the ability to respond quickly to important events or potential threats, ensuring systems are continuously monitored and protected.

---

**Benefits**:
- **Fast Notification Delivery**: SNS allows you to send notifications to a large number of recipients in a short amount of time.
- **Easy Integration**: SNS can be easily integrated with AWS services like Lambda, CloudWatch, and GuardDuty to automatically send notifications when events occur.
  
### Content
  - [Create SNS Topic](4.1-createsnstopic/)
  - [Create SNS Subscription](4.2-createsnssubscription/)
