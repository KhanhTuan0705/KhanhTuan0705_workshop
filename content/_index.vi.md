---
title : "Bảo mật Tự động với AWS GuardDuty và Lambda"
date: 2025-07-09
weight : 1 
chapter : false
---

# Bảo mật Tự động với AWS GuardDuty và Lambda

### Tổng Quan
Trong bài lab này, bạn sẽ học cách thiết lập một hệ thống phát hiện và phản ứng với tấn công tự động sử dụng các dịch vụ AWS như GuardDuty, Lambda, SNS và EC2. Hệ thống sẽ phát hiện hành vi đáng ngờ, dừng các instance EC2 và gửi thông báo qua SNS khi phát hiện một cuộc tấn công.

![ConnectPrivate](/images/arc-log1.png)

### Nội Dung
1. [Giới thiệu](1-introduce/)
2. [Các bước chuẩn bị](2-Prerequiste/)
3. [Phát hiện mối đe dọa với GuardDuty](3-ThreatdetectionwithGuardDuty/)
4. [Gửi thông báo với SNS Topic](4-Sendnotificationswithsns/)
5. [Tự động phản ứng với AWS Lambda](5-Automateresponseswithlambda/)
6. [Demo và Kiểm thử](6-Testinganddemo/)
7. [Dọn dẹp tài nguyên](7-cleanup/)
