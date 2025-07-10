---
title : "Prepare VPC and EC2"
date: 2025-07-06
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---

In this step, we will need to create a **VPC**. After creating the VPC, a **public subnet** will be automatically created. Next, we will create **2 Linux EC2 instances** in the **public subnet**:
- **target EC2**: The target machine that will be attacked and tested for security.
- **attack EC2**: The attack machine that will simulate intrusion attempts on the **target EC2**.

The architecture overview after completing this step will look like this:

![VPC](/images/arc-001.png)

To learn how to create **EC2 instances** and **VPC** with **public subnet**, you can refer to the following lab resources:
- [Introduction to Amazon EC2](https://000004.awsstudygroup.com/vi/)
- [Working with Amazon VPC](https://000003.awsstudygroup.com/vi/)

### Content
  - [Create VPC](2.1.1-createvpc/)
  - [Create Security Group](2.1.2-createsecgroup/)
  - [Create target EC2 instance](2.1.3-createec2target/)
  - [Create attack EC2 instance](2.1.4-createec2attack/)
