+++
title = "Tạo S3 bucket"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++

#### Tạo S3 bucket

1. Tạo **Bucket** này cho **CodeBuild** lưu artifact (tạo ra tập tin **build.json** sau mỗi lần build). Chúng ta sử dụng lệnh sau:

```
ACCOUNT_ID=$(aws sts get-caller-identity | jq -r '.Account')
aws s3 mb s3://eks-${ACCOUNT_ID}-codepipeline-artifacts
```
![00001-Create-S3-bucket](/images/4-Generate-Code-Pipeline/1-Create-S3-bucket/00001-Create-S3-bucket.png?width=90pc)

2. Trong giao diện [AWS Console](https://aws.amazon.com/console/)
- Tìm  **S3**
- Chọn  **S3**

![00002-Create-S3-bucket](/images/4-Generate-Code-Pipeline/1-Create-S3-bucket/00002-Create-S3-bucket.png?width=90pc)

3. Trong giao diện **S3**
- Chọn  **S3**
- Chọn  **Bucket**
- Xem **bucket artifact** đã tạo

![00003-Create-S3-bucket](/images/4-Generate-Code-Pipeline/1-Create-S3-bucket/00003-Create-S3-bucket.png?width=90pc)