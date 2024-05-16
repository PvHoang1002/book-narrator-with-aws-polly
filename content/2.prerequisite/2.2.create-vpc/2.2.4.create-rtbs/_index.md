---
title: "Create Route Tables"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.2.4 </b> "
---

#### Create public route table

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Route tables**.
   - Click **Create route table**.

![start-create-public-rtb](/images/create-vpc/rtb/start-create-rtb-1.png)

2. At the **Create route table** page.
   - In the **Name** field, enter _`public-route-table`_.
   - In the **VPC** section, select **my-vpc**.
   - Click **Create route table**.

![create-public-rtb](/images/create-vpc/rtb/create-public-rtb.png)

3. At the **_public-route-table_** page.
   - Select **Subnet associations** tab.
   - Click **Edit subnet associations**.

![start-associate-public-rtb](/images/create-vpc/rtb/start-associate-1.png)

4. At the **Edit subnet associations** page.
   - Select **_public-subnet_**.
   - Click **Save associations**.

![save-associate-public-rtb](/images/create-vpc/rtb/save-associate-1.png)

5. At the **_public-route-table_** page.
   - Select **Routes** tab.
   - Click **Edit routes**.

![start-edit-routes](/images/create-vpc/rtb/start-edit-routes-1.png)

6. At the **Edit routes** page.
   - Click **Add route**.
   - In the **Destination** field, enter _`0.0.0.0/0`_.
   - In the **Target** section, select **Internet Gateway**, then select **my-internet-gateway**.

![save-edit-routes](/images/create-vpc/rtb/save-edit-routes-1.png)

The routes of the **Public route table** were successfully edited.

![edit-routes-success](/images/create-vpc/rtb/edit-routes-success-1.png)

#### Create private route table

1. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.
   - Click **Route tables**.
   - Click **Create route table**.

![start-create-private-rtb](/images/create-vpc/rtb/start-create-rtb-2.png)

2. At the **Create route table** page.
   - In the **Name** field, enter _`private-route-table`_.
   - In the **VPC** section, select **my-vpc**.
   - Click **Create route table**.

![create-private-rtb](/images/create-vpc/rtb/create-private-rtb.png)

3. At the **_private-route-table_** page.
   - Select **Subnet associations** tab.
   - Click **Edit subnet associations**.

![start-associate-private-rtb](/images/create-vpc/rtb/start-associate-2.png)

4. At the **Edit subnet associations** page.
   - Select **_private-subnet_**.
   - Click **Save associations**.

![save-associate-private-rtb](/images/create-vpc/rtb/save-associate-2.png)

In the **Route tables** section, review the two route tables that were successfully created and associated.

![create-rtbs-success](/images/create-vpc/rtb/create-rtbs-success.png)
