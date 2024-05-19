---
title: "Create VPC"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.2.1 </b> "
---

#### Create VPC **_my-vpc_**

1. Go to [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   ![open-vpc](/images/create-vpc/vpc/open-vpc.png)
   - Click **Your VPCs**.
   - Click **Create VPC**.

![start-create-vpc](/images/create-vpc/vpc/start-create-vpc.png)

2. At the **Create VPC** page.
   - In the **Resources to create** section, select **VPC only**.
   - In the **Name tag** field, enter _`my-vpc`_.
   - In the **IPv4 CIDR** field, enter: _`10.10.0.0/16`_.
   - All other settings, leave as default.
   - Click **Create VPC**.

![configure-vpc](/images/create-vpc/vpc/configure-vpc.png)

![create-vpc](/images/create-vpc/vpc/create-vpc.png)
