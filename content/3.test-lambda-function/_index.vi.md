---
title: "Kiểm thử hàm Lambda"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Trong bước này, chúng ta sẽ kiểm thử hàm Lambda để đảm bảo rằng nó thực hiện chính xác tác vụ chuyển văn bản thành giọng nói.

#### Tải file lên bucket **_input-bucket-for-polly_**

1. Đi tới trang [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).
   ![mở s3](/images/create-s3/choose-s3.png)
   - Nháy chuột vào **_input-bucket-for-polly_**.

![chọn bucket đầu vào](/images/create-s3/test-input-bucket.png)

2. Tại trang thông tin về bucket **_input-bucket-for-polly_**.
   - Nháy chuột vào **Upload**.

![bắt đầu tải file lên](/images/create-s3/test-upload-input-bucket.png)

2. Tại trang **Upload**.
   - Nháy chuột vào **Add files**.
   - Từ máy tính của bạn, chọn một file văn bản mà bạn muốn chuyển thành giọng nói. Đây là một file văn bản mẫu [input.txt](attachments/input.txt).
   - Trong phần **Files and folders**, chọn file mới được thêm vào.
   - Nháy chuột vào **Upload**.

![thêm file đầu vào](/images/create-s3/add-file-input.png)

File **_input.txt_** đã được tải lên bucket **_input-bucket-for-polly_** thành công.

![thêm file thành công](/images/create-s3/add-file-success.png)

#### Kiểm tra file đầu ra trong bucket **_output-bucket-from-polly_**

1. Trở lại trang **Buckets**.
   - Nháy chuột vào **_output-bucket-from-polly_**.

![chọn bucket đầu ra](/images/create-s3/test-output-bucket.png)

Tại trang thông tin về bucket **_output-bucket-from-polly_**, đã có một file mới tên là **_input.mp3_**. Nó chứng tỏ rằng hàm Lambda đã hoạt động thành công.

![kiểm tra bucket đầu ra thành công](/images/create-s3/test-output-success.png)
