---
title: "Clean up resources"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: "<b>5. </b>"
---

We will take the following steps to delete the resources we created in this project.

#### Delete EC2 instances

Go to [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/), click **Instances**.

- Select **public-instance**.
  - Click **Instance state**.
  - Click **Terminate instance**, then click **Terminate** to confirm.
- For **_private-instance_**, perform the same actions.

![delete-ec2-instance](/images/clean-up-resource/delete-ec2-instance.png)

#### Delete S3 buckets

Go to [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).

- Select **_input-bucket-for-polly_**.
  - Click **Empty**.
  - Enter _`permanently delete`_, then click **Empty** to proceed to delete the objects in the bucket.
  - After deleting all objects in the bucket, click **Delete**.
  - Enter _`input-bucket-for-polly`_, then click **Delete bucket** to proceed with deleting the S3 bucket.
- For **_output-bucket-from-polly_**, perform the same actions.

![empty-bucket](/images/clean-up-resource/empty-bucket.png)

![delete-bucket](/images/clean-up-resource/delete-bucket.png)

#### Delete Lambda function

Go to [AWS Lambda](https://aws.amazon.com/lambda/)

- Select **_text-to-speech-converter_**.
- Click **Actions**, then click **Delete**.
- In the confirm box, enter _`delete`_, then click **Delete** to proceed with deleting the function.

![delete-lambda-function](/images/clean-up-resource/delete-lambda-function.png)

#### Delete VPC Endpoint

Go to [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).

- Click **Endpoints**.
- Select **_s3-endpoint_**.
- Click **Actions**, then click **Delete VPC endpoints**.
- In the confirm box, enter _`delete`_, then click **Delete** to proceed with deleting the endpoint.

![delete-endpoint](/images/clean-up-resource/delete-endpoint.png)

#### Delete VPC

At the [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/) page.

- Click **Your VPCs**.
- Select **_my-vpc_**.
- Click **Actions**, then click **Delete VPC**.
- In the confirm box, enter _`delete`_ to confirm, then click **Delete** to delete **_my-vpc_** and its related resources.

![delete-vpc](/images/clean-up-resource/delete-vpc.png)

#### Delete IAM Roles

Go to [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/).

- Click **Roles**.
- Select both **_ec2-access-s3_** and **_lambda-access-s3-polly_** roles.
- Click **Delete**.
- In the confirm box, enter _`delete`_ to confirm, then click **Delete** to proceed with deleting IAM roles.

![delete-iam-role](/images/clean-up-resource/delete-iam-role.png)
