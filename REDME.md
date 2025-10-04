# S3LambdaCloudUploader

This project outlines a **serverless media upload hub** built using **AWS Lambda, Amazon S3,** and **Amazon DynamoDB.** It enables users to upload media files through a web interface, storing the files in **S3** and their associated metadata in **DynamoDB.**


## ✅ Features

* **Serverless Backend**
Utilizes **AWS Lambda** for efficient, scalable backend logic without the need to manage servers.

* Object Storage
Employs **Amazon S3** for durable and highly available storage of media assets.

* Data Management
Uses **Amazon DynamoDB** for fast, flexible, and schema-less storage of media metadata.

* User-Friendly Interface
Provides a simple and intuitive **web form** for uploading media files.

# Project Architecture Diagram
![](/img/Serverless-Media-Upload-Hub-AWS-Lambda-with-S3-and-DynamoDB.png)

## 🧩 Project Walkthrough and Components

Here are the key aspects of the project, illustrated with screenshots:
### 1. 🖼️ Upload Interface
![](/img/photo_6271464727288417208_y.jpg)
A simple web form allows users to enter a name, caption, and select a file to upload.

### 2. 🔐 IAM Role Permissions
![](/img/Screenshot%20(23).png)
Shows the IAM role granted to the Lambda function, enabling access to **S3** and **DynamoDB** services.

### 3. 💻 Lambda Function Code
![](/img/Screenshot%20(24).png)

Displays the **Python code** used in the Lambda function, which handles:

* Uploading the media file to S3

* Writing metadata to DynamoDB
### 4. 🗃️ S3 Bucket Overview
![](/img/Screenshot%20(25).png)
The S3 bucket (lamdawithdynadb) configured to store uploaded media files.
### 5. 📄 DynamoDB Table Entries

The `reels` DynamoDB table displaying the metadata for uploaded items, including `id`, `caption`, `file_url`, and `name`.
### 6. ✅ Successful Upload Confirmation
![](/img/photo_6271694276110519607_y.jpg)
The confirmation message displayed on the web interface after a successful media upload, showing the stored details and file URL.

## 🚀 High-Level Deployment Steps
To set up this project:

1.Configure an Amazon S3 bucket

* Used to store uploaded media files.

2.Create a DynamoDB table

* Table name: reels (or as preferred)

* Stores metadata such as name, caption, file URL, and timestamp.

3.Set up an IAM role

* Grants the Lambda function permissions to interact with both S3 and DynamoDB.

4.Develop the AWS Lambda function

* Written in Python (or your language of choice).

* Handles receiving the upload, saving to S3, and logging metadata.

5.(Optional) Add a Lambda layer

* For managing external dependencies (e.g., boto3, uuid if customized).

6.Integrate with Amazon API Gateway

* Exposes the Lambda function as a REST endpoint for HTTP interaction.

7.Create a simple frontend interface

* A web form to upload files via the API Gateway endpoint.
