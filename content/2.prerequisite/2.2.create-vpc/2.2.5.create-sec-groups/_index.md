---
title: "Create Security Groups"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.2.5 </b> "
---

In this step, we will proceed to create the security groups used for our EC2 instances.

#### Create **_public-security-group_**

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Security groups**.
   - Click **Create security group**.

![start-create-public-sg](/images/create-vpc/sg/start-create-sg-1.png)

2. At the **Create security group** page, in the **Basic details** section.
   - In the **Security group name** field, enter _`public-security-group`_.
   - In the **Description** field, enter _`Security group for public instances`_.
   - Select **_my-vpc_**.

![config-public-sg](/images/create-vpc/sg/config-public-sg.png)

3. In the **Inbound rules** section, add two rules.
   - First rule: select **All ICMP - IVv4** type and **Anywhere-IPv4** source.
   - Second rule: select **SSH** type and **Anywhere-IPv4** source.

![inbound-rules-for-public-sg](/images/create-vpc/sg/inbound-rules-for-public-sg.png)

4. Scroll down to bottom of the page.
   - All other settings, leave as default.
   - Click **Create security group**.

#### Create **_private-security-group_**

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Security groups**.
   - Click **Create security group**.

![start-create-private-sg](/images/create-vpc/sg/start-create-sg-2.png)

2. At the **Create security group** page, in the **Basic details** section.
   - In the **Security group name** field, enter _`private-security-group`_.
   - In the **Description** field, enter _`Security group for private instances`_.
   - Select **_my-vpc_**.

![config-private-sg](/images/create-vpc/sg/config-private-sg.png)

3. In the **Inbound rules** section, click **Add rule**.
   - Select **SSH** type.
   - Select **Custom** source and enter _`10.10.1.0/24`_ (the IPv4 CIDR block of **_public-subnet_**).

![inbound-rules-for-private-sg](/images/create-vpc/sg/inbound-rules-for-private-sg.png)

4. Scroll down to bottom of the page.
   - All other settings, leave as default.
   - Click **Create security group**.
