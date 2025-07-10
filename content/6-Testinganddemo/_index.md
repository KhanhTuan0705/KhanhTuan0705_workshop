---
title: "Demo and Testing"
date: 2025-07-06
weight: 6
chapter: false
pre: "<b> 6. </b>"
---

### Demo Model Implementing AWS Security Solution with GuardDuty, Lambda, SNS, and EventBridge

In this model, we will implement a security solution using **GuardDuty**, **Lambda**, **SNS**, and **EventBridge**. Two EC2 instances will be created: a **target-ec2** (target machine) to test security and an **attack-ec2** (hacker machine) with a **suspicious IP**. When **GuardDuty** detects a threat from **attack-ec2**, **EventBridge** will trigger **Lambda** to take automated actions. SNS will send a warning notification to the administrator via email, helping monitor and respond quickly to security events.

---

### Connect EC2 Instances

{{% notice info %}}
You can refer to how to connect EC2 using **MobaXterm** instead of using **GIT**. In this case, we will use **MobaXterm** to connect to the EC2 machine.
If you're not sure how, you can refer to the guide at [Connect Linux Instance with MobaXterm](https://000004.awsstudygroup.com/vi/4-launchlinuxinstance/4.2-connectlinuxinstance/).
{{% /notice %}}

1. **Connect to target-ec2**

   ![EC2 Connect](/images/6.Demo/001-demo.png)

---

2. **Connect to attack-ec2**

   ![EC2 Connect](/images/6.Demo/02-demo.png)

---

3. **Install nmap on attack-ec2**

   On the **attack-ec2**, you need to install the **nmap** tool to perform port scanning. To install nmap, use the following command:

   ```bash
   sudo yum install nmap -y
   ```
   ![EC2 Connect](/images/6.Demo/03-demo.png)

---
4. **Scan the target-ec2 ports from attack-ec2**

   After successfully installing nmap, you can scan the ports of the target-ec2 using the following command on the attack-ec2 machine:
```bash
nmap -Pn -p 1-100 54.255.243.8
```
  - You can run this command about 1 to 10 times to scan the ports of the target-ec2.
  - After a successful port scan, the result is

   ![EC2 Connect](/images/6.Demo/04-demo.png)

---
### Results After Port Scan
5. After the port scan is successful, wait for a while for **GuardDuty** to detect it, as shown in the image

   ![EC2 Connect](/images/6.Demo/05-demo.png)
 - This is a warning that EC2 instance i-0d87fe691868ad547 is performing an outbound port scan to a remote server with IP 54.255.243.8 (from attack to target).

---
6. At the same time, you will also receive an email alert because you have set it up in the create **lambda function** section.
  - Notification: **GuardDuty detected suspicious behavior. Stopping EC2: i-0a40480e4ffe67c36**
  
  ![EC2 Connect](/images/6.Demo/06-demo.png)
  
---
7. Finally, the **TargetEC2** instance has been shut down due to the detection of suspicious behavior
   ![EC2 Connect](/images/6.Demo/07-demo.png)

{{% notice note %}}
In this test, we perform a port scan to allow GuardDuty to detect threats and then use Lambda to automatically shut down the EC2 instance. Additionally, you can experiment with other attack methods such as DDoS or other forms of attacks to evaluate GuardDuty's detection capabilities and test how Lambda responds to various threats.
{{% /notice %}}