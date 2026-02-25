---
title : "Create Route 53 Outbound Endpoint"
date : "2024-12-10"
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---

#### Create Route 53 Outbound Endpoint

**Step 1:** First, we will create an **Outbound Endpoint** in Route 53 to allow **Route 53 Resolver** to forward **DNS** queries for domains hosted outside of Route 53. When you create an **Outbound Endpoint** in Route 53, AWS will automatically create an **Elastic Network Interface** (ENI) in each **Availability Zone** (AZ) that you specify.

![RDGW](/images/2-Pre/0006.png?featherlight=false&width=45pc)

**Step 2:** Access the Route 53 interface through the search box and select Route 53.
- Expand the left menu, select **Outbound Endpoints** and click **Create Outbound Endpoint**.

![RDGW](/images/5.1-CreateOE/1.png?featherlight=false&width=90pc)
![RDGW](/images/5.1-CreateOE/2.png?featherlight=false&width=90pc)

**Step 3:** On the **Create Outbound Endpoint** page, fill in the following information:
   - **Endpoint name**: **`R53-OutboundEndpoint`**
   - **VPC in the Region**: HybridDNS-VPCStack- (This is the VPC created by CloudFormation in the previous section)
   - **Security group for this endpoint**: d-###….#_controllers (This is the security group created by CloudFormation to protect connections to **AWS Managed Microsoft Active Directory**)

![RDGW](/images/5.1-CreateOE/3.png?width=92pc)

**Step 4:** Configure **IP addresses**

- **IP address #1:**
  - In **Availability Zone**, select "us-east-2a"
  - In **Subnet**, select "Private subnet 1A"
  - In **IP address**, select "Use an IP address that is selected automatically"
- **IP address #2:**
  - In **Availability Zone**, select "us-east-2b"
  - In **Subnet**, select "Private subnet 2A"
  - In **IP address**, select "Use an IP address that is selected automatically"

![RDGW](/images/5.1-CreateOE/4.png?width=92pc)
![RDGW](/images/5.1-CreateOE/5.png?featherlight=false&width=90pc)

**Step 5:** Finally, click **Create Outbound Endpoint**.

![RDGW](/images/5.1-CreateOE/6.png?featherlight=false&width=90pc)

**Step 6:** After about 5 minutes, the **Outbound Endpoint** will be successfully configured in your VPC.

![RDGW](/images/5.1-CreateOE/7.png?featherlight=false&width=90pc)

**Step 7:** When the **Outbound Endpoints** have been created, click on the **Outbound Endpoint** item to view detailed information. You will see a list of IP addresses assigned to the **Outbound Endpoints**. AWS will place an **Elastic Network Interface** (ENI) in your subnet and assign this IP address to the ENI.

![RDGW](/images/5.1-CreateOE/7.png?featherlight=false&width=90pc)
