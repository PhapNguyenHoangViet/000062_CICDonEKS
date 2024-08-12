+++
title = "Installing eksctl"
date = 2021
weight = 4
chapter = false
pre = "<b>2.4. </b>"
+++

#### Installing eksctl

1. In this section we will install the eksctl tool into CloudShell Workspace.
- Run the command to download the eksctl tool.
```
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

sudo mv -v /tmp/eksctl /usr/local/bin

```
![00001-Install-eksctl](/images/2-preparation-steps/4-Install-eksctl/00001-Install-eksctl.png?width=90pc)

2. Check if eksctl works or not with the command below.
```
eksctl version

```
![00002-Install-eksctl](/images/2-preparation-steps/4-Install-eksctl/00002-Install-eksctl.png?width=90pc)

3. Enable bash-completion of eksctl
```
eksctl completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion

```
![00003-Install-eksctl](/images/2-preparation-steps/4-Install-eksctl/00003-Install-eksctl.png?width=90pc)


{{% notice note %}}
Installation information **Eksctl** see more at [Eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)
{{% /notice %}}
