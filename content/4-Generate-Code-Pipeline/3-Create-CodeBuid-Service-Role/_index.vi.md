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

![00001-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00001-Create-CodeBuid-Service-Role.png?width=90pc)

![00002-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00002-Create-CodeBuid-Service-Role.png?width=90pc)


1. Chúng ta kiểm tra role đã tạo, ta thực hiện:
- Truy cập vào trang **AWS Console**

- Tìm **IAM**

- Chọn  **IAM**

![00003-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00003-Create-CodeBuid-Service-Role.png?width=90pc)

3. Trong giao diện **IAM**
- Chọn  **Role**
- Tìm   `eks-Code`
- Xem 2 Role vừa tạo

![00004-Create-CodeBuid-Service-Role](/images/4-Generate-Code-Pipeline/3-Create-CodeBuid-Service-Role/00004-Create-CodeBuid-Service-Role.png?width=90pc)


