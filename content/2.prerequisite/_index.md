---
title: "Preparation"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

In order to set up our project, we need to undertake several preparation activities. Firstly, we will build a Virtual Private Cloud (VPC) along with virtual machines. Additionally, we will create S3 buckets and Lambda functions. Furthermore, we will create IAM roles to grant permissions to the Lambda function and EC2 virtual machine, allowing them to access the S3 buckets and interact with AWS Polly.

{{% notice note %}}
All the services and activities within this project are within the AWS Free Tier.
{{% /notice %}}

### Content

- [Create IAM Roles](2.1.create-iam-roles/)
- [Create VPC](2.2.create-vpc/)
- [Create S3 Buckets](2.3.create-s3-buckets/)
- [Create Lambda Function](2.4.create-lambda-function/)
