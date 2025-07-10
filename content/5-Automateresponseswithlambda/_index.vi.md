--- 
title : "Tự động phản ứng với AWS Lambda"
date: 2025-07-06
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

{{% notice info %}}
AWS Lambda giúp bạn tự động hóa các phản ứng khi có sự kiện xảy ra trong AWS. Bạn có thể sử dụng Lambda để kích hoạt các hành động tự động khi GuardDuty phát hiện các mối đe dọa.
{{% /notice %}}

## Giới thiệu về AWS Lambda

**AWS Lambda** là một dịch vụ điện toán serverless của AWS cho phép bạn chạy mã mà không cần phải quản lý máy chủ. Lambda giúp bạn xử lý các sự kiện theo thời gian thực và thực hiện các hành động tự động khi có sự kiện từ các dịch vụ AWS khác như GuardDuty, S3, và SNS.

---

**Lợi ích**:
- **Không cần quản lý máy chủ**: Lambda chạy mã tự động khi có sự kiện mà không cần bạn phải quản lý server.
- **Khả năng mở rộng tự động**: Lambda tự động mở rộng để xử lý các yêu cầu, giúp tiết kiệm tài nguyên và chi phí.
- **Tích hợp với các dịch vụ AWS**: Lambda có thể dễ dàng tích hợp với các dịch vụ AWS như GuardDuty để thực hiện hành động khi có mối đe dọa được phát hiện.

### Nội dung
  - [Tạo hàm Lambda](5.1-createlambdafunction/)
  - [Tạo EventBridge Rule kết nối GuardDuty với Lambda](5.2-createeventbridgerule/)  
