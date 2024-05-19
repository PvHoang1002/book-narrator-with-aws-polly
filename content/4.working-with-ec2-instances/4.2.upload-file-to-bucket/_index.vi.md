---
title: "Tải file lên S3 bucket"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

#### Tải file **_hello.txt_** lên **_input-bucket-for-polly_**

1. Hiện tại chúng ta đang làm việc với máy ảo **_private-instance_**.
   - Nhập lệnh _`nano hello.txt`_ và nhấn phím **Enter**.
   - Copy nội dung của file văn bản mà chúng ta vừa sử dụng ở [**mục 3**](3.test-lambda-function/).
   - Paste nó vào màn hình của **MobaXterm**.
   - Nhấn tổ hợp phím Ctrl + S để lưu nội dung file và Ctrl + X để thoát khỏi trình soạn thảo nano.

![viết file hello](/images/connect-ec2/nano-hello-file.png)

2. Để tải file **_hello.txt_** lên **_input-bucket-for-polly_**.
   - Nhập lệnh _`aws s3 cp hello.txt s3://input-bucket-for-polly --endpoint-url https://s3.ap-southeast-1.amazonaws.com`_ và nhấn phím **Enter**.

Sẽ có một thông báo: **_upload: ./hello.txt to s3://input-bucket-for-polly_** xuất hiện sau khi chúng ta thực thi câu lệnh. Nó có nghĩa là việc tải file lên đã diễn ra thành công.

![tải file hello lên s3 bucket](/images/connect-ec2/upload-hello-to-s3.png)

3. Nhập lệnh _`aws s3 ls hello.txt s3://output-bucket-from-polly --endpoint-url https://s3.ap-southeast-1.amazonaws.com`_ và nhấn phím **Enter**.

Câu lệnh này sẽ liệt kê tất cả những file có trong bucket **_output-bucket-from-polly_** và chúng ta có thể thấy có một file tên là **_hello.mp3_**. Điều đó có nghĩa là hàm Lambda đã được thực thi thành công.

![kiểm tra đầu ra file hello](/images/connect-ec2/check-hello-output.png)

4. Đi tới trang [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).
   - Chọn bucket **_output-bucket-from-polly_**.

Trong trang thông tin về bucket **_output-bucket-from-polly_**, chúng ta sẽ thấy file **_hello.mp3_**.

![kiểm tra bucket đầu ra thành công](/images/create-s3/check-output-bucket-success.png)
