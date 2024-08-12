+++
title = "Tạo Workspace"
date = 2024
weight = 2
chapter = false
pre = "<b>2.2. </b>"
+++

#### Tạo Workspace
1. Truy cập vào giao diện [AWS Management Console](https://console.aws.amazon.com/console/) 

- Tìm**CloudShell**
- Chon **CloudShell**

![00001-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00001-Create-Workspace.png?width=90pc)

2. Trong giao diện **AWS CloudShell**

- Thường thì khi chọn vào dịch vụ AWS CloudShell sẽ tự động tạo ra môi trường CLI cho chúng ta thực thi lệnh.
- Nhưng trong vài trường hợp, CloudShell sẽ không tự động tạo sẵn, do đó, ta sẽ ấn chọn Open environment – trong đó là tên region khi mở CloudShell.

![00002-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00002-Create-Workspace.png?width=90pc)

3. Copy and paste the following command into the **CloudShell** Terminal to install tools that support text processing on the command line.

```
sudo yum -y install jq gettext bash-completion
```

![00003-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00003-Create-Workspace.png?width=90pc)

4. Copy và Paste đoạn lệnh dưới đây vào Terminal của CloudShell để cài đặt các công cụ hỗ trợ xử lý text trên dòng lệnh.

```
sudo pip install --upgrade awscli && hash -r
```
![00004-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00004-Create-Workspace.png?width=90pc)


5. Chúng ta sẽ cấu hình **aws cli** sử dụng Region hiện tại.
```
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=<REGION>
export AZS=($(aws ec2 describe-availability-zones --query 'AvailabilityZones[].ZoneName' --output text --region $AWS_REGION))
```
**export AWS_REGION='yourREGION'**, thay trường thành id của region mà CloudShell đang mở.

![00005-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00005-Create-Workspace.png?width=90pc)

6. Kiểm tra Region hiện tại
```
test -n "$AWS_REGION" && echo AWS_REGION is "$AWS_REGION" || echo AWS_REGION is not set
```
![00006-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00006-Create-Workspace.png?width=90pc)

7. Chúng ta sẽ lưu các thông tin cấu hình vào bash_profile

```
echo "export ACCOUNT_ID=$ACCOUNT_ID" | tee -a ~/.bash_profile
echo "export AWS_REGION=$AWS_REGION" | tee -a ~/.bash_profile
echo "export AZS=${AZS[@]}" | tee -a ~/.bash_profile
aws configure set default.region $AWS_REGION
aws configure get default.region
```
![00007-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00007-Create-Workspace.png?width=90pc)

8. Chúng ta sẽ sử dụng câu lệnh để kiểm tra CloudShell đang sử dụng IAM Role có chính xác không.
```
aws sts get-caller-identity --query Arn | grep CloudFormation-Role -q && echo "IAM role valid" || echo "IAM role NOT valid"
```
![00008-Create-Workspace](../images/2-Preparation-steps/2-Create-Workspace/00008-Create-Workspace.png?width=90pc)