+++
title = "Tạo service role cho dịch vụ CodeBuild"
date = 2024
weight = 3
chapter = false
pre = "<b>4.3. </b>"
+++

#### Tạo service role cho dịch vụ CodeBuild
1. CodeBuild cần phải có IAM roles để build docker, push image và tương tác với EKS cluster bằng command kubectl.
- Hãy tạo các role eks-CodePipelineServiceRole và thêm inline policy từ terminal CloudShell

```
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codebuild/cbAssumeRolePolicyDocument.json
aws iam create-role --role-name eks-CodeBuildServiceRole --assume-role-policy-document file://cbAssumeRolePolicyDocument.json
wget https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/codebuild/cbPolicyDocument.json
aws iam put-role-policy --role-name eks-CodeBuildServiceRole --policy-name codebuild-access --policy-document file://cbPolicyDocument.json
```

![00001-create-codebuid-service-role](/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00001-create-codebuid-service-role.png?width=90pc)

![00002-create-codebuid-service-role](/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00002-create-codebuid-service-role.png?width=90pc)


1. Chúng ta kiểm tra role đã tạo, ta thực hiện:
- Truy cập vào trang **AWS Console**

- Tìm **IAM**

- Chọn  **IAM**

![00003-create-codebuid-service-role](/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00003-create-codebuid-service-role.png?width=90pc)

3. Trong giao diện **IAM**
- Chọn  **Role**
- Tìm   `eks-Code`
- Xem 2 Role vừa tạo

![00004-create-codebuid-service-role](/images/4-Generate-Code-Pipeline/3-create-codebuid-service-role/00004-create-codebuid-service-role.png?width=90pc)


