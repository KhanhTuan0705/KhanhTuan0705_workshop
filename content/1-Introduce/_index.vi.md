---
title: "Giới thiệu"
date: 2024-06-16
weight: 1
chapter: false
pre: " <b>1.</b> "
---


### Mục tiêu  
Trong thời đại hiện nay, các mối đe dọa bảo mật đối với cơ sở hạ tầng đám mây đang ngày càng trở nên phổ biến và tinh vi. Dự án này được thiết kế nhằm xây dựng một hệ thống **phát hiện và phản ứng tự động** với các hành vi đáng ngờ trên EC2, giúp giảm thiểu rủi ro và tăng cường bảo mật cho hệ thống.

### Tổng quan về hệ thống  
Hệ thống sử dụng sự kết hợp của các dịch vụ AWS để đảm bảo quá trình giám sát và phản ứng được thực hiện tự động và hiệu quả:

- **Amazon GuardDuty**: Phát hiện các hành vi bất thường trên EC2 như port scan, truy cập trái phép, v.v.
- **Amazon EventBridge**: Nhận sự kiện từ GuardDuty và kích hoạt xử lý tự động.
- **AWS Lambda**: Xử lý các cảnh báo từ GuardDuty, thực hiện hành động như dừng EC2 hoặc gửi thông báo.
- **Amazon SNS**: Gửi cảnh báo đến quản trị viên qua email hoặc tin nhắn.

Các dịch vụ này hoạt động phối hợp để tạo ra một hệ thống giám sát – phản ứng – cảnh báo khép kín và linh hoạt.

### Các trường hợp sử dụng  

- **Phát hiện và phản ứng với tấn công dò quét cổng (Port Scan).**
- **Dừng EC2 instance** khi phát hiện hành vi nghi ngờ.
- **Gửi thông báo tức thì** đến quản trị viên khi có sự kiện bảo mật.
- **Tự động hóa toàn bộ quy trình phản ứng sự cố.**

> Hệ thống không chỉ giúp phát hiện kịp thời các mối đe dọa mà còn giảm thiểu thiệt hại bằng cách chủ động thực thi các biện pháp phòng ngừa – đảm bảo an toàn cho hạ tầng đám mây.

