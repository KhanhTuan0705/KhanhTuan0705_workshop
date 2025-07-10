---
title : "Gửi thông báo với SNS Topic"
date: 2025-07-06
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

{{% notice info %}}
Amazon Simple Notification Service (SNS) là một dịch vụ tin nhắn đám mây mạnh mẽ của AWS, giúp gửi thông báo đến các hệ thống hoặc người dùng thông qua các kênh khác nhau như email, SMS, HTTP/HTTPS endpoints hoặc các dịch vụ khác. SNS hỗ trợ việc gửi thông báo theo thời gian thực, có khả năng mở rộng cao và dễ tích hợp với các dịch vụ AWS khác như Lambda và GuardDuty.
{{% /notice %}}

## Giới thiệu về SNS

**SNS** là dịch vụ của AWS giúp bạn gửi thông báo đến các hệ thống hoặc người dùng thông qua email, SMS, HTTP/HTTPS endpoints hoặc các dịch vụ AWS khác. SNS giúp tăng cường khả năng phản ứng nhanh chóng đối với các sự kiện quan trọng hoặc mối đe dọa tiềm ẩn, đảm bảo hệ thống luôn được theo dõi và bảo vệ.

---

**Lợi ích**:
- **Gửi thông báo nhanh chóng**: SNS cho phép gửi thông báo đến một số lượng lớn người nhận trong thời gian ngắn.
- **Tích hợp dễ dàng**: SNS có thể dễ dàng tích hợp với các dịch vụ AWS như Lambda, CloudWatch, và GuardDuty để tự động gửi thông báo khi có sự kiện xảy ra.
  
### Nội dung
  - [Tạo SNS Topic](4.1-createsnstopic/)
  - [Tạo SNS Subscription](4.2-createsnssubscription/)
