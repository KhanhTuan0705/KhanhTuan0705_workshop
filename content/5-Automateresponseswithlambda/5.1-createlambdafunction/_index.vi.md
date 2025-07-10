---
title: "Tạo hàm Lambda"
date: 2025-07-06
weight: 1
chapter: false
pre: "<b> 5.1. </b>"
---

### Tạo hàm Lambda `HandleGuardDutyFinding`

Truy cập vào [AWS Lambda Console](https://console.aws.amazon.com/lambda/) để bắt đầu quá trình tạo hàm Lambda mới.

---

1. Trên giao diện điều khiển Lambda, chọn **Create function**.

![Lambda](/images/5.Lambda/01-lambda.png)

---

2. Trong màn hình **Create function**:
   - Chọn **Author from scratch**.
   - **Function name**: Nhập tên hàm Lambda là `HandleGuardDutyFinding`.
   - **Runtime**: Chọn **Python 3.12** (hoặc phiên bản mới nhất).
   - Nhấn **Create function**: để tạo hàm.

![Lambda](/images/5.Lambda/02-lambda.png)

---

3. Thêm mã nguồn cho hàm Lambda, sau khi tạo xong **lambda function**:
   - Kéo xuống phần **Code source**.

![Lambda](/images/5.Lambda/03-lambda.png)

   - Dán đoạn code này vào file lambda_function.py

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
   - Điền id của instance EC2 và ARN của SNS Topic .
   - Nhấn **Deploy**.

![Lambda](/images/5.Lambda/04-lambda.png) 

 ---

4. Thêm quyền cho Lambda 
   - Nhấn chọn **Configuration** .
   - Chọn **Permissions**.
   - Chọn dòng chữ màu xanh phía dưới Role name để cấp quyền cho Lambda.

![Lambda](/images/5.Lambda/05-lambda.png)   
  
   - Nhấn chọn **Add Permissions** .
   - Chọn **Attach policies**.

![Lambda](/images/5.Lambda/06-lambda.png)   
  
   - Nhấn chọn **Configuration** .
   - Chọn **Permissions**.
   - Chọn dòng chữ màu xanh phía dưới Role name để cấp quyền cho Lambda.
   - 
---

5. Trong **Other permissions policies** :
   - Tại seach **ec2** tích vào **AmazonEC2FullAccess**
   - Tại seach **sn** tích vào **AmazonSNSFullAccess**
   - Sau khi tích chọn hai quyền thì ta nhấn chọn **Add permissions**

![Lambda](/images/5.Lambda/07-lambda.png)  
![Lambda](/images/5.Lambda/08-lambda.png)  

   - Sau khi thêm ta được hai quyền như hình

![Lambda](/images/5.Lambda/09-lambda.png)