---
title : "Create Key Pair"
date : "2024-12-10"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create Key Pair

To ensure secure access to **EC2 instances**, AWS uses private/public key pairs. For **Windows** instances, the key pair is used to retrieve the administrator password through the **Amazon EC2 console**. In this section, you will create a key pair.

![Create Key Pair](/images/2-Pre/0003.png?featherlight=false&width=45pc)

1. Access the **AWS Management Console**

   - Search for EC2
   - Select **EC2**

   ![Create Key Pair](/images/2.1-CreateKeypair/1.png?width=90pc)

2. In the **EC2** interface

   - Select **Key Pairs**
   - Select **Create key pair**

   ![Create Key Pair](/images/2.1-CreateKeypair/2.png?width=90pc)

3. In the **Create key pair** interface

   - Enter **``` hyrid-DNS ```** for **Name**
   - **Key pair type**, select **RSA**
   - **Private key file format**, select **.pem**
   - Select **Create key pair**

   ![Create Key Pair](/images/2.1-CreateKeypair/3.png?width=90pc)

4. Key pair created successfully.

   ![Create Key Pair](/images/2.1-CreateKeypair/4.png?width=90pc)

5. Important: AWS will automatically download the private key file with the filename **hybrid-DNS.pem**. Make sure you save the PEM file and remember its location because you cannot download this key file again. You will need to use it to decrypt the password and connect to the **EC2 instance** deployed in the next step.

   ![alt text](/images/2.1-CreateKeypair/0005.png?width=40pc)
