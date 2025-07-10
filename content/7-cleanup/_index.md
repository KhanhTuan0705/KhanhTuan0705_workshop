---
title: "Cleanup Resources"
date: 2025-07-09
weight: 7
chapter: false
pre: "<b> 7. </b>"
---

### Cleanup AWS Resources

After completing the deployment and testing process, we need to clean up the resources to avoid unnecessary costs. Below are the steps to clean up the AWS resources we have used:

---

1. **Delete EC2 Instances**
   - Access the [AWS EC2 Console](https://console.aws.amazon.com/ec2/) to delete unused instances.
   - Select **Instances** in the AWS EC2 Console.
   - Select both **hacker-ec2** and **user-ec2** instances.
   - Select **Instance state**, then choose **Terminate instance**.
   - Click **Terminate** to confirm the deletion.

   ![Delete EC2 Instance](/images/7.clean/01-clean.png)

---

2. **Delete SNS Topic**
   - Access the [AWS SNS Console](https://console.aws.amazon.com/sns/v3/home) to delete the `GuardDutyAlertTopic` topic.
   - Select **Topics**, find the `GuardDutyAlertTopic`, and click **Delete**.
   - Confirm by entering **delete me** and click **delete**.

   ![Delete SNS Topic](/images/7.clean/02-clean.png)

---

3. **Delete Lambda Function**
   - Access the [AWS Lambda Console](https://console.aws.amazon.com/lambda/) to delete the `HandleGuardDutyFinding` Lambda function.
   - Select **Functions**, find the `HandleGuardDutyFinding` function, and click **Delete**.
   - Confirm by entering **confirm** and click **delete**.

   ![Delete Lambda Function](/images/7.clean/03-clean.png)

---

4. **Delete EventBridge Rule**
   - Access the [AWS EventBridge Console](https://console.aws.amazon.com/events/) to delete the `GuardDutyTriggerLambda` rule.
   - Select **Rules**, find the `GuardDutyTriggerLambda` rule, and click **Delete**.
   - Confirm by entering **delete** and click **delete**.

   ![Delete EventBridge Rule](/images/7.clean/04-clean.png)

---

5. **Delete IAM Role**
   - Access the [IAM Console](https://console.aws.amazon.com/iam/) to delete the `HandleGuardDutyFinding-role`.
   - Select **Roles**, find the `HandleGuardDutyFinding-role`, and click **Delete**.
   - Confirm by entering **name role** and click **delete**.

   ![Delete IAM Role](/images/7.clean/05-clean.png)

---

6. **Delete VPC**
   - Access the [AWS VPC Console](https://console.aws.amazon.com/vpc/) to delete **SecurityVPC**.
   - Select **Your VPCs**, find the `SecurityVPC`, then select **Actions**.
   - Choose **Delete VPC** and confirm.

   ![Delete VPC](/images/7.clean/06-clean.png)

---

7. **Delete GuardDuty**
   - Access the [AWS GuardDuty Console](https://console.aws.amazon.com/guardduty/) to delete the GuardDuty service.
   - Select **Settings** in the GuardDuty Console.
   - Click **Disable**, then click **Disable** to confirm.

   ![Delete GuardDuty](/images/7.clean/01-clean.png)

---

### Notes
After deleting the resources, you can also check your AWS account to ensure that no resources are left behind and no unwanted costs are incurred.

{{% notice note %}}
Cleaning up resources after completing testing is very important to avoid unnecessary costs. Make sure all services have been deleted and no resources are left behind.
{{% /notice %}}
