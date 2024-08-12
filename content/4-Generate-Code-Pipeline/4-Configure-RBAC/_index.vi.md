+++
title = "Cấu hình RBAC"
date = 2024
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++

#### Cấu hình RBAC

1. Để CodeBuild có thể tương tác với **EKS**, chúng ta sẽ chỉnh sửa **configMap aws-auth**
- Từ terminal mà bạn đã kết nối **EKS cluster**, lấy bản sao configMap aws-auth bằng command:
```
kubectl get configmaps aws-auth -n kube-system -o yaml > aws-auth.yaml
```
![00001-configure-rbac](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-configure-rbac/00001-configure-rbac.png?width=90pc)

2. Mở tập tin **aws-auth.yaml** vừa tạo ở trên:
```
nano aws-auth.yaml
```
![00002-configure-rbac](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-configure-rbac/00002-configure-rbac.png?width=90pc)

3. Sửa file **aws-auth.yaml** này, thêm một item trong mảng **data.mapRoles**:
```
- groups:
  - system:masters
  rolearn: arn:aws:iam::{$AWS_ACCOUNT_ID}}:role/eks-CodeBuildServiceRole
  username: codebuild-eks

```
![00003-configure-rbac](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-configure-rbac/00003-configure-rbac.png?width=90pc)

4. Tập tin aws-auth.yaml sau khi thêm role eks-CodeBuildServiceRole có dạng như sau:
{{% notice note %}}
Remove the lines metadata.creationTimestamp and metadata.resourceVersion
{{% /notice %}}
```
apiVersion: v1
data:
  mapRoles: |
    - groups:
      - system:bootstrappers
      - system:nodes
      rolearn: arn:aws:iam::451085899692:role/eksctl-k8s-demo-nodegroup-k8s-dem-NodeInstanceRole-LYNRCIX49ZOU
      username: system:node:{{EC2PrivateDNSName}}
    - groups:
      - system:masters
      rolearn: arn:aws:iam::{$AWS_ACCOUNT_ID}}:role/eks-CodeBuildServiceRole
      username: codebuild-eks
kind: ConfigMap
metadata:
  creationTimestamp: "2022-04-26T10:21:52Z"
  managedFields:
  - apiVersion: v1
    fieldsType: FieldsV1
    fieldsV1:
      f:data:
        .: {}
        f:mapRoles: {}
    manager: vpcLambda
    operation: Update
    time: "2022-04-26T10:21:52Z"
  name: aws-auth
  namespace: kube-system
  resourceVersion: "2691"
  uid: a2862e92-4697-4654-bb19-dc28b17dc21b
```

![00005-configure-rbac](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-configure-rbac/00005-configure-rbac.png?width=90pc)
5. Apply tập tin **aws-auth.yaml** đã thay đổi từ terminal:
```
kubectl apply -f aws-auth.yaml
```

![00004-configure-rbac](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-configure-rbac/00004-configure-rbac.png?width=90pc)