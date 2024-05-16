---
title: "Create Lambda Role"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

#### Create Role **_lambda-access-s3-polly_**

1. Go to [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/).
   ![open-iam](/images/create-role/open-iam.png)
   - Click **Roles**.
   - Click **Create role**.

![start-create-role](/images/create-role/start-create-role-1.png)

2. At the **Select trusted entity** page.
   - In the **Trusted entity type** section, select _AWS service_.
   - In the **Use case** section, select _Lambda_ use case.
   - Click **Next**.

![choose-lambda-service](/images/create-role/choose-lambda-service.png)

3. At the **Add permissions** page.

- In the **Permissions policies** section, enter _`AmazonS3FullAccess`_ into the search field.
  - Select _AmazonS3FullAccess_ policy.

![add-s3-permission](/images/create-role/add-s3-permission-to-ec2.png)

- In the **Permissions policies** section, enter _`AmazonPollyFullAccess`_ into the search field.
  - Select _AmazonPollyFullAccess_ policy.
  - Click **Next**.

![add-polly-permission](/images/create-role/add-polly-permission-to-lambda.png)

4. At the **Name, review, and create** page.
   - In the **Role details** section, enter _`lambda-access-s3-polly`_ into the **Role name** field.
   - Reivew **Permissions policy summary** section.
   - Click **Create role**.

![lambda-role-name](/images/create-role/lambda-role-name.png)

![create-role-lambda](/images/create-role/create-role-lambda.png)
