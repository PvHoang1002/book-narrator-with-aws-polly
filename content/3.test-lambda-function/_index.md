---
title: "Test Lambda fucntion"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

In this step, we are going to test the Lambda function to ensure that it performs the text-to-speech task correctly.

#### Upload file to bucket **_input-bucket-for-polly_**

1. Go to [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/).
   ![choose-s3](/images/create-s3/choose-s3.png)
   - Click **_input-bucket-for-polly_**.

![select-input-bucket](/images/create-s3/test-input-bucket.png)

2. At the **_input-bucket-for-polly_** info page.
   - Click **Upload**.

![start-upload-file](/images/create-s3/test-upload-input-bucket.png)

2. At the **Upload** page.
   - Click **Add files**.
   - From your computer, select a text file that you want to convert into speech. Here is a sample text file [input.txt](attachments/input.txt).
   - In the **Files and folders** section, select the newly added file.
   - Click **Upload**.

![add-file-input](/images/create-s3/add-file-input.png)

The **_input.txt_** file was uploaded to **_input-bucket-for-polly_** successfully.

![add-file-success](/images/create-s3/add-file-success.png)

#### Check output file in bucket **_output-bucket-from-polly_**

1. Back to the **Buckets** page.
   - Click **_output-bucket-from-polly_**.

![select-output-bucket](/images/create-s3/test-output-bucket.png)

At the **_output-bucket-from-polly_** info page, there is a new file named **_input.mp3_**. It proves that the Lambda function worked successfully.

![test-output-bucket-success](/images/create-s3/test-output-success.png)
