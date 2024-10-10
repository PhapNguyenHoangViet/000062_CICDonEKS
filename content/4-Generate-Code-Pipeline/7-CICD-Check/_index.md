+++
title = "Test CI/CD"
date = 2024
weight = 7
chapter = false
pre = "<b>4.7. </b>"
+++


#### Test CI/CD pipeline
1. Go to your **GitHub** https://github.com/{GITHUB_ACCOUNT}/000062-websource
- Select the fork repository
- Open the file **index.html**, select the edit icon
- Edit the code in the file index.html. In this article, change the code of the title (**line 48**) from **John Doe** to **AWS First Cloud Journey**
- Then select **Commit changes**

![00001-CICD-Check](/images/4-Generate-Code-Pipeline/7-CICD-Check/00001-CICD-Check.png?width=90pc)

2. After pushing the code, **CodePipeline** will be triggered to execute **CodeBuild**.
- Go to the admin page **CodePipeline** and you will see the status of the pipeline is **In Progress**
- Pipele’s has 2 stages:
   - **Source**
   - Pull source from GitHub
   - Pack source for stage build
   - **Build**
   - Create **Docker image** from **source**
   - Push the image to **ECR repository**
   - Deploy application updates to **EKS cluster**

![00002-CICD-Check](/images/4-Generate-Code-Pipeline/7-CICD-Check/00002-CICD-Check.png?width=90pc)


3. Deploy application updates to **EKS cluster** Wait about 5-10 minutes for the build process to complete and go to **Succeeded** state.

![00003-CICD-Check](/images/4-Generate-Code-Pipeline/7-CICD-Check/00003-CICD-Check.png?width=90pc)


4. Go to the website URL to see the changes.
- At this time, the title of the website has changed to **AWS First Cloud Journey**

![00004-CICD-Check](/images/4-Generate-Code-Pipeline/7-CICD-Check/00004-CICD-Check.png?width=90pc)


**Congratulations on completing the lab!!!**

