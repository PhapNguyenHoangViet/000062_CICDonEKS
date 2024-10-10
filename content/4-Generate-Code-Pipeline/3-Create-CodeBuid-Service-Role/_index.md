+++
title = "Create service role for CodeBuild service"
date = 2024
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++

#### Create service role for CodeBuild service
1. CodeBuild requires IAM roles to build docker, push images, and interact with the EKS cluster using the kubectl command.
- Let’s create role eks-CodePipelineServiceRole and add inline policy from terminal CloudShell

```
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codebuild/cbAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodeBuildServiceRole --assume-role-policy-document file://cbAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codebuild/cbPolicyDocument.json
aws iam put-role-policy --role-name eks-CodeBuildServiceRole --policy-name codebuild-access --policy-document file://cbPolicyDocument.json
```

![00001-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00001-Create-CodeBuid-Service-Role.png?width=90pc)

![00002-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00002-Create-CodeBuid-Service-Role.png?width=90pc)


2. We check the created role, we do:
- Go to the **AWS Console**

- Find **IAM**

- Select **IAM**

![00003-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00003-Create-CodeBuid-Service-Role.png?width=90pc)

![00001-Create-CodePipeline-Service-Role](/images/4-Generate-Code-Pipeline/2-Create-CodePipeline-Service-Role/00001-Create-CodePipeline-Service-Role.png?width=90pc)

3. In the **IAM** interface
- Select **Role**
- Find `eks-Code`
- View the 2 Roles just created

![00004-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00004-Create-CodeBuid-Service-Role.png?width=90pc)


