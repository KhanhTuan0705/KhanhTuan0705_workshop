---
title : "Chuẩn bị VPC và EC2"
date: 2025-07-09
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

Trong bước này, chúng ta sẽ cần tạo một **VPC**. Sau khi tạo VPC, **subnet public** sẽ được tự động tạo. Tiếp theo, chúng ta sẽ tạo **2 EC2 instances** Linux nằm trong **public subnet**:
- **target EC2**: Máy mục tiêu sẽ bị tấn công và kiểm tra bảo mật.
- **attack EC2**: Máy tấn công sẽ giả lập các hành vi xâm nhập vào **target EC2**.

Tổng quan kiến trúc sau khi các bạn hoàn tất bước này sẽ như sau:

![VPC](/images/arc-001.png)

Để tìm hiểu cách tạo các **EC2 instance** và **VPC**, bạn có thể tham khảo các bài lab dưới đây:
- [Giới thiệu về Amazon EC2](https://000004.awsstudygroup.com/vi/)
- [Làm việc với Amazon VPC](https://000003.awsstudygroup.com/vi/)

### Nội dung
  - [Tạo VPC](2.1.1-createvpc/)
  - [Tạo security group](2.1.2-createsecgroup/)
  - [Tạo máy chủ target EC2](2.1.3-createec2target/)
  - [Tạo máy chủ attack EC2](2.1.4-createec2attack/)
