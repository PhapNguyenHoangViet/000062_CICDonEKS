+++
title = "Create S3 bucket"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1. </b>"
+++

#### Create S3 bucket

1. Create this **Bucket** for **CodeBuild** to save artifact (generate build.json file after each build). We use the following command:

```
ACCOUNT_ID=$(aws sts get-caller-identity | jq -r '.Account')
aws s3 mb s3://eks-${ACCOUNT_ID}-codepipeline-artifacts
```
![00001-Create-S3-bucket](/images/4-Generate-Code-Pipeline/1-Create-S3-bucket/00001-Create-S3-bucket.png?width=90pc)

2. In the [AWS Console](https://aws.amazon.com/console/)
- Find **S3**
- Select **S3**

![00002-Create-S3-bucket](/images/4-Generate-Code-Pipeline/1-Create-S3-bucket/00002-Create-S3-bucket.png?width=90pc)

3. In the **S3** interface
- Select **S3**
- Select **Bucket**
- View created **bucket artifact**

![00003-Create-S3-bucket](/images/4-Generate-Code-Pipeline/1-Create-S3-bucket/00003-Create-S3-bucket.png?width=90pc)