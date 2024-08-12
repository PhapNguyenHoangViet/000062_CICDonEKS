+++
title = "Kiểm tra CI/CD"
date = 2024
weight = 7
chapter = false
pre = "<b>4.7. </b>"
+++


#### Kiểm tra CI/CD pipeline
1. Vào GitHub của bạn https://github.com/{GITHUB_ACCOUNT}/000062-websource
- Chọn **repository** đã fork
- Mở file **index.html**, chọn icon chỉnh sửa
- Chỉnh sửa code trong file **index.html**. Trong bài này chỉnh code phần title **(dòng 48)**chuyển từ **John Doe** thành **AWS First Cloud Journey**
- Sau đó, chọn **Commit changes**

![00001-CICD-Check](../images/4-Generate-Code-Pipeline/7-CICD-Check/00001-CICD-Check.png?width=90pc)

2. Sau khi push code, **CodePipeline** sẽ được trigger để thực thi **CodeBuild**.
- Vào trang quản trị **CodePipeline** sẽ thấy trạng thái của pipeline là **In Progress**
- Pipele của có 2 stage
   - **Source**
   - Pull source từ GitHub
   - Đóng gói source cho stage build
   - **Build**
   - Tạo **Docker image** từ source
   - Đẩy image lên **ECR repository**
   - Triển khai cập nhật ứng dụng lên **EKS cluster**

![00002-CICD-Check](../images/4-Generate-Code-Pipeline/7-CICD-Check/00002-CICD-Check.png?width=90pc)


3. Deploy application updates to **EKS cluster** Wait about 5-10 minutes for the build process to complete and go to **Succeeded** state.

![00003-CICD-Check](../images/4-Generate-Code-Pipeline/7-CICD-Check/00003-CICD-Check.png?width=90pc)


4. Vào website URL xem thay đổi.
- Lúc này title của website đã chuyển thành AWS First Cloud Journey

![00004-CICD-Check](../images/4-Generate-Code-Pipeline/7-CICD-Check/00004-CICD-Check.png?width=90pc)


**Chúc mừng bạn đã hoàn thành bài lab.!!!**

