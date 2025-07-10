---
title : "Create SNS Topic"
date: 2025-07-06
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

### Create SNS Topic `GuardDutyAlertTopic`

Access the [AWS SNS Console](https://console.aws.amazon.com/sns/v3/home) to start the process of creating a new SNS Topic.

---

1. On the SNS console, select **Topics** and click **Create topic** in the top-right corner.

![SNS](/images/4.SNS/01-sns.png)

---

2. In the **Create topic** screen:
   - Choose **Standard** for the topic type.
   - Enter the topic name as `GuardDutyAlertTopic`.
   - Choose a **Display name** for SNS messages, for example: `GuardDuty Alerts`.

![SNS](/images/4.SNS/02-sns.png)

---

3. Configure the access permissions and notifications:
   - Enter a description for the topic (optional).
   - Configure the access permissions (you can leave the defaults if not needed).
   - Click **Create topic** to finish.

![SNS](/images/4.SNS/03-sns.png)
