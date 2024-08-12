+++
title = "Deploying the application"
date = 2024
weight = 3
chapter = false
pre = "<b>3.3. </b>"
+++

#### Deploy application to EKS cluster

1. Deploy a static Website to the **EKS Cluster** you just created. To deploy, we will first run the following command:
```
kubectl create deployment fcj-workshop --image=awsfcj/000062

```
![00001-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00001-Deploy-Application.png?width=90pc)

{{% notice info %}}
**awsfcj/00062** is a pre-built image to use in this lab
{{% /notice %}}

![00002-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00002-Deploy-Application.png?width=90pc)

2. To be able to access the Website from outside the EKS cluster, we will have to deploy a LoadBalancer Service to the cluster with the following command:
```
kubectl expose deployments/fcj-workshop --type=LoadBalancer --port=80

```
![00003-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00003-Deploy-Application.png?width=90pc)

3. To view information about LoadBalancer above, I will run the following command:

```
kubectl get svc

```
![00004-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00004-Deploy-Application.png?width=90pc)

4. Copy the link in **EXTERNAL-IP** into the browser to access the website

![00005-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00005-Deploy-Application.png?width=90pc)

5. Visit the **website**

![00006-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00006-Deploy-Application.png?width=90pc)
