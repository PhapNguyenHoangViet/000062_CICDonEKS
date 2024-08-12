+++
title = "Cài đặt Kubernetes Tool"
date = 2024
weight = 3
chapter = false
pre = "<b>2.3. </b>"
+++

#### Cài đặt Kubernetes Tool

1. Copy và Paste đoạn lệnh dưới đây vào **Terminal của Workspace** để cài đặt **kubectl**.
```
sudo curl --silent --location -o /usr/local/bin/kubectl \
  https://amazon-eks.s3.us-west-2.amazonaws.com/1.17.11/2020-09-18/bin/linux/amd64/kubectl

sudo chmod +x /usr/local/bin/kubectl
```
![00001-install-kubernetes-tool](/images/2-preparation-steps/3-install-kubernetes-tool/00001-Install-Kubernetes-Tool.png?width=90pc)

2. Ta xem **jq** giống như sed cho dữ liệu JSON - bạn có thể sử dụng nó để cắt và lọc cũng như ánh xạ và chuyển đổi dữ liệu có cấu trúc với cùng một cách dễ dàng giống như sed, awk, grep.

```
echo 'yq() {
  docker run --rm -i -v "${PWD}":/workdir mikefarah/yq "$@"
}' | tee -a ~/.bashrc && source ~/.bashrc
```
![00002-install-kubernetes-tool](/images/2-preparation-steps/3-install-kubernetes-tool/00002-Install-Kubernetes-Tool.png?width=90pc)

3. Kiểm tra các công cụ đã được cài đặt bằng cách chạy lệnh dưới đây.
```
for command in kubectl jq envsubst aws
  do
    which $command &>/dev/null && echo "$command in path" || echo "$command NOT FOUND"
  done
```
![00003-install-kubernetes-tool](/images/2-preparation-steps/3-install-kubernetes-tool/00003-Install-Kubernetes-Tool.png?width=90pc)

4. Bật tính năng tự động hoàn tất cho công cụ kubectl bằng cách chạy lệnh dưới đây:
```
kubectl completion bash >> ~/.bash_completion
. /etc/profile.d/bash_completion.sh
. ~/.bash_completion
```
![00004-install-kubernetes-tool](/images/2-preparation-steps/3-install-kubernetes-tool/00004-Install-Kubernetes-Tool.png?width=90pc)


5. Thiết lập phiên bản 2.2.0 khi sử dụng AWS Load Balancer Controller
```
echo 'export LBC_VERSION="v2.2.0"' >>  ~/.bash_profile
.  ~/.bash_profile

```


{{% notice note %}}
Information on installing **Kubernetes Tool** can be found at [Kubernetes Tool](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)
{{% /notice %}}
