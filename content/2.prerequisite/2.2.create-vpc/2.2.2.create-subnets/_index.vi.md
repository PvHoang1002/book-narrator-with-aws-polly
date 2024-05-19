---
title: "Tạo các Subnet"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2.2 </b> "
---

#### Tạo **_public-subnet_**

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Subnets**.
   - Nháy chuột vào **Create subnet**.

![bắt đầu tạo public subnet](/images/create-vpc/subnet/start-create-subnet-1.png)

2. Tại trang **Create subnet**.
   - Trong phần **VPC ID**, chọn **_my-vpc_**.
   - Trong vùng **Subnet name**, nhập _`public-subnet`_.
   - Trong phần **Availability Zone**, chọn Availability zone đầu tiên **ap-southeast-1a**.
   - Trong vùng **IPv4 subnet CIRD block**, nhập _`10.10.1.0/24`_.
   - Nháy chuột vào **Create subnet**.

![chọn vpc](/images/create-vpc/subnet/choose-vpc.png)

![tạo public subnet](/images/create-vpc/subnet/create-public-subnet.png)

#### Tạo **_private-subnet_**

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Subnets**.
   - Nháy chuột vào **Create subnet**.

![bắt đầu tạo private subnet](/images/create-vpc/subnet/start-create-subnet-2.png)

2. Tại trang **Create subnet**.
   - Trong phần **VPC ID**, chọn **_my-vpc_**.
   - Trong vùng **Subnet name**, nhập _`private-subnet`_.
   - Trong phần **Availability Zone**, chọn Availability zone đầu tiên **ap-southeast-1a**.
   - Trong vùng **IPv4 subnet CIRD block**, nhập _`10.10.2.0/24`_.
   - Nháy chuột vào **Create subnet**.

![chọn vpc](/images/create-vpc/subnet/choose-vpc.png)

![tạo private subnet](/images/create-vpc/subnet/create-private-subnet.png)

Trong phần **Subnets**, kiểm tra lại hai subnet vừa được tạo thành công.
![tạo các subnet thành công](/images/create-vpc/subnet/create-subnet-success.png)
