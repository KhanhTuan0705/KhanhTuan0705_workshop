---
title: "Demo và Kiểm thử"
date: 2025-07-06
weight: 6
chapter: false
pre: "<b> 6. </b>"
---

### Mô hình Demo Triển khai Giải pháp Bảo mật AWS sử dụng GuardDuty, Lambda, SNS và EventBridge

Trong mô hình này, chúng ta sẽ triển khai giải pháp bảo mật sử dụng **GuardDuty**, **Lambda**, **SNS**, và **EventBridge**. Hai máy chủ EC2 sẽ được tạo: một máy **target-ec2** (máy mục tiêu) để kiểm tra khả năng bảo mật và một máy **attack-ec2** (máy hacker) với **IP đáng ngờ**. Khi **GuardDuty** phát hiện mối đe dọa từ **attack-ec2**, **EventBridge** sẽ kích hoạt **Lambda** để thực hiện hành động tự động. SNS sẽ gửi thông báo cảnh báo đến người quản trị qua email, giúp theo dõi và phản ứng nhanh chóng với sự kiện bảo mật.

---

### Kết nối máy EC2

{{% notice info %}}
Bạn có thể tham khảo cách kết nối EC2 bằng **MobaXterm** thay vì sử dụng **GIT**. Trong trường hợp này, chúng ta sẽ dùng **MobaXterm** để kết nối với máy EC2. 
Nếu bạn chưa biết cách, bạn có thể tham khảo hướng dẫn tại [Kết nối Linux instance với MobaXterm](https://000004.awsstudygroup.com/vi/4-launchlinuxinstance/4.2-connectlinuxinstance/).
{{% /notice %}}

1. **Kết nối máy **target-ec2**

   ![EC2 Connect](/images/6.Demo/001-demo.png)

---

2. **Kết nối máy **attack-ec2**

   ![EC2 Connect](/images/6.Demo/02-demo.png)

---
3. **Cài đặt nmap cho máy **attack-ec2**

   Trên máy **attack-ec2**, bạn cần cài đặt công cụ **nmap** để thực hiện quét cổng. Để cài đặt nmap, sử dụng lệnh sau:

   ```bash
   sudo yum install nmap -y
   ```
   ![EC2 Connect](/images/6.Demo/03-demo.png)

---
4. **Quét cổng của máy target-ec2 từ máy attack-ec2**

   Sau khi cài đặt thành công nmap, bạn có thể quét cổng của máy target-ec2 bằng cách sử dụng lệnh sau trên máy attack-ec2:
```bash
nmap -Pn -p 1-100 54.255.243.8
```
  - Ta nhập khoảng 1 đến 10 lần lệnh này quét các cổng của máy target-ec2
  - Kết quả sau khi portscan thành công :

   ![EC2 Connect](/images/6.Demo/04-demo.png)

---
### Kết quả sau khi port scan
5. Sau khi portscan thành công thì chờ một khoảng thời gian để
**GuarduDuty** sẽ phát hiện ra như hình
   ![EC2 Connect](/images/6.Demo/05-demo.png)
 - Đây là cảnh báo EC2 instance i-0d87fe691868ad547 đang thực hiện hành vi port scan outbound đến máy chủ từ xa có IP 54.255.243.8 (từ máy attack đến máy target)

---
6. Đồng thời bạn cũng sẽ nhận được một mail cảnh báo do bạn đã thiết lập ở phần **tạo hàm lambda**
  - Thông báo : **GuardDuty phát hiện hành vi đáng ngờ. Đang dừng EC2: i-0a40480e4ffe67c36**
  
  ![EC2 Connect](/images/6.Demo/06-demo.png)
  
---
7. Cuối cùng là máy EC2 **TargetEC2** đã tắt vì phát hiện hành vi đáng ngờ
   ![EC2 Connect](/images/6.Demo/07-demo.png)

{{% notice note %}}
Trong bài kiểm thử này, chúng ta sẽ thực hiện quét cổng (port scan) nhằm để GuardDuty phát hiện mối đe dọa, sau đó sử dụng Lambda để tự động tắt máy EC2. Ngoài ra, bạn cũng có thể thử nghiệm với các phương án khác như tấn công DDoS hay các hình thức tấn công khác để đánh giá khả năng phát hiện của GuardDuty, đồng thời kiểm tra cách Lambda phản ứng với nhiều loại mối nguy khác nhau.
{{% /notice %}}