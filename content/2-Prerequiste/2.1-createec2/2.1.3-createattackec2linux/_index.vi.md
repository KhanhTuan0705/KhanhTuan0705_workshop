---
title : " Tạo AttackEC2"
date: 2025-07-06
weight : 3 
chapter : false
pre : " <b> 2.1.3 </b> "
---

### Tạo EC2 `AttackEC2`

Truy cập vào [AWS EC2 Console](https://console.aws.amazon.com/ec2/v2/home) để bắt đầu quá trình tạo EC2 mới.

---

1. Trên giao diện điều khiển EC2, chọn **Instances** và nhấn **Launch instances** ở góc trên bên phải.

![EC2](/images/2.prerequisite/13-createec2.png)

---

2. Trong màn hình **Launch an instance**:
   - Chọn **Name** cho instance là `AttackEC2`.
   - Chọn **Amazon Linux** tại phần **Application and OS Images (Amazon Machine Image)**.

![EC2](/images/2.prerequisite/14-createec2.png)

---

3. Trong **Amazon Machine Image (AMI)**:
   - Click **Select** để chọn hệ điều hành **Amazon Linux 2**.
   - Chọn **Amazon Linux 2 AMI**. (sử dụng Free Tier)

![EC2](/images/2.prerequisite/15-createec2.png)

---

1. Trong **Instance Type**:
   - Chọn **t2.micro** (sử dụng Free Tier).
    - Nhấn **Create new key pair** trong phần **Key pair (login)**.

![EC2](/images/2.prerequisite/16-createec2.png)
---

1. Trong mục **Create Key Pair**:
   - Nhập **Key pair name** là `AttackEC2Key`.
   - Chọn **RSA** cho **Key pair type**.
   - Chọn định dạng **.pem** cho **Private key file format** (để sử dụng với OpenSSH).
   - Nhấn **Create key pair**.

![EC2](/images/2.prerequisite/17-createec2.png)
---

6. Trong phần **Network Settings** chọn **Edit**:

   - Tại **VPC**, chọn **SecurityVPC**.
   - Tại **Subnet**, chọn **SecurityVPC-subnet-public1-ap-southeast-1a**.
   - Đảm bảo **Auto-assign public IP** được chọn là **Enable**.
   - Tại phần **Firewall (security groups)**:
   - Chọn **Create security group**.
   - Nhập tên `AttackSG` cho security group.
   - Mô tả: `Allow SSH for attack simulation`.
   - Cấu hình các inbound rules với **SSH** cho phép truy cập từ **0.0.0.0/0**.

![EC2](/images/2.prerequisite/18-createec2.png)
---
7. Tại **Inbound Security Group Rules**, trong phần **Network Settings** thêm một rule mới:
   - **Type**: Chọn `ssh`.
   - **Protocol**: Chọn `TCP`.
   - **Port Range**: Nhập `22`.
   - **Source**: Chọn `Anywhere` (hoặc nhập `0.0.0.0/0` để cho phép tất cả địa chỉ IP).
   - **Description** (tùy chọn): Có thể nhập mô tả như `SSH for attack simulation`.
   - Sau khi hoàn tất, nhấn **Launch instance** trong phần **Summary** để khởi tạo EC2.

![EC2](/images/2.prerequisite/19-createec2.png)

---
8. Sau khi nhấn **Launch instance** và chờ đợi từ 1 đến 2 phút bạn sẽ thấy trạng thái của EC2 chuyển thành **Running** là máy ảo đã tạo thành công.

![EC2](/images/2.prerequisite/20-createec2.png)


---
