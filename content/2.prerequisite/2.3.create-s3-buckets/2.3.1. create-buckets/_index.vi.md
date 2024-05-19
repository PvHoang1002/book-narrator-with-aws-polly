---
title: "Tạo các S3 Bucket"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 2.3.1 </b> "
---

Trong bước này, chúng ta sẽ tiến hành tạo hai bucket: **_input-bucket-for-polly_** và **_output-bucket-from-polly_**. Trong khi bucket đầu vào được dùng để lưu trữ tệp văn bản được tải lên từ máy ảo EC2, thì bucket đầu ra lại chứa tệp âm thanh do AWS Polly tạo.

#### Tạo **_input-bucket-for-polly_**

1. Đi tới trang [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).
   ![mở s3](/images/create-s3/choose-s3.png)
   - Nháy chuột vào **Create bucket**.

![bắt đầu tạo bucket đầu vào](/images/create-s3/start-create-bucket-1.png)

2. Tại trang **Create bucket**, trong phần **General configuration**.
   - Tại vùng **AWS Region**, chọn **Asia Pacific (Singapore) ap-southeast-1**.
   - Trong vùng **Bucket name**, nhập _`input-bucket-for-polly`_.
   - Các cài đặt khác, giữ nguyên theo mặc định.
   - Lăn chuột tới cuối trang và nháy chuột vào **Create bucket**.

![bucket đầu vào](/images/create-s3/input-bucket.png)

![tạo bucket](/images/create-s3/create-bucket.png)

#### Tạo **_out-bucket-from-polly_**

1. Tại trang [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).
   - Nháy chuột vào **Create bucket**.

![bắt đầu tạo bucket đầu ra](/images/create-s3/start-create-bucket-2.png)

2. Tại trang **Create bucket**, trong phần **General configuration**.
   - Tại vùng **AWS Region**, chọn **Asia Pacific (Singapore) ap-southeast-1**.
   - Trong vùng **Bucket name**, nhập _`output-bucket-from-polly`_.
   - Các cài đặt khác, giữ nguyên theo mặc định.
   - Lăn chuột tới cuối trang và nháy chuột vào **Create bucket**.

![bucket đầu ra](/images/create-s3/output-bucket.png)

![tạo bucket](/images/create-s3/create-bucket.png)

Trong phần **General purpose buckets**, kiểm tra lại hai bucket vừa tạo thành công.

![tạo các bucket thành công](/images/create-s3/create-buckets-success.png)
