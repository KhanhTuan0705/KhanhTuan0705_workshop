---
title : "Các bước chuẩn bị"
date: 2025-07-06
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
Bạn cần tạo **2 instance Linux** trên **subnet công cộng** để triển khai bài lab này. Các máy này sẽ lần lượt là **target EC2** và **attack EC2**.
{{% /notice %}}

Để tìm hiểu cách tạo **EC2 instance** và **VPC** với **subnet công cộng**, bạn có thể tham khảo các tài liệu sau:
- [Giới thiệu về Amazon EC2](https://000004.awsstudygroup.com/vi/)
- [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)

Trong bước chuẩn bị này, chúng ta sẽ thực hiện cấu hình giải pháp bảo mật cho **EC2** bằng cách sử dụng **GuardDuty**. Cụ thể, chúng ta sẽ tạo hai máy chủ EC2:
- **target EC2** (máy mục tiêu) sẽ là hệ thống cần được bảo vệ, với **IP bên ngoài** để kiểm tra khả năng bảo mật.
- **attack EC2** (máy tấn công) sẽ giả lập các cuộc tấn công và quét các cổng mở từ **IP bên ngoài** vào **target EC2**.

### Nội dung
  - [Tạo VPC và EC2 Instance](2.1-createec2/)
