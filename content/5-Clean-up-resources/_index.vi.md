+++
title = "Dọn dẹp tài nguyên"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Xóa stack bằng AWS CloudFormation console

1. Mở bảng điều khiển [AWS CloudFormation console](https://console.aws.amazon.com/cloudformation/)

2. Trong trang Stack của **AWS CloudFormation**, chọn Stack mà bạn muốn xóa

3. Chọn **Delete**

4. Chọn **Delete stack**

#### Delete Repository
1. Mở trang [Amazon ECR console](https://console.aws.amazon.com/ecr/repositories)

2. Trên thanh điều hướng, chọn **Region** chứa repository cần xóa

3. Chọn **Repository**

4. Trong trang Repository, chọn **Private**

5. Chọn Repository cần xóa và chọn **Delete**

6. Xác minh xóa **Repository** và chọn **Delete**

#### Delete EKSCluster
1. Mở trang [Amazon EKS console page](https://console.aws.amazon.com/eks/home#/clusters)

2. Chọn **cluster** cần xóa và chọn **Delete**

3. Xác minh xóa **cluster** và chọn **Delete**

#### Delete CloudShell Environment
1. Chọn **Region** chứa môi trường cần xóa

2. Trong giao diện **CloudShell**, chọn **Actions**

3. Chọn **Delete**

4. **Verify** environment deletion bằng cách nhập delete và chọn **delete**