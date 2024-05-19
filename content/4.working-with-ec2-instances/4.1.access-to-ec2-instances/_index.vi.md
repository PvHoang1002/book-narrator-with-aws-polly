---
title: "Truy cập vào các máy ảo"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

Trong bước này, chúng ta sẽ tiến hành truy cập vào máy ảo **_public-instance_** đầu tiên. Máy ảo **_public-instance_** sẽ hoạt động như một máy chủ Bastion để giúp chúng ta truy cập vào máy ảo **_private-instance_**.

{{% notice note %}}
Máy chủ Bastion là một máy tính có mục đích đặc biệt để quản lý các máy ảo hoặc cơ sở dữ liệu riêng tư nằm trong private subnet (mà không cần phải xử lý qua Internet). Máy chủ Bastion được đặt trong public subnet và hoạt động như một "cổng kết nối" giữa thế giới bên ngoài và private subnet.
{{% /notice %}}

#### Truy cập vào máy ảo **_public-instance_**

1. Đi tới trang [Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/).

   - Nháy chuột vào **Instances**.
   - Chọn máy ảo **_public-instance_** và copy địa chỉ IP public của nó.

2. Mở **MobaXterm** và tạo một phiên **SSH**.
   - Trong vùng **Remote host**, nhập địa chỉ IP public vừa copy của máy ảo **_public-instance_**.
   - Trong vùng **Specify username**, nhập _`ec2-user`_.
   - Chọn **Use private key** và chọn file **_aws-keypair.pem_** lưu trên máy tính của bạn.
   - Các cài đặt khác, giữ nguyên theo mặc định. Sau đó nháy chuột vào **OK**.

![kết nối với máy ảo public](/images/connect-ec2/connect-public-instance.png)

3. Kết nối đến máy ảo **_public-instance_** đã được thiết lập thành công.
   - Nhập lệnh _`pwd`_ và nhấn phím **Enter** để đảm bảo thư mục làm việc hiện tại là **_/home/ec2-user/_**.
   - Nhập lệnh _`sudo su`_ và nhấn phím **Enter** (Câu lệnh này có thể không cần thực hiện).
   - Nhập lệnh _`nano aws-keypair.pem`_ và nhấn phím **Enter**.

![viết file keypair](/images/connect-ec2/nano-keypair-file.png)

4. Giữ cửa số **MobaXterm** mở.
   - Di chuyển tới nơi lưu trữ file **_aws-keypair.pem_** trên máy tính của bạn và mở nó.
   - Copy khóa riêng tư và paste nó vòa màn hình **MobaXterm**.
   - Nhấn tổ hợp phím Ctrl + S để lưu nội dung file và Ctrl + X để thoát khỏi trình soạn thảo nano.

![copy file keypair](/images/connect-ec2/copy-keypair.png)

#### Truy cập vào máy ảo **_private-instance_**

1. Tại trang **Instances** trên **AWS Console**, copy địa chỉ IP private của máy ảo **_private-instance_**.
   - Trên màn hình **MobaXterm**, nhập lệnh _`chmod 400 aws-keypair.pem`_ và nhấn phím **Enter**.
   - Nhập lệnh _`ssh -i "aws-keypair.pem" ec2-user@private-ip`_ và nhấn phím **Enter** (Hãy nhớ thay cụm _private-ip_ bằng địa chỉ IP private của máy ảo **_private-instance_**).

Kết nối tới máy ảo **_private-instance_** sẽ được thiết lập thành công. Giữ cửa sổ **MobaXterm** mở, chúng ta sẽ tiến tới bước tiếp theo.

![kết nối tới máy ảo private](/images/connect-ec2/connect-private-instance.png)
