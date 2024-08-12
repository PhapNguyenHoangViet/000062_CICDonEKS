+++
title = "Create EKS Cluster"
date = 2024
weight = 1
chapter = false
pre = "<b>3.1. </b>"
+++

#### Create EKS Cluster
1. To create **EKS cluster**, we will first have to generate **SSH key** to be able to access **EC2 Node** in the Cluster as needed:
```
aws ec2 create-key-pair --key-name k8s-demo --query 'KeyMaterial' --output text> k8s-demo.pem

```
![00001-Create-EKS-cluster](/images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00001-Create-EKS-Cluster.png?width=90pc)

2. In the **AWS Console interface**
- Find **EC2**
- Select **EC2**

![00002-Create-EKS-cluster](/images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00002-Create-EKS-Cluster.png?width=90pc)

3. In **EC2** interface
- Select **Key Pair**
- View **Key Pair** just created

![00003-Create-EKS-cluster](/images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00003-Create-EKS-Cluster.png?width=90pc)

4. To create **EKS Cluster** and **EC2 Nodes** we use the following command:
```
eksctl create cluster --name k8s-demo --region ap-southeast-1 --nodegroup-name k8s-demo --nodes 2 --ssh-access --ssh-public-key k8s-demo --managed
```

- When you run this command, **eksctl** will use **AWS CloudFormation** to create the necessary infrastructure and setup **Master Node **(Control Plane).****

![00004-Create-EKS-cluster](/images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00004-Create-EKS-Cluster.png?width=90pc)

5. Interface after creating **EKS Cluster.**

![00005-Create-EKS-cluster](/images/3-Create-EKS-cluster/1-Create-EKS-Cluster/00005-Create-EKS-Cluster.png?width=90pc)

{{% notice note %}}
It takes about 15 minutes to complete the initialization of **EKS Cluster**
{{% /notice %}}
