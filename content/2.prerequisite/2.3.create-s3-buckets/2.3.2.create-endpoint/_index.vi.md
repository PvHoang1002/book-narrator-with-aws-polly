---
title: "Tạo S3 Gateway Endpoint"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.3.2 </b> "
---

#### Tạo endpoint **_s3-endpoint_**

1. Đi tới trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   ![mở vpc](/images/create-vpc/vpc/open-vpc.png)
   - Nháy chuột vào **Endpoints**.
   - Nháy chuột vào **Create endpoint**.

![bắt đầu tạo s3 endpoint](/images/create-s3/start-create-s3-endpoint.png)

2. Tại trang **Create endpoint**.

- Trong phần **Endpoint settings**.
  - Trong vùng **Name tag**, nhập _`s3-endpoint`_.
  - Tại vùng **Service category**, chọn **AWS services**.
- Trong phần **Services**.
  - Nhập _`com.amazonaws.ap-southeast-1.s3`_ vào vùng tìm kiếm.
  - Chọn **com.amazonaws.ap-southeast-1.s3** với Type là **Gateway**.

![cài đặt endpoint 1](/images/create-s3/endpoint-settings-1.png)

- Trong phần **VPC**.
  - Chọn **_my-vpc_**.
- Trong phần **Route tables** .
  - Chọn **_private-route-table_**.

![cài đặt endpoint 2](/images/create-s3/endpoint-settings-2.png)

3. Kéo chuột tới cuối trang, sau đó nháy chuột vào **Create endpoint**.

![tạo endpoint](/images/create-s3/create-endpoint.png)

Trong phần **Endpoints**, kiểm tra lại endpoint vừa được tạo thành công.

![tạo endpoint thành công](/images/create-s3/create-endpoint-success.png)

4. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).

- Nháy chuột vào **Route tables**.
- Chọn **_private-route-table_**.

Đã có một tuyến đường mới ánh xạ tới **_s3-endpoint_** mà chúng ta vừa tạo.

![cập nhật private rtb thành công](/images/create-s3/update-private-route-table-success.png)
