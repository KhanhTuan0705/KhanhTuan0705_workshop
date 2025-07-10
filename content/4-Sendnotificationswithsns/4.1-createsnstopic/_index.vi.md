---
title : "Tạo SNS Topic"
date: 2025-07-06
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

### Tạo SNS Topic `GuardDutyAlertTopic`

Truy cập vào [AWS SNS Console](https://console.aws.amazon.com/sns/v3/home) để bắt đầu quá trình tạo SNS Topic mới.

---

1. Trên giao diện điều khiển SNS, chọn **Topics** và nhấn **Create topic** ở góc trên bên phải.

![SNS](/images/4.SNS/01-sns.png)

---

1. Trong màn hình **Create topic**:
   - Chọn **Standard** cho loại topic.
   - Nhập tên topic là `GuardDutyAlertTopic`.
   - Chọn **Display name** (Tên hiển thị) cho SNS message, ví dụ: `GuardDuty Alerts`.

![SNS](/images/4.SNS/02-sns.png)

---

3. Cấu hình các quyền truy cập và thông báo:
   - Nhập mô tả cho topic (tuỳ chọn).
   - Cấu hình các quyền truy cập (mặc định có thể bỏ qua nếu không cần).
   - Nhấn **Create topic** để hoàn tất.

![SNS](/images/4.SNS/03-sns.png)

---

