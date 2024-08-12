+++
title = "Clean up resources"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

#### Clear stack using AWS CloudFormation console
1. Open the [AWS CloudFormation console](https://console.aws.amazon.com/cloudformation/)

2. In the **Stack** page of **AWS CloudFormation**, select the **Stack** that you want to delete

3. Select **Delete**

4. Select **Delete stack**

#### Delete Repository
1. Open the [Amazon ECR console](https://console.aws.amazon.com/ecr/repositories)

2. On the navigation bar, select **Region** containing the repository to be deleted

3. Select **Repository**

4. In the **Repository** page, select **Private**

5. Select **Repository** to delete and select **Delete**

6. Verify delete **Repository** and select **Delete**

#### Delete EKSCluster
1. Open [Amazon EKS console page](https://console.aws.amazon.com/eks/home#/clusters)

2. Select the cluster to delete and select **Delete**

3. Verify cluster deletion and select **Delete**

#### Delete CloudShell Environment
1. Select **Region** containing the environment to delete

2. In the **CloudShell** interface, choose **Actions**

3. Select **Delete**

4. **Verify** environment deletion by entering delete and selecting **delete**
