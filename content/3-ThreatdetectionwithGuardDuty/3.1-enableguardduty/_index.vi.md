---
title: "Kích hoạt AWS GuardDuty"
date: 2025-07-06
weight: 3
chapter: false
pre: "<b> 3.1 </b>"
---

{{% notice info %}}
Kích hoạt **AWS GuardDuty** để bắt đầu giám sát và phát hiện các mối đe dọa trong môi trường AWS của bạn.
{{% /notice %}}

## Cách kích hoạt GuardDuty

Khi bạn kích hoạt **GuardDuty**, hệ thống sẽ bắt đầu phân tích các hoạt động trên **EC2**, **S3**, và các dịch vụ AWS khác để phát hiện mối đe dọa và hành vi đáng ngờ. Đây là một bước quan trọng để đảm bảo rằng các tài nguyên AWS của bạn được bảo vệ tối ưu.

---

### Các bước kích hoạt AWS GuardDuty:

1. **Đăng nhập vào AWS Management Console**:
   - Truy cập vào [AWS GuardDuty Console](https://console.aws.amazon.com/guardduty/home) trong AWS Management Console.
   - Chọn **Amazon GuardDuty - all features**  sau đó nhấn vào  "Get started" tiến hành sang bước tiếp theo.
   
![GD](/images/3.GD/01-gd.png)

2. **Nhấn vào nút "Enable GuardDuty" để kích hoạt dịch vụ**:
   {{% notice note %}}
   Account mới thì AWS sẽ cho dùng thử miễn phí 30 ngày nha.
   {{% /notice %}}
   - Nếu là lần đầu sử dụng, bạn sẽ thấy một nút **Enable GuardDuty**.
   - Nhấn vào nút này để bắt đầu quá trình kích hoạt.
  
![GD](/images/3.GD/02-gd.png)

3. **Xác nhận cấu hình và bắt đầu quét**:
   - GuardDuty sẽ tự động bắt đầu quét các tài nguyên của bạn và bắt đầu giám sát các hành động trên EC2, S3, và các dịch vụ AWS khác.
   - Sau khi kích hoạt, GuardDuty sẽ bắt đầu phát hiện các mối đe dọa tiềm ẩn và gửi cảnh báo nếu có bất kỳ hành vi đáng ngờ nào.
  
![GD](/images/3.GD/03-gd.png)

1. **Kiểm tra các findings**:
   - Sau khi GuardDuty hoạt động, bạn có thể truy cập mục **Findings** để xem các cảnh báo và phát hiện mối đe dọa.
   - Tại đây, bạn sẽ thấy các chi tiết về các mối đe dọa đã được phát hiện.
  
![GD](/images/3.GD/04-gd.png)

---

### Tài liệu tham khảo:
- [AWS GuardDuty Official Documentation](https://docs.aws.amazon.com/guardduty/latest/ug/what-is-guardduty.html)
- [How to use AWS GuardDuty](https://aws.amazon.com/guardduty/)

---

