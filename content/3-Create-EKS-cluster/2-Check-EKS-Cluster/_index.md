+++
title = "Check EKS Cluster"
date = 2024
weight = 2
chapter = false
pre = "<b>3.2. </b>"
+++

#### Check EKS Cluster
1. In the [AWS Console](https://aws.amazon.com/console/)
- Find **CloudFormation**
- Select **CloudFormation**

![00001-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00001-Check-EKS-Cluster.png?width=90pc)

2. In the **CloudFormation** interface
- Select **Stack**
- View created stacks

![00002-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00002-Check-EKS-Cluster.png?width=90pc)

3. Run the command to check the nodes created
```
kubectl get nodes
```
![00003-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00003-Check-EKS-Cluster.png?width=90pc)

4. In the [AWS Console](https://aws.amazon.com/console/)
- Find **EKS**
- Select **EKS**

![00004-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00004-Check-EKS-Cluster.png?width=90pc)


5. In the **EKS** interface
- Select **Cluster**
- View the created cluster

![00005-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00005-Check-EKS-Cluster.png?width=90pc)

6. In the [AWS Console](https://aws.amazon.com/console/)
- Find **EC2**
- Select **EC2**

![00006-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00006-Check-EKS-Cluster.png?width=90pc)

7. In the **EC2** interface
- Select **Instances**
- View created instances
 
![00007-Check-EKS-Cluster](../images/3-Create-EKS-cluster/2-Check-EKS-Cluster/00007-Check-EKS-Cluster.png?width=90pc)

