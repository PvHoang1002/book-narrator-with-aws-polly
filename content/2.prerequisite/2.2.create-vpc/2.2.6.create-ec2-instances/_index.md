---
title: "Create EC2 Instances"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 2.2.6 </b> "
---

#### Create **_public-instance_**

1. Go to [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/).
   ![choose](/images/create-ec2/choose-ec2.png)
   - Click **Instances**.
   - Click **Launch instances**.

![start-create-public-instance](/images/create-ec2/start-create-ec2-1.png)

2. At the **Laucnh an instance** page, in the **Name and tags** section.
   - Enter _`public-instance`_.

![public-instance-name](/images/create-ec2/public-instance.png)

3. In the **Application and OS Images** section.
   - Select **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.

![instance-os-image](/images/create-ec2/ec2-os-image.png)

4. Next, we will choose instance type and select key pair for securly connecting to instances.

- In the **Instance Type** section.
  - Select **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.
- In the **Keypair** section.
  - Select **_aws-keypair_**. If no key pair exists, please refer to the instructions for [creating a new key pair](https://000003.awsstudygroup.com/4-createec2server/4.1-createec2/#:~:text=Select%20an%20Instance%20type%20and%20opt%20to%20Create%20a%20new%20key%20pair).

![choose-instance-type-keypair](/images/create-ec2/choose-instance-type-keypair.png)

5. Next, we will configure **_public-instance_**'s network settings and storage.

- In the **Network settings** section.
  - At the **VPC** field, select **_my-vpc_**.
  - At the **Subnet** field, select **_public-subnet_**.
  - At the **Auto-assign public IP** field, select **Enable**.
  - At the **Firewall** field, choose **Select existing security group** and select **_public-security-group_**.
- In the **Configure storage** section.
  - Select 1x **8** GiB **gp2** root volume.
- Click **Laucnh instance**.

![launch-public-instance](/images/create-ec2/launch-public-instance.png)

#### Create **_private-instance_**

1. At the [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/) page.
   - Click **Launch instances**.

![start-create-private-instance](/images/create-ec2/start-create-ec2-2.png)

2. At the **Laucnh an instance** page, in the **Name and tags** section.
   - Enter _`private-instance`_.

![private-instance-name](/images/create-ec2/private-instance.png)

3. In the **Application and OS Images** section.
   - Select **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.

![instance-os-image](/images/create-ec2/ec2-os-image.png)

4. Next, we will choose instance type and select key pair for securly connecting to instances.

- In the **Instance Type** section.
  - Select **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.
- In the **Keypair** section.
  - Select **_aws-keypair_**.

![choose-instance-type-keypair](/images/create-ec2/choose-instance-type-keypair.png)

5. Next, we will configure **_private-instance_**'s network settings and storage.

- In the **Network settings** section.
  - At the **VPC** field, select **_my-vpc_**.
  - At the **Subnet** field, select **_private-subnet_**.
  - At the **Auto-assign public IP** field, select **Disable**.
  - At the **Firewall** field, choose **Select existing security group** and select **_private-security-group_**.
- In the **Configure storage** section.
  - Select 1x **8** GiB **gp2** root volume.

![setting-private-instance](/images/create-ec2/setting-private-instance.png)

6. Click the **Advanced details** section.
   - At the **Instance profile** field, select **_ec2-access-s3_**.
   - Click **Launch instance**.

![launch-private-instance](/images/create-ec2/launch-private-instance.png)

In the **Instances** section, review the two public/private instances that were successfully created and their states are **Running**.

![create-instances-success](/images/create-ec2/create-ec2-instances-success.png)

7. Select the **_private-instance_**.
   - Click **Actions**.
   - Click **Security**.
   - Click **Modify IAM role**.

![start-check-private-instance-role](/images/create-ec2/start-check-private-instance-role.png)

The **_private-instance_**'s IAM role is **_ec2-access-s3_**.

![check-private-instance-role](/images/create-ec2/check-private-instance-role-success.png)
