+++
title = "Create CI/CD"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

### Tổng quan
- Trong các bước tiếp theo, chúng ta sẽ tạo một Deployment Pipeline bằng AWS CodePipeline và tích hợp với công cụ third party là GitHub. Khi chúng ta thay đổi code trên GitHub, Pipeline của chúng ta sẽ được kích hoạt và deploy phiên bản ứng dụng mới lên ứng dụng web chúng ta đã chạy trên EKS Cluster.

![architecture](../images/4-Generate-Code-Pipeline/architecture.png?width=90pc)

### Nội dung
1. [Tạo S3 bucket](1-Create-S3-bucket)
2. [Tạo CodePipeline Service Role](2-Create-CodePipeline-Service-Role)
3. [Tạo Code Buid Service Role](3-Create-CodeBuid-Service-Role)
4. [Cấu hình RBAC](4-Configure-RBAC)
5. [Forke source code](5-Fork-Source-Code)
6. [Tạo CodePipeline](6-Generate-CodePipeline)
7. [Kiểm tra CI/CD](7-CICD-Check)