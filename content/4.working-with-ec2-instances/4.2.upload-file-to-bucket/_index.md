---
title: "Upload file to S3 bucket"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

#### Upload file **_hello.txt_** to **_input-bucket-for-polly_**

1. We are now working on **_private-instance_**.
   - Enter _`nano hello.txt`_ command and press **Enter**.
   - Copy the content of the text file we just used in [**section 3**](3.test-lambda-function/).
   - Paste it into the **MobaXterm** screen.
   - Press the key combination Ctrl + S to save the file content and Ctrl + X to exit the nano editor.

![nano-hello-file](/images/connect-ec2/nano-hello-file.png)

2. To upload file **_hello.txt_** to **_input-bucket-for-polly_**.
   - Enter _`aws s3 cp hello.txt s3://input-bucket-for-polly --endpoint-url https://s3.ap-southeast-1.amazonaws.com`_ command and press **Enter**.

There will be a message **_upload: ./hello.txt to s3://input-bucket-for-polly_** appear right after we execute the command. It means the upload action was performed successfully.

![upload-hello-to-s3](/images/connect-ec2/upload-hello-to-s3.png)

3. Enter _`aws s3 ls hello.txt s3://output-bucket-from-polly --endpoint-url https://s3.ap-southeast-1.amazonaws.com`_ command and press **Enter**.

This command will list all files contained in **_output-bucket-from-polly_** and we can see there is a file named **_hello.mp3_**. It means the Lambda function was executed successfully.

![check-hello-output](/images/connect-ec2/check-hello-output.png)

4. Go to [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).
   - Select **_output-bucket-from-polly_**.

In the **_output-bucket-from-polly_** info page, we can see the **_hello.mp3_** file.

![check-output-bucket-success](/images/create-s3/check-output-bucket-success.png)
