---
title : "Create TargetEC2"
date: 2025-07-06
weight : 2 
chapter : false
pre : " <b> 2.1.2 </b> "
---

### Create EC2 `TargetEC2`

Access the [AWS EC2 Console](https://console.aws.amazon.com/ec2/v2/home) to start the process of creating a new EC2 instance.

---

1. On the EC2 console screen, select **Instances** and click **Launch instances** in the top right corner.

![EC2](/images/2.prerequisite/05-createec2.png)

---

2. In the **Launch an instance** screen:
   - Choose a **Name** for the instance as `TargetEC2`.
   - Select **Amazon Linux** under **Application and OS Images (Amazon Machine Image)**.

![EC2](/images/2.prerequisite/06-createec2.png)

---

3. In the **Amazon Machine Image (AMI)** section:
   - Click **Select** to choose the **Amazon Linux 2** operating system.
   - Choose **Amazon Linux 2 AMI**.

![EC2](/images/2.prerequisite/07-createec2.png)

---

4. In the **Instance Type** section:
   - Select **t2.micro** (for Free Tier usage).
   - Click **Create new key pair** in the **Key pair (login)** section.

![EC2](/images/2.prerequisite/08-createec2.png)
---

5. In the **Create Key Pair** section:
   - Enter **Key pair name** as `TargetEC2Key`.
   - Select **RSA** for **Key pair type**.
   - Choose **.pem** as the **Private key file format** (to use with OpenSSH).
   - Click **Create key pair**.

![EC2](/images/2.prerequisite/09-createec2.png)
---

6. In the **Network Settings** section, click **Edit**:

   - For **VPC**, choose **SecurityVPC**.
   - For **Subnet**, choose **SecurityVPC-subnet-public1-ap-southeast-1a**.
   - Ensure **Auto-assign public IP** is selected as **Enable**.
   - In the **Firewall (security groups)** section:
   - Click **Create security group**.
   - Enter `SecuritySG` as the security group name.
   - Description: `Allow SSH for attack simulation`.
   - Configure inbound rules with **SSH** to allow access from **0.0.0.0/0**.

![EC2](/images/2.prerequisite/10-createec2.png)
---

7. In the **Inbound Security Group Rules**, in the **Network Settings** section, add a new rule:
   - **Type**: Select `ssh`.
   - **Protocol**: Select `TCP`.
   - **Port Range**: Enter `22`.
   - **Source**: Select `Anywhere` (or enter `0.0.0.0/0` to allow all IP addresses).
   - **Description** (optional): You can enter a description like `SSH for attack simulation`.
   - Once completed, click **Launch instance** in the **Summary** section to initiate the EC2 instance.

![EC2](/images/2.prerequisite/11-createec2.png)

---

8. After clicking **Launch instance**, wait for 1 to 2 minutes. The status of the EC2 instance will change to **Running**, indicating the virtual machine has been successfully created.

![EC2](/images/2.prerequisite/12-createec2.png)

---
