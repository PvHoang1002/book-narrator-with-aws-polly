---
title: "Tạo VPC"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2.2 </b> "
---

Trong phần này, chúng ta sẽ tạo một VPC với 2 mạng con public/private. Tại mỗi mạng con, chúng ta cũng sẽ cài đặt thêm một máy ảo EC2.

Tổng quan về kiến trúc sau khi hoàn thành bước này sẽ như sau:

![mô hình vpc](/images/diagrams/vpc-diagram.png)

### Nội dung

- [Tạo VPC](2.2.1.create-vpc/)
- [Tạo các Subnet](2.2.2.create-subnets/)
- [Tạo Internet Gateway](2.2.3.create-igw/)
- [Tạo các Route Table](2.2.4.create-rtbs/)
- [Tạo các Security Group](2.2.5.create-sec-groups/)
- [Tạo các máy ảo EC2](2.2.6.create-ec2-instances/)
