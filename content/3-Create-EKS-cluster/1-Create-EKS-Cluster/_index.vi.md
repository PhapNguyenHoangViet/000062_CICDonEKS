+++
title = "Tạo EKS Cluster"
date = 2024
weight = 1
chapter = false
pre = "<b>3.1. </b>"
+++

#### Tạo EKS Cluster
1. Để tạo **EKS cluster**, trước tiên chúng ta sẽ phải tạo **SSH key** để có thể access vào **EC2 Node** trong Cluster khi cần thiết:
```
aws ec2 create-key-pair --key-name k8s-demo --query 'KeyMaterial' --output text> k8s-demo.pem

```
![00001-Create-EKS-cluster](../images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00001-Create-EKS-Cluster.png?width=90pc)

2. Trong giao diện **AWS Console interface**
- Tìm  **EC2**
- Chọn  **EC2**

![00002-Create-EKS-cluster](../images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00002-Create-EKS-Cluster.png?width=90pc)

3. Trong giao diện **EC2**
- Chọn **Key Pair**
- Xem **Key Pair** vừa tạo

![00003-Create-EKS-cluster](../images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00003-Create-EKS-Cluster.png?width=90pc)

4. Để tạo **EKS Cluster** và các **EC2 Node** chúng ta sử dụng command sau:
```
eksctl create cluster --name k8s-demo --region ap-southeast-1 --nodegroup-name k8s-demo --nodes 2 --ssh-access --ssh-public-key k8s-demo --managed
```

- Khi bạn chạy command này, thì **eksctl** sẽ sử dụng **AWS CloudFormation** để tạo các **infrastructure** cần thiết và setup Master Node (Control Plane).

![00004-Create-EKS-cluster](../images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00004-Create-EKS-Cluster.png?width=90pc)

5. Giao diện sau khi tạo **EKS Cluster**.

![00005-Create-EKS-cluster](../images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00005-Create-EKS-Cluster.png?width=90pc)

{{% notice note %}}
Mất khoảng 15 phút để hoàn thành quá trình khởi tạo **EKS Cluster**
{{% /notice %}}
