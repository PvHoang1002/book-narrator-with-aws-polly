---
title: "Tạo VPC"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.2.1 </b> "
---

#### Tạo VPC **_my-vpc_**

1. Đi tới trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   ![mở vpc](/images/create-vpc/vpc/open-vpc.png)
   - Nháy chuột vào **Your VPCs**.
   - Nháy chuột vào **Create VPC**.

![bắt đầu tạo vpc](/images/create-vpc/vpc/start-create-vpc.png)

2. Tại trang **Create VPC**.
   - Trong phần **Resources to create**, chọn **VPC only**.
   - Trong vùng **Name tag**, nhập _`my-vpc`_.
   - Trong vùng **IPv4 CIDR**, nhập: _`10.10.0.0/16`_.
   - Các cài đặt khác, giữ nguyên theo mặc định.
   - Nháy chuột vào **Create VPC**.

![cấu hình vpc](/images/create-vpc/vpc/configure-vpc.png)

![tạo vpc](/images/create-vpc/vpc/create-vpc.png)
