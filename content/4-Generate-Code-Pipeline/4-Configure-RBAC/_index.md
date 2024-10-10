+++
title = "Configuring RBAC"
date = 2024
weight = 4
chapter = false
pre = "<b>4.4. </b>"
+++

#### Configuring RBAC

1. In order for CodeBuild to interact with EKS, we will modify **configMap aws-auth**
- From terminal to which you have connected EKS cluster, get a copy of **configMap aws-auth** with the command:
```
kubectl get configmaps aws-auth -n kube-system -o yaml > aws-auth.yaml
```
![00001-Configure-RBAC](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-Configure-RBAC/00001-Configure-RBAC.png?width=90pc)

2. Open the file **aws-auth.yaml** :
```
nano aws-auth.yaml
```
![00002-Configure-RBAC](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-Configure-RBAC/00002-Configure-RBAC.png?width=90pc)

3. Edit this aws-auth.yaml file, adding an item in the data.mapRoles array:
```
- groups:
  - system:masters
  rolearn: arn:aws:iam::{$AWS_ACCOUNT_ID}}:role/eks-CodeBuildServiceRole
  username: codebuild-eks

```
![00003-Configure-RBAC](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-Configure-RBAC/00003-Configure-RBAC.png?width=90pc)
4. The aws-auth.yaml file after adding the eks-CodeBuildServiceRole role has the following form:
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

![00005-Configure-RBAC](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-Configure-RBAC/00005-Configure-RBAC.png?width=90pc)
5. Apply the changed aws-auth.yaml file from the terminal:
```
kubectl apply -f aws-auth.yaml
```

![00004-Configure-RBAC](/000062_CICDonEKS/images/4-Generate-Code-Pipeline/4-Configure-RBAC/00004-Configure-RBAC.png?width=90pc)