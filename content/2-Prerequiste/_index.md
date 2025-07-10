---
title : "Preparation Steps"
date: 2025-07-06
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---

{{% notice info %}}
You need to create **2 Linux instances** in the **public subnet** to complete this lab. These machines will be **target EC2** and **attack EC2**.
{{% /notice %}}

To learn how to create **EC2 instances** and a **VPC** with **public subnets**, you can refer to the following resources:
- [Introduction to Amazon EC2](https://000004.awsstudygroup.com/vi/)
- [Working with Amazon VPC](https://000003.awsstudygroup.com/vi/)

In this preparation step, we will configure a security solution for **EC2** using **GuardDuty**. Specifically, we will create two EC2 instances:
- **target EC2**: This instance will be the system that needs to be protected, with an **external IP** to test its security posture.
- **attack EC2**: This instance will simulate attacks and scan open ports from an **external IP** to the **target EC2**.

### Content
  - [Prepare VPC and EC2](2.1-createec2/)
