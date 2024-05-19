---
title: "Tạo EC2 Role"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.1.2 </b> "
---

#### Create role **_ec2-access-s3_**

1. Tại trang [AWS Identity and Access Management (IAM)](https://aws.amazon.com/iam/).
   - Nháy chuột vào **Create role**.

![bắt đầu tạo role](/images/create-role/start-create-role-2.png)

2. Tại trang **Select trusted entity**.
   - Trong phần **Trusted entity type**, chọn **AWS service**.
   - Trong phần **Use case**, chọn **EC2** use case.
   - Nháy chuột vào **Next**.

![chọn dịch vụ ec2](/images/create-role/choose-ec2-service.png)

3. Tại trang **Add permissions**.
   - Trong phần **Permissions policies**, nhập _`AmazonS3FullAccess`_ vào vùng tìm kiếm.
   - Chọn chính sách **_AmazonS3FullAccess_**.
   - Nháy chuột vào **Next**.

![thêm quyền truy cập s3](/images/create-role/add-s3-permission-to-ec2.png)

4. Tại trang **Name, review, and create**.
   - Trong phần **Role details**, nhập _`ec2-access-s3`_ vào **Role name**.
   - Kiểm tra lại phần **Permissions policy summary**.
   - Nháy chuột vào **Create role**.

![đặt tên ec2 role](/images/create-role/ec2-role-name.png)

![tạo ec2 role](/images/create-role/create-role-ec2.png)
