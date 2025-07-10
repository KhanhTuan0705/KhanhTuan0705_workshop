---
title: "Create Lambda Function"
date: 2025-07-06
weight: 1
chapter: false
pre: "<b> 5.1. </b>"
---

### Create Lambda Function `HandleGuardDutyFinding`

Navigate to the [AWS Lambda Console](https://console.aws.amazon.com/lambda/) to begin creating a new Lambda function.

---

1. In the Lambda console, select **Create function**.

![Lambda](/images/5.Lambda/01-lambda.png)

---

2. In the **Create function** screen:
   - Select **Author from scratch**.
   - **Function name**: Enter the Lambda function name as `HandleGuardDutyFinding`.
   - **Runtime**: Select **Python 3.12** (or the latest version).
   - Click **Create function** to create the function.

![Lambda](/images/5.Lambda/02-lambda.png)

---

3. Add the source code for the Lambda function after the function is created:
   - Scroll down to the **Code source** section.

![Lambda](/images/5.Lambda/03-lambda.png)

   - Paste the following code into the `lambda_function.py` file.
```python
import json
import boto3

# Initialize AWS clients
ec2 = boto3.client('ec2')
sns = boto3.client('sns')

# Define your target EC2 instance ID and SNS topic ARN
import boto3
import json

# Tạo client EC2 và SNS từ AWS SDK
ec2 = boto3.client('ec2')
sns = boto3.client('sns')

# ID của instance EC2 và ARN của SNS Topic
INSTANCE_ID = ''  
SNS_TOPIC_ARN = ''

def lambda_handler(event, context):
    # In thông tin sự kiện GuardDuty nhận được
    print("GuardDuty Event:")
    print(json.dumps(event, indent=2))
    
    # Gửi thông báo qua SNS
    sns.publish(
        TopicArn=SNS_TOPIC_ARN,
        Subject='GuardDuty Alert',
        Message=f'GuardDuty detected suspicious behavior. Stopping EC2: {INSTANCE_ID}'
    )
    
    # Dừng instance EC2 có ID đã chỉ định
    ec2.stop_instances(InstanceIds=[INSTANCE_ID])

    # Trả về kết quả sau khi thực hiện các hành động
    return {
        'statusCode': 200,
        'body': json.dumps('EC2 has been stopped and an email alert has been sent.')
    }
```
   - Enter the EC2 instance ID and the SNS Topic ARN.
   - Click **Deploy**.

![Lambda](/images/5.Lambda/04-lambda.png)

---

4. Add permissions for Lambda:
   - Click on **Configuration**.
   - Select **Permissions**.
   - Click the blue text under Role name to assign permissions to Lambda.

![Lambda](/images/5.Lambda/05-lambda.png)

   - Click **Add Permissions**.
   - Select **Attach policies**.

![Lambda](/images/5.Lambda/06-lambda.png)

   - Click on **Configuration**.
   - Select **Permissions**.
   - Click the blue text under Role name to assign permissions to Lambda.

---

5. In **Other permissions policies**:
   - Search for **ec2** and check **AmazonEC2FullAccess**.
   - Search for **sns** and check **AmazonSNSFullAccess**.
   - After selecting both permissions, click **Add permissions**.

![Lambda](/images/5.Lambda/07-lambda.png)
![Lambda](/images/5.Lambda/08-lambda.png)

   - After adding, you will see the two permissions as shown in the image.

![Lambda](/images/5.Lambda/09-lambda.png)
