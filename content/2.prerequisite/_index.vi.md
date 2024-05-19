---
title: "Chuẩn bị"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

Để thiết lập dự án, chúng ta cần thực hiện một số hoạt động chuẩn bị. Đầu tiên, chúng ta sẽ xây dựng VPC cùng với các máy ảo. Ngoài ra, chúng ta sẽ tạo các S3 Bucket và hàm Lambda. Hơn nữa, chúng ta cũng sẽ tạo các IAM role để cấp quyền cho hàm Lambda và máy ảo EC2, cho phép chúng truy cập vào các S3 Bucket và tương tác với AWS Polly.

{{% notice note %}}
Tất cả các dịch vụ và hoạt động trong dự án này đều nằm trong Bậc miễn phí của AWS.
{{% /notice %}}

### Nội dung

- [Tạo các IAM Role](2.1.create-iam-roles/)
- [Tạo VPC](2.2.create-vpc/)
- [Tạo các S3 Bucket](2.3.create-s3-buckets/)
- [Tạo hàm Lambda](2.4.create-lambda-function/)
