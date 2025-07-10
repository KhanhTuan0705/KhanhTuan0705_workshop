---
title: "Tạo EventBridge Rule nối GuardDuty đến Lambda"
date: 2025-07-06
weight : 2
chapter : false
pre : " <b> 5.2. </b> "
---

### Tạo EventBridge Rule nối GuardDuty đến Lambda

Truy cập vào [AWS EventBridge Console](https://console.aws.amazon.com/events/) để bắt đầu tạo EventBridge Rule mới.

---

1. Trên giao diện điều khiển EventBridge, chọn **Rules** ở menu bên trái và nhấn **Create rule** ở góc trên bên phải.

![EventBridge](/images/5.Lambda/10-lambda.png)  

---

2. Trong màn hình **Define rule detail**:
   - **Name**: Nhập tên rule là `GuardDutyTriggerLambda`.
   - **Description**: Thêm mô tả cho rule như `Trigger Lambda when GuardDuty detects a security finding`.
   - **Event bus**: Chọn **default**.
   - **Rule type**: Chọn **Rule with an event pattern**.
   - Chọn **Next** để tiếp tục

![EventBridge](/images/5.Lambda/11-lambda.png)  

---

3. Trong phần **Build event pattern **, chọn **Use pattern form** để tạo sự kiện từ mẫu có sẵn.

   - **Event source**: Chọn **AWS services**.
   - **AWS service**: Chọn **GuardDuty**.
   - **Event type**: Chọn **GuardDuty Finding**.
   - Sau khi cấu hình xong, bạn sẽ thấy sự kiện **GuardDuty Finding** sẽ được gửi đến **Lambda function** khi có mối đe dọa.
   - Event Pattern sẽ hiển thị như sau:

```json
{
  "source": ["aws.guardduty"],
  "detail-type": ["GuardDuty Finding"]
}
```

![EventBridge](/images/5.Lambda/12-lambda.png)  

---

4. Tại mục **Select target** :
   - Trong phần **Select a target**, chọn **AWS service**.
   - Trong phần **Target location**, chọn **Target in this account**.
   - Tiếp theo, chọn **Lambda function** trong phần **Function** và nhập tên của hàm Lambda là `HandleGuardDutyFinding`.
   - Trong phần **Configure version/alias**, bạn có thể để mặc định nếu không cần chọn phiên bản hoặc alias.
   - Cấu hình **Permissions**:
   - Chọn **Use execution role (recommended)** để Lambda có quyền truy cập các tài nguyên cần thiết.
   - Chọn **Create a new role for this specific resource** nếu bạn muốn tạo một role mới cho sự kiện này.
   - Đặt tên cho **Execution role** là `Amazon_EventBridge_Invoke_Lambda`.
   - Sau khi cấu hình xong, nhấn **Next** để tiếp tục.

![EventBridge](/images/5.Lambda/13-lambda.png)  

---

5. Ta nhấn **Next** một lần nữa và nhấn **Create rule** d9e73 hoàn tất quá trình tạo.
![EventBridge](/images/5.Lambda/14-lambda.png)  