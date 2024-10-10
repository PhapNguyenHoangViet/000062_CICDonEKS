+++
title = "Kiểm tra EKS Cluster"
date = 2024
weight = 2
chapter = false
pre = "<b>3.2. </b>"
+++

#### Kiểm tra EKS Cluster
1. Trong giao diện [AWS Console](https://aws.amazon.com/console/)
- Tìm **CloudFormation**
- Chọn  **CloudFormation**

![00001-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00001-Check-EKS-Cluster.png?width=90pc)

2. Trong giao diện **CloudFormation**
- Chọn  **Stack**
- Xem các stack đã tạo

![00002-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00002-Check-EKS-Cluster.png?width=90pc)

3. Chạy câu lệnh để kiểm tra các nodes được tạo
```
kubectl get nodes
```
![00003-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00003-Check-EKS-Cluster.png?width=90pc)

4. Trong giao diện  [AWS Console](https://aws.amazon.com/console/)
- Tìm **EKS**
- Chọn  **EKS**

![00004-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00004-Check-EKS-Cluster.png?width=90pc)


1. Trong giao diện **EKS**
- Chọn  **Cluster**
- Xem cluster đã tạo

![00005-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00005-Check-EKS-Cluster.png?width=90pc)

6. Trong giao diện [AWS Console](https://aws.amazon.com/console/)
- Tìm **EC2**
- Chọn  **EC2**

![00006-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00006-Check-EKS-Cluster.png?width=90pc)

7. Trong giao diện **EC2**
- Chọn **Instances**
- Xem các instance đã tạo

![00007-Check-EKS-Cluster](/000062_CICDonEKS/images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00007-Check-EKS-Cluster.png?width=90pc)

