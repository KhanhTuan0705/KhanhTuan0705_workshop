---
title: "Activate AWS GuardDuty"
date: 2025-07-06
weight: 3
chapter: false
pre: "<b> 3.1 </b>"
---

{{% notice info %}}
Activate **AWS GuardDuty** to start monitoring and detecting threats in your AWS environment.
{{% /notice %}}

## How to Activate GuardDuty

When you activate **GuardDuty**, the system will begin analyzing activities on **EC2**, **S3**, and other AWS services to detect threats and suspicious behaviors. This is an important step to ensure that your AWS resources are optimally protected.

---

### Steps to Activate AWS GuardDuty:

1. **Log in to the AWS Management Console**:
   - Access the [AWS GuardDuty Console](https://console.aws.amazon.com/guardduty/home) in the AWS Management Console.
   - Select **Amazon GuardDuty - all features** and click "Get started" to proceed to the next step.

![GD](/images/3.GD/01-gd.png)

2. **Click the "Enable GuardDuty" button to activate the service**:
   {{% notice note %}}
   New accounts get a free 30-day trial from AWS.
   {{% /notice %}}
   - If it's your first time using it, you'll see an **Enable GuardDuty** button.
   - Click this button to start the activation process.

![GD](/images/3.GD/02-gd.png)

1. **Confirm the configuration and start scanning**:
   - GuardDuty will automatically start scanning your resources and monitoring activities on EC2, S3, and other AWS services.
   - Once activated, GuardDuty will begin detecting potential threats and send alerts if any suspicious behavior is found.
  
![GD](/images/3.GD/03-gd.png)

2. **Check the findings**:
   - After GuardDuty is active, you can go to the **Findings** section to view alerts and detected threats.
   - Here, you'll see details about any threats that have been identified.
  
![GD](/images/3.GD/04-gd.png)
---

### References:
- [AWS GuardDuty Official Documentation](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)
- [How to use AWS GuardDuty](https://aws.amazon.com/guardduty/)

---
