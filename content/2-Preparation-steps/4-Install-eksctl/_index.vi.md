+++
title = "Cài đặt eksctl"
date = 2021
weight = 4
chapter = false
pre = "<b>2.4. </b>"
+++

#### Cài đặt eksctl

1. Trong phần này chúng ta sẽ thực hiện cài đặt công cụ **eksctl** vào **CloudShell Workspace.**
- Chạy câu lệnh để tải về công cụ eksctl.
```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

sudo mv -v /tmp/eksctl /usr/local/bin

```
![00001-Install-eksctl](../images/2-preparation-steps/4-Install-eksctl/00001-Install-eksctl.png?width=90pc)

2. Kiểm tra eksctl hoạt động hay không bằng câu lệnh dưới đây.
```
eksctl version

```
![00002-Install-eksctl](../images/2-preparation-steps/4-Install-eksctl/00002-Install-eksctl.png?width=90pc)

3. Kích hoạt tính năng bash-completion của eksctl
```
eksctl completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion

```
![00003-Install-eksctl](../images/2-preparation-steps/4-Install-eksctl/00003-Install-eksctl.png?width=90pc)


{{% notice note %}}
Thông tin cài đặt Eksctl xem thêm tại [Eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)
{{% /notice %}}
