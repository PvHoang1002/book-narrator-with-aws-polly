---
title: "Tạo các Route Table"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.2.4 </b> "
---

#### Tạo public route table

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Route tables**.
   - Nháy chuột vào **Create route table**.

![bắt đầu tạo public rtb](/images/create-vpc/rtb/start-create-rtb-1.png)

2. Tại trang **Create route table**.
   - Trong cùng **Name**, nhập _`public-route-table`_.
   - Trong phần **VPC**, chọn **_my-vpc_**.
   - Nháy chuột vào **Create route table**.

![tạo public rtb](/images/create-vpc/rtb/create-public-rtb.png)

3. Tại trang **_public-route-table_**.
   - Chọn tab **Subnet associations**.
   - Nháy chuột vào **Edit subnet associations**.

![bắt đầu liên kết public rtb](/images/create-vpc/rtb/start-associate-1.png)

4. Tại trang **Edit subnet associations**.
   - Chọn **_public-subnet_**.
   - Nháy chuột vào **Save associations**.

![lưu liên kết public rtb](/images/create-vpc/rtb/save-associate-1.png)

5. Tại trang **_public-route-table_**.
   - Chọn tab **Routes**.
   - Nháy chuột vào **Edit routes**.

![bắt đầu chỉnh sửa tuyến đường](/images/create-vpc/rtb/start-edit-routes-1.png)

6. Tại trang **Edit routes**.
   - Nháy chuột vào **Add route**.
   - Trong vùng **Destination**, nhập _`0.0.0.0/0`_.
   - Trong phần **Target**, chọn **Internet Gateway**, sau đó chọn **_my-internet-gateway_**.
   - Nháy chuột vào **Save changes**.

![lưu chỉnh sửa tuyến đường](/images/create-vpc/rtb/save-edit-routes-1.png)

Các tuyến đường của **_public-route-table_** đã được chỉnh sửa thành công.

![chỉnh sửa tuyến đường thành công](/images/create-vpc/rtb/edit-routes-success-1.png)

#### Tạo **_private-route-table_**

1. Tại trang [Amazon Virtual Private Cloud (VPC)](https://aws.amazon.com/vpc/).
   - Nháy chuột vào **Route tables**.
   - Nháy chuột vào **Create route table**.

![bắt đầu tạo private rtb](/images/create-vpc/rtb/start-create-rtb-2.png)

2. Tại trang **Create route table**.
   - Trong vùng **Name**, nhập _`private-route-table`_.
   - Trong phần **VPC**, chọn **_my-vpc_**.
   - Nháy chuột vào **Create route table**.

![tạo private rtb](/images/create-vpc/rtb/create-private-rtb.png)

3. Tại trang **_private-route-table_**.
   - Chọn tab **Subnet associations**.
   - Nháy chuột vào **Edit subnet associations**.

![bắt đầu liên kết private rtb](/images/create-vpc/rtb/start-associate-2.png)

4. Tại trang **Edit subnet associations**.
   - Chọn **_private-subnet_**.
   - Nháy chuột vào **Save associations**.

![save-associate-private-rtb](/images/create-vpc/rtb/save-associate-2.png)

Trong phần **Route tables**, kiểm tra lại hai route table vừa được tạo thành công và liên kết.

![tạo các rtb thành công](/images/create-vpc/rtb/create-rtbs-success.png)
