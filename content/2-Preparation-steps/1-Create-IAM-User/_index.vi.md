+++
title = "Tạo IAM User"
date = 2024
weight = 1
chapter = false
pre = "<b>2.1. </b>"
+++

#### Tạo IAM User
1. Truy cập vào trang [AWS Console](https://aws.amazon.com/console/) 
- Tìm **IAM**
- Chọn **IAM**

![0001-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0001-createiamuser.png?width=90pc)

2. Trong giao diện **IAM**
- Chọn **User**
- Chọn **Add users**

![0002-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0002-createiamuser.png?width=90pc)

3. Trong bước **Add user**
- Nhập **User name**, nhập `aws-eks`
- Chọn **Access key - Programmatic access**
- Chọn **Password - AWS Management Console access**
- Chọn **Custom password**
- Chọn **Show password**
- Bỏ chọn **User must create a new password at next sign-in**
- Chọn **Next:Permissions**

![0003-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0003-createiamuser.png?width=90pc)

4. Trong bước tiếp theo của **Add user**
- Chọn  **Attach existing policies directly**
- Chọn  **AdministratorAccess**
- Chọn  **Next:Tags**


![0004-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0004-createiamuser.png?width=90pc)

1. Trong bước **Add tags**
- Nhập  **Key**: `Name`
- Nhập  **Value**: `Admin user`

![0005-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0005-createiamuser.png?width=90pc)

6. Kiểm tra lại và chọn **Create user**

![0006-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0006-createiamuser.png?width=90pc)

7. Sau khi **Add user** thành công
- Xem thông tin user đã tạo
- Chọn **Download.csv** để tải thông tin về **Access key ID** và **Serect access key**
- Sau đó, chọn **Close**

![0007-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0007-createiamuser.png?width=90pc)

8. Xem thông tin tạo user thành công

![0008-createiamuser](../images/2-Preparation-steps/1-Create-IAM-User/0008-createiamuser.png?width=90pc)