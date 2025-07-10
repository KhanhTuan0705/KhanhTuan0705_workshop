---
title : "Create VPC"
date: 2025-07-06
weight : 1 
chapter : false
pre : " <b> 2.1.1 </b> "
---

### Create VPC `SecurityVPC`

Go to the [AWS VPC Console](https://console.aws.amazon.com/vpc/home) to begin creating a new VPC.

---

1. In the VPC dashboard, select **Your VPCs** and click **Create VPC** at the top-right corner.

![VPC](/images/2.prerequisite/01-createvpc.png)

---

2. On the **Create VPC** screen:
   - Select **VPC and more** so AWS automatically creates the associated resources (subnets, route table, internet gateway, etc.).
   - Enter the name: `SecurityVPC`
   - IPv4 CIDR block: `10.0.0.0/16`
   - Select **No IPv6 CIDR block**

![VPC](/images/2.prerequisite/02-createvpc.png)

---

3. Configure availability zones and subnets:
   - Availability Zones: select `1`
   - Public Subnets: select `1`
   - Private Subnets: select `0`

![VPC](/images/2.prerequisite/03-createvpc.png)

---

4. Configure advanced settings:
   - NAT Gateway: select `None`
   - VPC Endpoints: select `None`
   - Make sure to check:
     - Enable DNS hostnames
     - Enable DNS resolution
   - Click **Create VPC** to finish

![VPC](/images/2.prerequisite/04-createvpc.png)
