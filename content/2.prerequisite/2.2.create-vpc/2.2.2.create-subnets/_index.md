---
title: "Create Subnets"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2.2 </b> "
---

#### Create **_public-subnet_**

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Subnets**.
   - Click **Create subnet**.

![start-create-public-subnet](/images/create-vpc/subnet/start-create-subnet-1.png)

2. At the **Create subnet** page.
   - In the **VPC ID** section, select **_my-vpc_**.
   - In the **Subnet name** field, enter _`public-subnet`_.
   - In the **Availability Zone** section, select the first Availability zone **ap-southeast-1a**.
   - In the **IPv4 subnet CIRD block** field, enter _`10.10.1.0/24`_.
   - Click **Create subnet**.

![choose-vpc](/images/create-vpc/subnet/choose-vpc.png)

![create-public-subnet](/images/create-vpc/subnet/create-public-subnet.png)

#### Create **_private-subnet_**

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Subnets**.
   - Click **Create subnet**.

![start-create-private-subnet](/images/create-vpc/subnet/start-create-subnet-2.png)

2. At the **Create subnet** page.
   - In the **VPC ID** section, select **_my-vpc_**.
   - In the **Subnet name** field, enter _`private-subnet`_.
   - In the **Availability Zone** section, select the first Availability zone **ap-southeast-1a**.
   - In the **IPv4 subnet CIRD block** field, enter _`10.10.2.0/24`_.
   - Click **Create subnet**.

![choose-vpc](/images/create-vpc/subnet/choose-vpc.png)

![create-private-subnet](/images/create-vpc/subnet/create-private-subnet.png)

In the **Subnets** section, review the two subnets that were successfully created.
![create-subnets-success](/images/create-vpc/subnet/create-subnet-success.png)
