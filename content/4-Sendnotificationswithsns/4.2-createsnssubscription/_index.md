---
title : "Create SNS Subscription"
date: 2025-07-06
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---

### Create SNS Subscription

1. Access the [Amazon SNS Console](https://console.aws.amazon.com/sns/v3/home) and select **Subscriptions** from the left menu.
   -  Click **Create subscription**.
![SNS](/images/4.SNS/04-sns.png)


---

2. In the **Create subscription** screen:
   - Choose **Topic ARN** from the dropdown menu, search for and select the SNS Topic you created in the previous step (e.g., `GuardDutyAlertTopic`).
   - Choose **Protocol** (e.g., `Email` if you want to receive notifications via email).
   - Enter the **Endpoint**, which is the address where you want to receive notifications (e.g., your email address).
   - Click **Create subscription** to create the subscription.

![SNS](/images/4.SNS/05-sns.png)

---

3. After creating the subscription, you will receive a confirmation email. In the email, you will see a message:
    - Click **Confirm subscription** to confirm your subscription.
![SNS](/images/4.SNS/06-sns.png)
    - When you click it, the following screen will appear, indicating that the subscription is confirmed.
![SNS](/images/4.SNS/07-sns.png)     
    - If you no longer wish to receive notifications, click the **"click here to unsubscribe"** link.

---

4. After confirming, you have successfully created the **SNS Subscription** and can now receive notifications from SNS when new events occur from GuardDuty.
