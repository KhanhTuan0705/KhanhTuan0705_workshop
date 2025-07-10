---
title : "Tạo SNS Subscription"
date: 2025-07-06
weight : 2
chapter : false
pre : " <b> 4.2. </b> "
---

### Tạo SNS Subscription

1. Truy cập vào [Amazon SNS Console](https://console.aws.amazon.com/sns/v3/home) và chọn **Subscriptions** từ menu bên trái.
   -  Chọn **Create subscription**.
![SNS](/images/4.SNS/04-sns.png)


---

2. Trong màn hình **Create subscription**:
   - Chọn **Topic ARN** từ menu xổ xuống, tìm và chọn SNS Topic mà bạn đã tạo ở bước trước (ví dụ: `GuardDutyAlertTopic`).
   - Chọn **Protocol** (ví dụ: `Email` nếu bạn muốn nhận thông báo qua email).
   - Nhập **Endpoint** là địa chỉ mà bạn muốn nhận thông báo (ví dụ: địa chỉ email của bạn).
   - Nhấn **Create subscription** để tạo subscription.

![SNS](/images/4.SNS/05-sns.png)

---

3. Sau khi tạo subscription xong, bạn sẽ nhận được một email xác nhận. Trong email, bạn sẽ thấy thông báo:
    - Nhấn **Confirm subscription** để được xác nhận
![SNS](/images/4.SNS/06-sns.png)
    - Khi nhấn vào nó hiện ra bảng dưới đây là đã hoàn tất xác nhận
![SNS](/images/4.SNS/07-sns.png)     
    - Bạn cần nhấn vào liên kết **"click here to unsubscribe"** nếu không muốn nhận thông báo nữa.

---

4. Sau khi xác nhận, bạn đã hoàn tất việc tạo **SNS Subscription** và có thể nhận thông báo từ SNS khi có sự kiện mới từ GuardDuty.



