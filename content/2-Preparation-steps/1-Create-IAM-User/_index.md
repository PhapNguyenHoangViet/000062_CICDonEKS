+++
title = "Create IAM User"
date = 2024
weight = 1
chapter = false
pre = "<b>2.1. </b>"
+++

#### Create IAM User
1. Go to the [AWS Console](https://aws.amazon.com/console/) 
- Find IAM
- Select IAM

![0001-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0001-createiamuser.png?width=90pc)

2. In the IAM interface
- Select User
- Select Add users

![0002-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0002-createiamuser.png?width=90pc)

3. In Add user step
- Enter **User name**, enter `aws-eks`
- Select **Access key - Programmatic access**
- Select **Password - AWS Management Console access**
- Select **Custom password**
- Select **Show password**
- Uncheck **User must create a new password at next sign-in**
- Select **Next:Permissions**

![0003-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0003-createiamuser.png?width=90pc)
![0003-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0003.1-createiamuser.png?width=90pc)

4. In the next step of **Add user**
- Select **Attach existing policies directly**
- Select **AdministratorAccess**
- Select **Next:Tags**


![0004-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0004-createiamuser.png?width=90pc)

5. In **Add tags** step
- Enter **Key**: `Name`
- Enter **Value**: `Admin user`

![0005-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0005-createiamuser.png?width=90pc)

6. Check again and select Create user

![0006-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0006-createiamuser.png?width=90pc)

7. After **Add user** is successful
- View created user information
- Select **Download.csv** to download information about **Access key ID** and **Secure access key**
- Then select Close

![0007-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0007-createiamuser.png?width=90pc)

8. View successful user creation information

![0008-createiamuser](/images/2-Preparation-steps/1-Create-IAM-User/0008-createiamuser.png?width=90pc)