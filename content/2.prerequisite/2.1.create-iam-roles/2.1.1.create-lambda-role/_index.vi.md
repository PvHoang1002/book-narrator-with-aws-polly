---
title: "Tạo Lambda Role"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.1.1 </b> "
---

#### Tạo role **_lambda-access-s3-polly_**

1. Đi tới trang [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/)
   .![mở iam](/images/create-role/open-iam.png)
   - Nháy chuột vào **Roles** .
   - Nháy chuột vào **Create role** .

![bắt đầu tạo role](/images/create-role/start-create-role-1.png)

2. Tại trang **Select trusted entity**.
   - Trong phần **Trusted entity type** , chọn **AWS service**.
   - Trong phần **Use case** , chọn **Lambda** use case.
   - Nháy chuột vào **Next**.

![chọn dịch vụ lambda](/images/create-role/choose-lambda-service.png)

3. Tại trang **Add permissions**.

- Trong phần **Permissions policies**, nhập _`AmazonS3FullAccess`_ vào vùng tìm kiếm.
  - Chọn chính sách **_AmazonS3FullAccess_**.

![thêm quyền truy cập s3](/images/create-role/add-s3-permission-to-ec2.png)

- Tại trang **Permissions policies**, nhập _`AmazonPollyFullAccess`_ vào vùng tìm kiếm.
  - Chọn chính sách **_AmazonPollyFullAccess_**.
  - Nháy chuột vào **Next**.

![thêm quyền truy cập polly](/images/create-role/add-polly-permission-to-lambda.png)

4. Tại trang **Name, review, and create**.
   - Trong phần **Role details**, nhập _`lambda-access-s3-polly`_ vào **Role name**.
   - Kiểm tra lại phần **Permissions policy summary**.
   - Nháy chuột vào **Create role**.

![đặt tên lambda role](/images/create-role/lambda-role-name.png)

![tạo lambda role](/images/create-role/create-role-lambda.png)
