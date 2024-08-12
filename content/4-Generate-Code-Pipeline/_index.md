+++
title = "Create CI/CD"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

### Overview
- In the next steps, we will create a Deployment Pipeline using AWS CodePipeline and integrate with the third party tool GitHub. When we change the code on GitHub, our Pipeline will be activated and deploy the new version of the application to the web application we already run on the EKS Cluster.

![architecture](/images/4-Generate-Code-Pipeline/architecture.png?width=90pc)

### Content
1. [Create S3 bucket](1-Create-S3-bucket)
2. [Create CodePipeline Service Role](2-Create-CodePipeline-Service-Role)
3. [Create Code Buid Service Role](3-Create-CodeBuid-Service-Role)
4. [Configure RBAC](4-Configure-RBAC)
5. [Forke source code](5-Fork-Source-Code)
6. [Generate CodePipeline](6-Generate-CodePipeline)
7. [CI/CD Check](7-CICD-Check)