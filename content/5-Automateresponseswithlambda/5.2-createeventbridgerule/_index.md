---
title: "Create EventBridge Rule to Link GuardDuty to Lambda"
date: 2025-07-06
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

### Create EventBridge Rule to Link GuardDuty to Lambda

Navigate to the [AWS EventBridge Console](https://console.aws.amazon.com/events/) to begin creating a new EventBridge Rule.

---

1. In the EventBridge console, select **Rules** from the left-hand menu and click **Create rule** at the top-right corner.

![EventBridge](/images/5.Lambda/10-lambda.png)  

---

2. In the **Define rule detail** screen:
   - **Name**: Enter the rule name as `GuardDutyTriggerLambda`.
   - **Description**: Add a description for the rule such as `Trigger Lambda when GuardDuty detects a security finding`.
   - **Event bus**: Select **default**.
   - **Rule type**: Select **Rule with an event pattern**.
   - Click **Next** to continue.

![EventBridge](/images/5.Lambda/11-lambda.png)  

---

3. In the **Build event pattern** section, select **Use pattern form** to create the event from the available pattern.

   - **Event source**: Select **AWS services**.
   - **AWS service**: Select **GuardDuty**.
   - **Event type**: Select **GuardDuty Finding**.
   - After configuring, you will see the **GuardDuty Finding** event will be sent to the **Lambda function** when a threat is detected.
   - The Event Pattern will appear as follows:

![EventBridge](/images/5.Lambda/12-lambda.png)  

```json
{
  "source": ["aws.guardduty"],
  "detail-type": ["GuardDuty Finding"]
}

```
---

4. In the **Select target** section:
   - Under **Select a target**, select **AWS service**.
   - Under **Target location**, select **Target in this account**.
   - Then, select **Lambda function** in the **Function** section and enter the Lambda function name as `HandleGuardDutyFinding`.
   - In the **Configure version/alias** section, you can leave it as default if you don’t need to select a version or alias.
   - Configure **Permissions**:
     - Select **Use execution role (recommended)** to allow Lambda to access the required resources.
     - Select **Create a new role for this specific resource** if you want to create a new role for this event.
     - Name the **Execution role** as `Amazon_EventBridge_Invoke_Lambda`.
   - After completing the configuration, click **Next** to continue.

![EventBridge](/images/5.Lambda/13-lambda.png)  

---

5. Click **Next** once more and click **Create rule** to complete the creation process.

![EventBridge](/images/5.Lambda/14-lambda.png)  
