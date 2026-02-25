---
title : "Configure Security Group"
date : "2024-12-10"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

#### Configure Security Group

1. Log in to **AWS Console** and access **EC2 Management console** through the search box and search for "EC2".

   - Make sure you have selected the correct Region. Pay attention to the upper left corner of the **AWS Console** and select the correct Region you need (Here we are selecting us-east-2)

![Security Group](/images/2.3-SecurityGroup/1.png?width=90pc)

2. In the **EC2** interface

   - In the left menu, select **Security Groups**.
   - Check the checkbox of the security group with the description "**Enable RDP access from the Internet**"
   - In the area at the bottom of the screen, select the Inbound tab.
   - Select **Edit inbound rules**.

![Security Group](/images/2.3-SecurityGroup/2.png?width=90pc)

3. Configure and edit **Inbound**

   - Click **Delete** next to the rule with **Port Range** content, 3391 to delete the rule
   - Click **Delete** next to the rule with **Port Range** content, 443 to delete the rule
   - For the RDP rule in the Source column, select "**My IP**" from the list (within the scope of the lab you can select **0.0.0.0/0**)
   - For the ICMP rule in the Source column, select "**My IP**" from the list (within the scope of the lab you can select **0.0.0.0/0**)
   - Select Save rules

![Security Group](/images/2.3-SecurityGroup/3.png?width=90pc)

4. Complete security group configuration.

![Security Group](/images/2.3-SecurityGroup/4.png?width=90pc)

{{% notice tip %}}
When securing your application, you need to ensure **only open the ports that your application needs**. In this step, **you have deleted ports *3391* and *443***, because you will not use those ports in this lab. Additionally, you have locked access so that RDP and ICMP connections **can only originate from your public IP address**.
{{% /notice %}}