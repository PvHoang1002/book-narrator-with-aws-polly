---
title: "Tạo hàm Lambda"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

#### Tạo hàm **_text-to-speech-converter_**

Bây giờ, chúng ta sẽ tạo một hàm Lambda để lắng nghe các sự kiện từ bucket mới tạo **_input-bucket-for-polly_** và từ đó thực hiện các nhiệm vụ cần thiết với **AWS Polly**.

1. Đi tới trang [AWS Lambda](https://aws.amazon.com/lambda/).
   ![mở lambda](/images/create-lambda/choose-lambda.png)
   - Nháy chuột vào **Create a function**.

![bắt đầu tạo một hàm lambda](/images/create-lambda/start-create-lambda-func.png)

2. Tại trang **Create function**.
   - Tại góc trên bên phải của màn hình, thay đổi **AWS Region** thành **Asia Pacific (Singapore) ap-southeast-1**.
   - Sau đó, chọn **Author from scratch**.
   - Trong phần **Basic information**, nhập _`text-to-speech-converter`_ vào vùng **Function name**.
   - Tại vùng **Runtime**, chọn **Python 3.12**.

![cấu hình hàm](/images/create-lambda/config-func.png)

3. Trong phần **Permissions**.
   - Nháy chuột vào **Change default execution role**.
   - Trong phần **Exection role**, chọn **Use an existing role**.
   - Sau đó, chọn role **_lambda-access-s3-polly_**.
   - Nháy chuột vào **Create function**.

![tạo hàm lambda](/images/create-lambda/create-func.png)

4. Sau khi hàm Lambda được tạo thành công.
   - Nháy chuột vào tab **Configuration**.
   - Trên bảng điều khiển bên trái, chọn **General configuration**.
   - Trên bảng điều khiển bên trái **Edit** trong phần **General configuration**.

![chỉnh sửa cấu hình](/images/create-lambda/edit-config.png)

5. Tại trang **Edit basic settings**, tìm tới phần **Timeout**.
   - Thay đổi thời gian timeout thành **3** phút.
   - Sau đó, nháy chuột vào **Save**.

![lưu chỉnh sửa timeout](/images/create-lambda/save-edit-timeout.png)

6. Trong phần **Function overview**, nháy chuột vào **Add trigger**.

![thêm trigger](/images/create-lambda/add-trigger.png)

7. Tại trang **Add trigger**, trong phần **Trigger configuration**.
   - Chọn dịch vụ **S3** với tư cách là nguồn.
   - Chọn bucket **_input-bucket-for-polly_**.
   - Tại vùng **Event types**, chọn **All object create events**.

![chỉnh sửa trigger](/images/create-lambda/edit-trigger.png)

8. Kéo chuột xuống và chọn xác nhận.
   - Sau đó, nháy chuột vào **Add**.

![tạo trigger](/images/create-lambda/create-trigger.png)

{{% notice warning %}}
Việc sử dụng cùng một bucket S3 cho cả đầu vào và đầu ra có thể gây ra các lệnh gọi đệ quy, tăng mức sử dụng Lambda và tăng chi phí.
{{% /notice %}}

Chúng ta sẽ thấy thông báo cho biết rằng trigger đã được thêm thành công vào hàm.

![thêm trigger thành công](/images/create-lambda/add-trigger-success.png)

9. Tiếp theo, chúng ta sẽ nhúng code vào trong hàm Lambda.
   - Di chuyển tới phần code bằng cách nháy chuột vào tab **Code**.

![bắt đầu chỉnh sửa code](/images/create-lambda/start-edit-code.png)

10. Thay thế code ban đầu bằng code được cung cấp bên dưới. Sau đó, nháy chuột vào **Deploy** để lưu code.

```
import boto3

def lambda_handler(event, context): # Get the S3 bucket and key from the event
s3_bucket = event['Records'][0]['s3']['bucket']['name']
s3_key = event['Records'][0]['s3']['object']['key']

    # Check if the uploaded file is a .txt file
    if s3_key.endswith('.txt'):
        # Create clients for Polly and S3
        polly_client = boto3.client('polly')
        s3_client = boto3.client('s3')

        # Read the content of the uploaded .txt file from S3
        response = s3_client.get_object(Bucket=s3_bucket, Key=s3_key)
        text_content = response['Body'].read().decode('utf-8')

        # Text-to-speech converter using Polly
        response = polly_client.synthesize_speech(
            Text=text_content,
            OutputFormat='mp3',
            VoiceId='Joanna',  # Joanna is one of Polly's voices
            Engine='standard',
            LanguageCode='en-US'
        )

        # Specify the bucket where the output.mp3 file will be stored
        output_bucket = 'output-bucket-from-polly'

        # Specify the key for the output.mp3 file (use the same key as the input .txt file)
        mp3_key = s3_key[:-4] + '.mp3'  # Change the file extension to .mp3

        # Stored audio file in specified S3 bucket
        s3_client.put_object(
            Bucket=output_bucket,
            Key=mp3_key,
            Body=response['AudioStream'].read()
        )

        return {
            'statusCode': 200,
            'body': f'File {s3_key} has been converted to {mp3_key} and stored in {output_bucket}'
        }
    else:
        return {
            'statusCode': 200,
            'body': f'File {s3_key} is not a .txt file. Skipping conversion.'
        }

```

![chỉnh sửa và deploy code](/images/create-lambda/edit-and-deploy-code.png)
