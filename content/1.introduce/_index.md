---
title: "Introduction"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

**The Creating a Book Narrator** project leverages **AWS Polly**, a powerful cloud service that transforms text into natural-sounding speech. The goal is to provide an accessible and engaging auditory experience for readers by converting written content into high-quality audio.

### What is AWS Polly?

AWS Polly is an Amazon Web Services (AWS) service that offers text-to-speech (TTS) capabilities. It allows developers to generate lifelike speech from plain text using a variety of customizable voices. Polly supports multiple languages and provides a seamless way to integrate speech synthesis into applications, websites, and other platforms.

### How the program works?

![project-diagram](/images/diagrams/project-diagram.png)

- **User Uploads Text Content:**

  - Users upload their desired book or document in text format to an Amazon S3 bucket.
  - The S3 bucket acts as a storage location for the input text files.

- **Lambda Function Activation:**

  - When a new text file is uploaded, an AWS Lambda function is triggered.
  - The Lambda function processes the uploaded text and initiates the conversion process.

- **Text-to-Audio Conversion:**

  - The Lambda function interacts with AWS Polly to convert the text into high-quality audio.
  - Polly uses advanced algorithms to generate natural-sounding speech with customizable voice characteristics.

- **Saving the Audio File:**

  - The resulting audio file is created by Polly.
  - The Lambda function saves the audio file back to a different S3 bucket designated for audio storage.

- **Accessing the Narrated Content:**
  - Users can access the narrated content by retrieving the audio file from the designated S3 bucket.
  - They can listen to the book or document using any compatible audio player.
