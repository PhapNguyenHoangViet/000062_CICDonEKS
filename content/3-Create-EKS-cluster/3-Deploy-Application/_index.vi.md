+++
title = "Triển khai ứng dụng"
date = 2024
weight = 3
chapter = false
pre = "<b>3.3. </b>"
+++

#### Triển khai ứng dụng lên EKS cluster

1. Deploy một static Website vào EKS Cluster mình vừa tạo. Để deploy, đầu tiên chúng ta sẽ chạy command sau:
```
kubectl create deployment fcj-workshop --image=awsfcj/000062

```
![00001-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00001-Deploy-Application.png?width=90pc)

{{% notice info %}}
**awsfcj/00062** là image được build sẵn để sử dụng trong bài lab này
{{% /notice %}}

![00002-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00002-Deploy-Application.png?width=90pc)

2. Để có thể truy cập Website từ bên ngoài EKS cluster, chúng ta sẽ phải deploy một LoadBalancer Service vào cluster bằng command sau:
```
kubectl expose deployments/fcj-workshop --type=LoadBalancer --port=80

```
![00003-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00003-Deploy-Application.png?width=90pc)

3. Để xem thông tin về LoadBalancer trên, mình sẽ chạy command sau:

```
kubectl get svc

```
![00004-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00004-Deploy-Application.png?width=90pc)

4. Copy link trong **EXTERNAL-IP** vào trình duyệt sẽ truy cập được website

![00005-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00005-Deploy-Application.png?width=90pc)

5. Truy cập vào website

![00006-Deploy-Application](/images/3-Create-EKS-cluster/3-Deploy-Application/00006-Deploy-Application.png?width=90pc)
