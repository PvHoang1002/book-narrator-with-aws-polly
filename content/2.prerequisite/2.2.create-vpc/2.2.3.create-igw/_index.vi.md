---
title: "Tạo Internet Gateway"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 2.2.3 </b> "
---

#### Tạo IGW **_my-internet-gateway_**

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Internet gateways**.
   - Nháy chuột vào **Create internet gateway**.

![bắt đầu tạo igw](/images/create-vpc/igw/start-create-igw.png)

2. Tại trang **Create internet gateway**.
   - Trong vùng **Name tag**, nhập _`my-internet-gateway`_.
   - Nháy chuột vào **Create internet gateway**.

![tạo igw](/images/create-vpc/igw/create-igw.png)

3. Tại trang **_my-internet-gateway_**.
   - Nháy chuột vào **Actions**.
   - Nháy chuột vào **Attach to VPC**.

![bắt đầu gắn igw](/images/create-vpc/igw/start-attach-igw.png)

4. Tại trang **Attach to VPC**.
   - Chọn **_my-vpc_**.
   - Nháy chuột vào **Attach internet gateway**

![gắn igw vào vpc](/images/create-vpc/igw/attach-igw-to-vpc.png)

IGW **_my-internet-gateway_** đã được gắn vào VPC **_my-vpc_** thành công.

![gắn igw thành công](/images/create-vpc/igw/attach-igw-success.png)
