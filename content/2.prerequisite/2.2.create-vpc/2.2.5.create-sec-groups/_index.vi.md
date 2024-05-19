---
title: "Tạo các Security Group"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 2.2.5 </b> "
---

Trong bước này, chúng ta sẽ tiến hành tạo các security group được sử dụng cho các máy ảo EC2.

#### Tạo **_public-security-group_**

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Security groups**.
   - Nháy chuột vào **Create security group**.

![bắt đầu tạo public sg](/images/create-vpc/sg/start-create-sg-1.png)

2. Tại trang **Create security group**, trong phần **Basic details**.
   - Trong vùng **Security group name**, nhập _`public-security-group`_.
   - Trong vùng **Description**, nhập _`Security group for public instances`_.
   - Chọn **_my-vpc_**.

![cấu hình public sg](/images/create-vpc/sg/config-public-sg.png)

3. Trong phần **Inbound rules**, thêm hai luật.
   - Luật thứ nhất: chọn giao thức **All ICMP - IVv4** và nguồn là **Anywhere-IPv4**.
   - Luật thứ hai: chọn giao thức **SSH** và nguồn là **Anywhere-IPv4**.

![các luật inbound cho public sg](/images/create-vpc/sg/inbound-rules-for-public-sg.png)

4. Lăn chuột tới xuống cuối trang.
   - Các cài đặt khác, giữ nguyên theo mặc định.
   - Nháy chuột vào **Create security group**.

#### Tạo **_private-security-group_**

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Security groups**.
   - Nháy chuột vào **Create security group**.

![bắt đầu tạo private sg](/images/create-vpc/sg/start-create-sg-2.png)

2. Tại trang **Create security group**, trong phần **Basic details**.
   - Trong vùng **Security group name**, nhập _`private-security-group`_.
   - Trong vùng **Description**, nhập _`Security group for private instances`_.
   - Chọn **_my-vpc_**.

![cấu hình private sg](/images/create-vpc/sg/config-private-sg.png)

3. Tại trang **Inbound rules**, nháy chuột vào **Add rule**.
   - Chọn giao thức **SSH**.
   - Chọn nguồn là **Custom** và nhập _`10.10.1.0/24`_ (khối địa chỉ IPv4 của **_public-subnet_**).

![các luật inbound cho private sg](/images/create-vpc/sg/inbound-rules-for-private-sg.png)

4. Lăn chuột tới xuống cuối trang.
   - Các cài đặt khác, giữ nguyên theo mặc định.
   - Nháy chuột vào **Create security group**.
