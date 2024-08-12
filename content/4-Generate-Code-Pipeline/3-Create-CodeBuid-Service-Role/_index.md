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

![00001-create-codebuid-service-role](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00001-create-codebuid-service-role.png?width=90pc)

![00002-create-codebuid-service-role](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00002-create-codebuid-service-role.png?width=90pc)


2. We check the created role, we do:
- Go to the **AWS Console**

- Find **IAM**

- Select **IAM**

![00003-create-codebuid-service-role](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00003-create-codebuid-service-role.png?width=90pc)

3. In the **IAM** interface
- Select **Role**
- Find `eks-Code`
- View the 2 Roles just created

![00004-create-codebuid-service-role](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00004-create-codebuid-service-role.png?width=90pc)


