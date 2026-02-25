---
title : "Launch CloudFormation Template"
date : "2024-12-10"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

#### Launch CloudFormation Template

In this step, you will build the network infrastructure in AWS. In this section, you will leverage the template from **AWS Quick Start** to build a highly available (HA) and secure network infrastructure using **AWS CloudFormation**. Below is the architecture that will be built from the template.

![Launch CloudFormation](/images/2-Pre/0002.png?width=45pc)

## Step 1: Log in to AWS Management Console

- Find and select **CloudFormation** in the AWS Management Console.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/1.png?width=90pc)

## Step 2: Create CloudFormation stack

1. In the **CloudFormation** interface, select **Create stack**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/2.png?width=90pc)

2. In the **Create stack** interface:

   - **Prepare Template**: Template is ready.
   - **Template Source**: **Amazon S3 URL**
   - **Amazon S3 URL**: `https://aws-quickstart.s3.amazonaws.com/quickstart-microsoft-rdgateway/templates/rdgw-master.template`
   - Select **Next**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/3.png?width=90pc)

3. Configure the stack:

   - In **Stack name**, enter **`HybridDNS`**.
   - In **Availability Zones**, select **us-east-2a and us-east-2b**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/4.png?width=90pc)

4. Configure Network:

   - In **VPC CIDR, Private Subnet 1 & 2 CIDR, and Public Subnet 1 & 2 CIDR**, keep the default values.
   - In **Allowed Remote Desktop Gateway External Access CIDR**, enter **`0.0.0.0/0`**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/5.png?width=70pc)

{{% notice warning %}}
This configuration allows any IP address to access the RDP port of the EC2 instance to be created. This is not a secure configuration and should not be used in production environments. We will adjust access permissions after the CloudFormation template deployment is complete.
{{% /notice %}}

5. In the **Amazon EC2 configuration** step:

   - In **Key Pair Name**, select the previously created Key Pair **``` hybrid-DNS ```**.
   - In **Remote Desktop Gateway Instance Type**, keep the default value (t2.large).
   - In **Number of RDGW Hosts**, keep the default value (1).
   - In **Admin User Name**, keep the default value (StackAdmin).
   - **Admin Password**, set an easy-to-remember password for you.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/6.png?width=70pc)

{{% notice tip %}}
The diagram above shows two RDGW hosts (one host per Availability Zone). For practice purposes, we start with one RDGW host to reduce CloudFormation initialization time. However, as shown in the diagram, you can see the RDGW host is deployed in an Auto Scaling Group. After the CloudFormation stack deployment is complete, you can try configuring the Auto Scaling group. Auto Scaling group is an important service that provides availability and scalability for your applications.
{{% /notice %}}

6. For other options, keep the default values and select **Next**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/7.png?width=91pc)

7. Select **Next**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/8.png?width=90pc)
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/9.png?width=90pc)

8. Review the stack settings on the Review HybridDNS screen. Check the two checkboxes and select **Create Stack**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/10.png?width=90pc)

9. Finally, select **Submit** for the newly created stack.
![Launch CloudFormation](/images/2.2-LaunchCloudFormation/11.png?width=91pc)

10. The template takes about 15 minutes to complete. During this time, we will review the components that the CloudFormation template will create. After the stack initialization process is complete, the stack status will change to **CREATE_COMPLETE**.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/12.png?width=91pc)

11. View the **Output** section of the newly created stack.

![Launch CloudFormation](/images/2.2-LaunchCloudFormation/13.png?width=91pc)
