+++
title = "Create Workspace"
date = 2024
weight = 2
chapter = false
pre = "<b>2.2. </b>"
+++

#### Create Workspace
1. Access the [AWS Management Console](https://console.aws.amazon.com/console/) interface

- Search **CloudShell**
- Select **CloudShell**

![00001-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00001-Create-Workspace.png?width=90pc)

2. In the **AWS CloudShell** interface

- Usually, when selecting the **AWS CloudShell** service, it automatically creates a CLI environment for us to execute commands.
- However, in some cases, **CloudShell** may not automatically create one. In such instances, we will click on **Open environment** – where is the name of the region when opening CloudShell.

![00002-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00002-Create-Workspace.png?width=90pc)

3. Copy and paste the following command into the **CloudShell** Terminal to install tools that support text processing on the command line.

```
sudo yum -y install jq gettext bash-completion
```

![00003-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00003-Create-Workspace.png?width=90pc)

4. Copy and Paste the command below into **Terminal of Workspace** to update **awscli**.
```
sudo pip install --upgrade awscli && hash -r
```
![00004-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00004-Create-Workspace.png?width=90pc)


5. Next we will configure the aws cli to use the current Region.
```
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=<REGION>
export AZS=($(aws ec2 describe-availability-zones --query 'AvailabilityZones[].ZoneName' --output text --region $AWS_REGION))
```
At **export AWS_REGION=<REGION>**, Replace the field with the ID of the region where CloudShell is currently open.

![00005-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00005-Create-Workspace.png?width=90pc)

6. Check that AWS_REGION has been set to the correct current Region.
```
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set
```
![00006-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00006-Create-Workspace.png?width=90pc)

7. We will save the configuration information to bash_profile

```
echo "export ACCOUNT_ID=$ACCOUNT_ID" | tee -a ~/.bash_profile
echo "export AWS_REGION=$AWS_REGION" | tee -a ~/.bash_profile
echo "export AZS=${AZS[@]}" | tee -a ~/.bash_profile
aws configure set default.region $AWS_REGION
aws configure get default.region
```
![00007-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00007-Create-Workspace.png?width=90pc)

8. We will use a command to check if CloudShell is using the correct IAM Role.
```
aws sts get-caller-identity --query Arn | grep CloudFormation-Role -q && echo "IAM role valid" || echo "IAM role NOT valid"
```
![00008-Create-Workspace](/000062_CICDonEKS/images/2-Preparation-steps/2-Create-Workspace/00008-Create-Workspace.png?width=90pc)