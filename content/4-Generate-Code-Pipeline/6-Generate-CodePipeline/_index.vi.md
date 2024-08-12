+++
title = "Tạo một pipeline"
date = 2024
weight = 6
chapter = false
pre = "<b>4.6. </b>"
+++

#### Tạo một CI/CD pipeline với CodePipeline

1. Chúng ta sẽ tạo CodePipeline sử dụng công cụ AWS CloudFormation.
- Chọn Download [CloudFormation template file](https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/code_pipeline_fcj.yml)

![00001-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00001-Generate-CodePipeline.png?width=90pc)

- Ctrl A
- Ctrl C
- Tạo file New Text Document.txt

![000013-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000013-Generate-CodePipeline.png?width=90pc)

- Đổi tên code_pipeline_fcj.yml

![000014-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000014-Generate-CodePipeline.png?width=90pc)
- Ctrl V

![000015-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000015-Generate-CodePipeline.png?width=90pc)
- Thêm vào file  : **rm -f /etc/apt/sources.list.d/sbt.list**
```
- rm -f /etc/apt/sources.list.d/sbt.list
```

![000016-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000016-Generate-CodePipeline.png?width=90pc)


  
2. Trong giao diện [AWS Console](https://aws.amazon.com/console/)
- Tìm  **CloudFormation**
- Chọn  **CloudFormation**

![00002-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00002-Generate-CodePipeline.png?width=90pc)


3. Trong giao diện CloudFormation
- Chọn  **Stacks**
- Chọn  **Create stack**
- Chọn  **With new resources (standard)**

![00003-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00003-Generate-CodePipeline.png?width=90pc)

4. Trong giao diện **Create stack**
- Chọn  **Template is ready**
- Chọn  **Upload a template file**
- Chọn  **Choose file**
- Chọn  **CloudFormation template** đã tải về. Ví dụ `code_pipeline_fcj.yml`
- Chọn  **Next**

![00004-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00004-Generate-CodePipeline.png?width=90pc)

5. Phần **Stack name**, nhập `Eks-stack`

![00005-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00005-Generate-CodePipeline.png?width=90pc)


6. Tiếp theo, điền thông tin các mục sau:
**User name**, nhập tên **Github Account**
- Nhập **Access token** đã tạo
- Nhập tên **Repository**
- Nhập **Branch**
- Nhập tên **EksCluster**
- Nhập **EksDeployment**
- Nhập **EksNamespace**
- Chọn  **Next**

![00006-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00006-Generate-CodePipeline.png?width=90pc)


7. Kéo xuống cuối trang và chọn **Next**

![00007-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00007-Generate-CodePipeline.png?width=90pc)

8. Kéo xuống cuối trang và chọn **Create stack**

![00008-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00008-Generate-CodePipeline.png?width=90pc)

9.  Hoàn thành tạo stack

![00009-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00009-Generate-CodePipeline.png?width=90pc)

10. Trong giao diện [AWS Console](https://aws.amazon.com/console/)
- Tìm  **CodePipeline**
- Chọn  **CodePipeline**

![000010-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000010-Generate-CodePipeline.png?width=90pc)

11. Quá trình CI/CD

![000011-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000011-Generate-CodePipeline.png?width=90pc)

12. Quá trình CI/CD hoàn thành khi chuyển sang trang thái **Succeeded**

![000012-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000012-Generate-CodePipeline.png?width=90pc)


13. Kiểm tra
![000017-Generate-CodePipeline](/images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000017-Generate-CodePipeline.png?width=90pc)
