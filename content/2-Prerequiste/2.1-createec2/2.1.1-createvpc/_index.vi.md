---
title : "Tạo VPC"
date: 2025-07-06
weight : 1 
chapter : false
pre : " <b> 2.1.1 </b> "
---

### Tạo VPC `SecurityVPC`

Truy cập vào [AWS VPC Console](https://console.aws.amazon.com/vpc/home) để bắt đầu quá trình tạo VPC mới.

---

1. Trên giao diện điều khiển VPC, chọn **Your VPCs** và nhấn **Create VPC** ở góc trên bên phải.

![VPC](/images/2.prerequisite/01-createvpc.png)

---

2. Trong màn hình **Create VPC**:
   - Chọn **VPC and more** để AWS tự động tạo các tài nguyên kèm theo (subnet, route table, internet gateway,...).
   - Nhập tên là `SecurityVPC`.
   - CIDR IPv4: `10.0.0.0/16`
   - Chọn **No IPv6 CIDR block**

![VPC](/images/2.prerequisite/02-createvpc.png)

---

3. Cấu hình vùng khả dụng và subnet:
   - Availability Zones: chọn `1`
   - Public Subnets: chọn `1`
   - Private Subnets: chọn `0`

![VPC](/images/2.prerequisite/03-createvpc.png)

---

4. Cấu hình tuỳ chọn nâng cao:
   - NAT Gateway: chọn `None`
   - VPC Endpoints: chọn `None`
   - Đảm bảo tick chọn:
     - Enable DNS hostnames
     - Enable DNS resolution
   - Nhấn **Create VPC** để hoàn tất

![VPC](/images/2.prerequisite/04-createvpc.png)
