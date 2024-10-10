+++
title = "Tạo service role cho dịch vụ CodePipeline"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++

#### Tạo service role cho dịch vụ CodePipeline
1. **CodePileline** cần phải có IAM roles để build docker, push image và tương tác với **EKS cluster** bằng command **kubectl**.

2. Hãy tải các file policy json, tạo các role **eks-CodePipelineServiceRole** và thêm inline policy từ terminal như sau:

```
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodePipelineServiceRole --assume-role-policy-document file://cpAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpPolicyDocument.json
aws iam put-role-policy --role-name eks-CodePipelineServiceRole --policy-name codepipeline-access --policy-document file://cpPolicyDocument.json

```

![00001-Create-CodePipeline-Service-Role](/images/4-Generate-Code-Pipeline/2-Create-CodePipeline-Service-Role/00001-Create-CodePipeline-Service-Role.png?width=90pc)

![00002-Create-CodePipeline-Service-Role](/images/4-Generate-Code-Pipeline/2-Create-CodePipeline-Service-Role/00002-Create-CodePipeline-Service-Role.png?width=90pc)
