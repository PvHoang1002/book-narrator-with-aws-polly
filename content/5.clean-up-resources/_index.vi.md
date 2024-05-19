---
title: "Dọn dẹp tài nguyên"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: "<b>5. </b>"
---

Chúng ta sẽ thực hiện các bước sau để xóa các tài nguyên mà chúng ta đã tạo trong project này.

#### Xóa các máy ảo EC2

Đi tới trang [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/), nháy chuột vào **Instances**.

- Chọn **public-instance**.
  - Nháy chuột vào **Instance state**.
  - Nháy chuột vào **Terminate instance**, sau đó nháy chuột vào **Terminate** để xác nhận.
- Đối với máy ảo **_private-instance_**, thực hiện những thao tác tương tự.

![xóa máy ảo ec2](/images/clean-up-resource/delete-ec2-instance.png)

#### Xóa các S3 bucket

Đi tới trang [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).

- Chọn bucket **_input-bucket-for-polly_**.
  - Nháy chuột vào **Empty**.
  - Nhập _`permanently delete`_, sau đó nháy chuột vào **Empty** để tiến hành xóa các object có trong bucket.
  - Sau khi xóa hết các object trong bucket, nháy chuột vào **Delete**.
  - Nhập _`input-bucket-for-polly`_, sau đó nháy chuột vào **Delete bucket** để tiến hành xóa S3 bucket.
- Đối với bucket **_output-bucket-from-polly_**, thực hiện những thao tác tương tự.

![làm rỗng bucket](/images/clean-up-resource/empty-bucket.png)

![xóa bucket](/images/clean-up-resource/delete-bucket.png)

#### Xóa hàm Lambda

Đi tới trang [AWS Lambda](https://aws.amazon.com/lambda/)

- Chọn **_text-to-speech-converter_**.
- Nháy chuột vào **Actions**, sau đó nháy chuột vào **Delete**.
- Trong cửa sổ xác nhận, nhập _`delete`_, sau đó nháy chuột vào **Delete** để tiến hành xóa hàm.

![xóa hàm lambda](/images/clean-up-resource/delete-lambda-function.png)

#### Xóa VPC Endpoint

Đi tới trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).

- Nháy chuột vào **Endpoints**.
- Chọn **_s3-endpoint_**.
- Nháy chuột vào **Actions**, sau đó nháy chuột vào **Delete VPC endpoints**.
- Trong cửa sổ xác nhận, nhập _`delete`_, sau đó nháy chuột vào **Delete** để tiến hành xóa endpoint.

![xóa endpoint](/images/clean-up-resource/delete-endpoint.png)

#### Xóa VPC

Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).

- Nháy chuột vào **Your VPCs**.
- Chọn **_my-vpc_**.
- Nháy chuột vào **Actions**, sau đó nháy chuột vào **Delete VPC**.
- Trong cửa sổ xác nhận, nhập _`delete`_ để xác nhận xóa, sau đó nháy chuột vào **Delete** để xóa **_my-vpc_** và các tài nguyên liên quan đến nó.

![xóa vpc](/images/clean-up-resource/delete-vpc.png)

#### Xóa các IAM Role

Đi tới trang [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/).

- Nháy chuột vào **Roles**.
- Chọn cả hai role **_ec2-access-s3_** và **_lambda-access-s3-polly_**.
- Nháy chuột vào **Delete**.
- Trong cửa sổ xác nhận, nhập _`delete`_ để xác nhận xóa, sau đó nháy chuột vào **Delete** để tiến hành xóa các IAM role.

![xóa các iam role](/images/clean-up-resource/delete-iam-role.png)
