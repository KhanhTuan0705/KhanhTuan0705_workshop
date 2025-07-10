---
title: "Dọn dẹp tài nguyên"
date: 2025-07-09
weight: 7
chapter: false
pre: "<b> 7. </b>"
---

### Dọn dẹp tài nguyên AWS

Sau khi hoàn thành quá trình triển khai và kiểm thử, chúng ta cần tiến hành dọn dẹp tài nguyên để tránh phát sinh chi phí không cần thiết. Dưới đây là các bước để dọn dẹp các tài nguyên AWS đã sử dụng:

---

1. **Xóa EC2 Instances**
   - Truy cập vào [AWS EC2 Console](https://console.aws.amazon.com/ec2/) để xóa các instance không còn sử dụng.
   - Chọn vào **Instances** trong AWS EC2 Console.
   - Chọn cả 2 instance **hacker-ec2** và **user-ec2**.
   - Chọn **Instance state**, sau đó chọn **Terminate instance**.
   - Chọn **Terminate** để xác nhận việc xóa.

   ![Delete EC2 Instance](/images/7.clean/01-clean.png)

---

2. **Xóa SNS Topic**
   - Truy cập vào [AWS SNS Console](https://console.aws.amazon.com/sns/v3/home) để xóa topic `GuardDutyAlertTopic`.
   - Chọn **Topics**, tìm topic `GuardDutyAlertTopic`, nhấn **Delete**.
   - Xác nhận lại nhập **delete me** nhấn **delete**.

   ![Delete SNS Topic](/images/7.clean/02-clean.png)

---

3. **Xóa Lambda Function**
   - Truy cập vào [AWS Lambda Console](https://console.aws.amazon.com/lambda/) để xóa hàm Lambda `HandleGuardDutyFinding`.
   - Chọn **Functions**, tìm hàm `HandleGuardDutyFinding`, nhấn **Delete**.
   - Xác nhận lại nhập **confirm** nhấn **delete**.

   ![Delete Lambda Function](/images/7.clean/03-clean.png)

---

4. **Xóa EventBridge Rule**
   - Truy cập vào [AWS EventBridge Console](https://console.aws.amazon.com/events/) để xóa rule `GuardDutyTriggerLambda`.
   - Chọn **Rules**, tìm rule `GuardDutyTriggerLambda`, nhấn **Delete**.
   - Xác nhận lại nhập **delete** nhấn **delete**.

   ![Delete EventBridge Rule](/images/7.clean/04-clean.png)

---

5. **Xóa IAM Role**
   - Truy cập vào [IAM Console](https://console.aws.amazon.com/iam/) để xóa role `HandleGuardDutyFinding-role`.
   - Chọn **Roles**, tìm role `HandleGuardDutyFinding-role`, nhấn **Delete**.
   - Xác nhận lại nhập **name role** nhấn **delete**.

   ![Delete IAM Role](/images/7.clean/05-clean.png)

---

6. **Xóa VPC**
   - Truy cập vào [AWS VPC Console](https://console.aws.amazon.com/vpc/) để xóa **SecurityVPC**.
   - Chọn **Your VPCs**, tìm VPC `SecurityVPC`, sau đó chọn **Actions**.
   - Chọn **Delete VPC** và xác nhận.

   ![Delete VPC](/images/7.clean/06-clean.png)

---

7. **Xóa GuardDuty**
   - Truy cập vào [AWS GuardDuty Console](https://console.aws.amazon.com/guardduty/) để xóa dịch vụ GuardDuty.
   - Chọn **Settings** trong GuardDuty Console.
   - Click **Disable**, sau đó click **Disable** để xác nhận.
  


   ![Delete GuardDuty](/images/7.clean/01-clean.png)

---

### Lưu ý
Sau khi xóa các tài nguyên, bạn cũng có thể kiểm tra lại tài khoản AWS để chắc chắn rằng không có tài nguyên nào đang được giữ lại và phát sinh chi phí.


{{% notice note %}}
Việc dọn dẹp tài nguyên sau khi hoàn thành kiểm thử là rất quan trọng để tránh chi phí không cần thiết. Đảm bảo rằng tất cả các dịch vụ đã được xóa và không còn tài nguyên nào bị bỏ quên.
{{% /notice %}}
