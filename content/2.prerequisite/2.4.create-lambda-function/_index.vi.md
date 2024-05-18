---
title: "Create Lambda Function"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 2.4 </b> "
---

#### Create function **_text-to-speech-converter_**

Now, we are going to create a Lambda function to listen to events from the newly created **_input-bucket-for-polly_** and from there perform the necessary tasks with AWS Polly.

1. Go to [AWS Lambda](https://aws.amazon.com/lambda/).
   ![choose-lambda](/images/create-lambda/choose-lambda.png)
   - Click **Create a function**.

![start-create-lambda-func](/images/create-lambda/start-create-lambda-func.png)

2. At the **Create function** page.
   - On the top right of the screen, change the **AWS Region** to **Asia Pacific (Singapore) ap-southeast-1**.
   - Then, select **Author from scratch**.
   - In the **Basic information** section, enter _`text-to-speech-converter`_ into the **Function name** field.
   - In the **Runtime** field, select **Python 3.12**.

![config-func](/images/create-lambda/config-func.png)

3. In the **Permissions** section.
   - Click **Change default execution role**.
   - In the **Exection role** select **Use an existing role**.
   - Then, select **_lambda-access-s3-polly_** role.
   - Click **Create function**.

![create-lambda-func](/images/create-lambda/create-func.png)

4. After the Lambda fucntion was successfully created.
   - Click **Configuration** tab.
   - On the left side panel, select **General configuration**.
   - Click **Edit** in the **General configuration** section.

![edit-config](/images/create-lambda/edit-config.png)

5. At the **Edit basic settings** page, look for **Timeout** section.
   - Change the timeout to **3** minutes.
   - Then, click **Save**.

![save-edit-timeout](/images/create-lambda/save-edit-timeout.png)

6. In the **Function overview** section, click **Add trigger**.

![add-trigger](/images/create-lambda/add-trigger.png)

7. At the **Add trigger** page, in the **Trigger configuration** section.
   - Select **S3** service as a source.
   - Select bucket **_input-bucket-for-polly_**.
   - In the **Event types** field, select **All object create events**.

![edit-trigger](/images/create-lambda/edit-trigger.png)

8. Scrool down and select the acknowledgement.
   - Then, click **Add**.

![create-trigger](/images/create-lambda/create-trigger.png)

{{% notice warning %}}
Using the same S3 bucket for both input and output can cause recursive invocations, increased Lambda usage, and increased costs.
{{% /notice %}}

We will see a message that says the trigger was successfully added to the function.

![add-trigger-success](/images/create-lambda/add-trigger-success.png)

9. Next, we will embed the code into our Lambda function.
   - Navigate to code section by clicking **Code** tab.

![start-edit-code](/images/create-lambda/start-edit-code.png)

10. Replace the initial code by the code provided below. After that, click **Deploy** to save code.

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

![edit-and-deploy-code](/images/create-lambda/edit-and-deploy-code.png)
