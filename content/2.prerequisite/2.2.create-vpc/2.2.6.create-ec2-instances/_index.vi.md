---
title: "Tạo các máy ảo EC2"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 2.2.6 </b> "
---

#### Tạo **_public-instance_**

1. Tại trang [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/).
   ![mở ec2](/images/create-ec2/choose-ec2.png)
   - Nháy chuột vào **Instances**.
   - Nháy chuột vào **Launch instances**.

![bắt đầu tạo máy ảo public](/images/create-ec2/start-create-ec2-1.png)

2. Tại trang **Laucnh an instance**, trong phần **Name and tags**.
   - Nhập _`public-instance`_.

![đặt tên cho máy ảo public](/images/create-ec2/public-instance.png)

3. Trong phần **Application and OS Images**.
   - Chọn **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.

![chọn os image](/images/create-ec2/ec2-os-image.png)

4. Tiếp theo, chúng ta sẽ chọn loại máy ảo và chọn cặp khóa để kết nối an toàn với các máy ảo.

- Trong phần **Instance Type**.
  - Chọn **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.
- Trong phần **Keypair**.
  - Chọn **_aws-keypair_**. Nếu không tồn tại khóa nào, vui lòng tham khảo hướng dẫn để [tạo một cặp khóa mới](https://000003.awsstudygroup.com/vi/4-createec2server/4.1-createec2/#:~:text=Th%E1%BB%B1c%20hi%E1%BB%87n%20ch%E1%BB%8Dn%20Instance%20type%20v%C3%A0%20Ch%E1%BB%8Dn%20Create%20new%20key%20pair).

![chọn loại máy ảo và cặp khóa](/images/create-ec2/choose-instance-type-keypair.png)

5. Tiếp theo, chúng ta sẽ cấu hình các cài đặt về mạng và bộ nhớ của **_public-instance_**.

- Trong phần **Network settings**.
  - Tại vùng **VPC**, chọn **_my-vpc_**.
  - Tại vùng **Subnet**, chọn **_public-subnet_**.
  - Tại vùng **Auto-assign public IP**, chọn **Enable**.
  - Tại vùng **Firewall**, chọn **Select existing security group** và chọn **_public-security-group_**.
- Trong phần **Configure storage**.
  - Chọn 1x **8** GiB **gp2** root volume.
- Nháy chuột vào **Laucnh instance**.

![khởi chạy máy ảo public](/images/create-ec2/launch-public-instance.png)

#### Tạo **_private-instance_**

1. Tại trang [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/).
   - Nháy chuột vào **Launch instances**.

![bắt đầu tạo máy ảo private](/images/create-ec2/start-create-ec2-2.png)

2. Tại trang **Laucnh an instance**, trong phần **Name and tags**.
   - Nhập _`private-instance`_.

![đặt tên cho máy ảo private](/images/create-ec2/private-instance.png)

3. Trong phần **Application and OS Images**.
   - Chọn **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.

![chọn os image](/images/create-ec2/ec2-os-image.png)

4. Tiếp theo, chúng ta sẽ chọn loại máy ảo và chọn cặp khóa để kết nối an toàn với các máy ảo.

- Trong phần **Instance Type**.
  - Chọn **Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type**.
- Trong phần **Keypair**.
  - Chọn **_aws-keypair_**.

![chọn loại máy ảo và cặp khóa](/images/create-ec2/choose-instance-type-keypair.png)

5. Tiếp theo, chúng ta sẽ cấu hình các cài đặt về mạng và bộ nhớ của **_private-instance_**.

- Trong phần **Network settings**.
  - Tại vùng **VPC**, chọn **_my-vpc_**.
  - Tại vùng **Subnet**, chọn **_private-subnet_**.
  - Tại vùng **Auto-assign public IP**, chọn **Disable**.
  - Tại vùng **Firewall**, chọn **Select existing security group** và chọn **_private-security-group_**.
- Trong phần **Configure storage**.
  - Chọn 1x **8** GiB **gp2** root volume.

![setting-private-instance](/images/create-ec2/setting-private-instance.png)

6. Nháy chuột vào phần **Advanced details**.
   - Tại vùng **Instance profile**, chọn **_ec2-access-s3_**.
   - Nháy chuột vào **Launch instance**.

![khởi chạy máy ảo private](/images/create-ec2/launch-private-instance.png)

Trong phần **Instances**, kiểm tra lại hai máy ảo công khai/riêng tư đã được tạo thành công và trạng thái của chúng là **Running**.

![tạo các máy ảo thành công](/images/create-ec2/create-ec2-instances-success.png)

7. Chọn **_private-instance_**.
   - Nháy chuột vào **Actions**.
   - Nháy chuột vào **Security**.
   - Nháy chuột vào **Modify IAM role**.

![bắt đầu kiểm tra quyền của máy ảo private](/images/create-ec2/start-check-private-instance-role.png)

IAM Role của **_private-instance_** là **_ec2-access-s3_**.

![check-private-instance-role](/images/create-ec2/check-private-instance-role-success.png)
