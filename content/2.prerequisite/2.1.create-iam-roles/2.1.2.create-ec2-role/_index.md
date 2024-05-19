---
title: "Create EC2 Role"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.1.2 </b> "
---

#### Create role **_ec2-access-s3_**

1. At the [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/) page.
   - Click **Create role**.

![start-create-role](/images/create-role/start-create-role-2.png)

2. At the **Select trusted entity** page.
   - In the **Trusted entity type** section, select **AWS service**.
   - In the **Use case** section, select **EC2** use case.
   - Click **Next**.

![choose-ec2-service](/images/create-role/choose-ec2-service.png)

3. At the **Add permissions** page.
   - In the **Permissions policies** section, enter _`AmazonS3FullAccess`_ into the search field.
   - Select **_AmazonS3FullAccess_** policy.
   - Click **Next**.

![add-s3-permission](/images/create-role/add-s3-permission-to-ec2.png)

4. At the **Name, review, and create** page.
   - In the **Role details** section, enter _`ec2-access-s3`_ into the **Role name** field.
   - Reivew **Permissions policy summary** section.
   - Click **Create role**.

![ec2-role-name](/images/create-role/ec2-role-name.png)

![create-role-ec2](/images/create-role/create-role-ec2.png)
