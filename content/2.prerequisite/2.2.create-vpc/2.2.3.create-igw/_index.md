---
title: "Create Internet Gateway"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.2.3 </b> "
---

#### Create IGW **_my-internet-gateway_**

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Internet gateways**.
   - Click **Create internet gateway**.

![start-create-igw](/images/create-vpc/igw/start-create-igw.png)

2. At the **Create internet gateway** page.
   - In the **Name tag** field, enter _`my-internet-gateway`_.
   - Click **Create internet gateway**.

![create-igw](/images/create-vpc/igw/create-igw.png)

3. At the **_my-internet-gateway_** page.
   - Click **Actions**.
   - Click **Attach to VPC**.

![start-attach-igw](/images/create-vpc/igw/start-attach-igw.png)

4. At the **Attach to VPC** page.
   - Select **_my-vpc_**.
   - Click **Attach internet gateway**

![attach-igw-to-vpc](/images/create-vpc/igw/attach-igw-to-vpc.png)

The IGW **_my-internet-gateway_** was successfully attached to VPC **_my-vpc_**.

![attach-igw-success](/images/create-vpc/igw/attach-igw-success.png)
