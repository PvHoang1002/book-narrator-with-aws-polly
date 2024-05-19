---
title: "Access to EC2 instances"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

In this step, we will proceed to access to **_public-instance_** first. The **_public-instance_** will act like a Bastion host in order to help us access to the **_private-instance_**.

{{% notice note %}}
Bastion host is a special-purpose computer to manage private instances or databases located in a private subnet (without having to deal with the Internet). Bastion host is located in the public subnet and acts as a "gateway of login" between the outside world and private subnets.
{{% /notice %}}

#### Access to **_public-instance_**

1. Go to [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/).

   - Click **Instances**.
   - Select **_public-instance_** and copy its public IP address.

2. Open **MobaXterm** and creat a new **SSH** session.
   - In the **Remote host** field, enter the copied **_public-instance_**'s public IP address.
   - In the **Specify username** field, enter _`ec2-user`_.
   - Select **Use private key** and select **_aws-keypair.pem_** file stored in your computer.
   - All other settings, leave as default. Then click **OK**.

![connect-public-instance](/images/connect-ec2/connect-public-instance.png)

3. Connection to **_public-instance_** has been established successfully.
   - Enter _`pwd`_ command and press **Enter** to ensure the working directory is **_/home/ec2-user/_**.
   - Enter _`sudo su`_ command and press **Enter** (This command may not need to be executed).
   - Enter _`nano aws-keypair.pem`_ command and press **Enter**.

![nano-keypair-file](/images/connect-ec2/nano-keypair-file.png)

4. Keep the **MobaXterm** window open.
   - Navigate to the **_aws-keypair.pem_** file storage location on your computer and open it.
   - Copy the private key and paste it into **MobaXterm** screen.
   - Press the key combination Ctrl + S to save the file content and Ctrl + X to exit the nano editor.

![copy-keypair](/images/connect-ec2/copy-keypair.png)

#### Access to **_private-instance_**

1. At the **Instances** page on **AWS Console**, copy the **_private-instance_**'s private IP address.
   - On the **MobaXterm** screen, enter _`chmod 400 aws-keypair.pem`_ command and press **Enter**.
   - Enter _`ssh -i "aws-keypair.pem" ec2-user@private-ip`_ command and press **Enter** (Remember to replace _private-ip_ with **_private-instance_**'s private IP address).

Connection to **_private-instance_** will be established successfully. Keep the **MobaXterm** window open, we will move to the next step.

![connect-private-instance](/images/connect-ec2/connect-private-instance.png)
