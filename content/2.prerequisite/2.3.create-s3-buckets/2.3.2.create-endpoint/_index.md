---
title: "Create S3 Gateway Endpoint"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.3.2 </b> "
---

#### Create endpoint **_s3-endpoint_**

1. Go to [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   ![choose-vpc](/images/create-vpc/vpc/open-vpc.png)
   - Click **Endpoints**.
   - Click **Create endpoint**.

![start-create-s3-endpoint](/images/create-s3/start-create-s3-endpoint.png)

2. At the **Create endpoint** page.

- In the **Endpoint settings** section.
  - In the **Name tag** field, enter _`s3-endpoint`_.
  - In the **Service category** field, select **AWS services**.
- In the **Services** section.
  - Enter _`com.amazonaws.ap-southeast-1.s3`_ into the search box.
  - Select **com.amazonaws.ap-southeast-1.s3** with Type is **Gateway**.

![endpoint-settings-1](/images/create-s3/endpoint-settings-1.png)

- In the **VPC** section.
  - Select **_my-vpc_**.
- In the **Route tables** section.
  - Select **_private-route-table_**.

![endpoint-settings-2](/images/create-s3/endpoint-settings-2.png)

3. Scroll down to the bottom of the page, then click **Create endpoint**.

![create-endpoint](/images/create-s3/create-endpoint.png)

In the **Endpoints** section, review the endpoint that was successfully created.

![create-endpoint-success](/images/create-s3/create-endpoint-success.png)

4. At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.

- Click **Route tables**.
- Select **_private-route-table_**.

There is a new route mapping to the s3-endpoint we just created.

![update-private-route-table-success](/images/create-s3/update-private-route-table-success.png)
