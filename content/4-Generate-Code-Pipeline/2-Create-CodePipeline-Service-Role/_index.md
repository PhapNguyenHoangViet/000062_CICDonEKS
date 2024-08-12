+++
title = "Create service role for CodePipeline service"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2. </b>"
+++

#### Create service role for CodePipeline service
1. **CodePileline** requires IAM roles to **build docker**, push image and interact with **EKS cluster** using **kubectl** command.

2. **Download** the json policy files, create role **eks-CodePipelineServiceRole** and add inline policy from terminal as follows:

```
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodePipelineServiceRole --assume-role-policy-document file://cpAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codepipeline/cpPolicyDocument.json
aws iam put-role-policy --role-name eks-CodePipelineServiceRole --policy-name codepipeline-access --policy-document file://cpPolicyDocument.json

```

![00001-Create-CodePipeline-Service-Role](/images/4-Generate-Code-Pipeline/2-Create-CodePipeline-Service-Role/00001-Create-CodePipeline-Service-Role.png?width=90pc)

![00002-Create-CodePipeline-Service-Role](/images/4-Generate-Code-Pipeline/2-Create-CodePipeline-Service-Role/00002-Create-CodePipeline-Service-Role.png?width=90pc)
