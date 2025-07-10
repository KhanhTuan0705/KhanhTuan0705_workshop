---
title : "Phát hiện mối đe dọa với GuardDuty"
date: 2025-07-06
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

{{% notice info %}}
Để phát hiện mối đe dọa và đảm bảo bảo mật cho EC2, chúng ta sẽ kích hoạt **AWS GuardDuty**.
{{% /notice %}}

## Giới thiệu về GuardDuty

**GuardDuty** là dịch vụ bảo mật của AWS giúp phát hiện các mối đe dọa tiềm ẩn và hành vi đáng ngờ trong môi trường AWS. Dịch vụ này giám sát các hoạt động của EC2, S3 và các dịch vụ AWS khác, cung cấp các cảnh báo khi phát hiện mối đe dọa.

---

**Lợi ích**:
- **Phát hiện các mối đe dọa**: GuardDuty giúp phát hiện các cuộc tấn công như SSH brute force, các kết nối trái phép, hoặc các hành vi bất thường.
- **Bảo mật tốt hơn**: GuardDuty sẽ giúp bạn bảo vệ EC2 instances, S3 buckets và các dịch vụ AWS khác bằng cách phát hiện các hành vi đáng ngờ.
  
### Nội dung
  - [Kích hoạt AWS GuardDuty](3.1-enableguardduty/)
