+++
title = "Create a pipeline"
date = 2024
weight = 6
chapter = false
pre = "<b>4.6. </b>"
+++

#### Create a CI/CD pipeline with CodePipeline

1. We will create a CodePipeline using the AWS CloudFormation engine.
- Select Download [CloudFormation template file](https://raw.githubusercontent.com/First-Cloud-Journey/000062-EKSCICD/main/code_pipeline_fcj.yml)

![00001-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00001-Generate-CodePipeline.png?width=90pc)

- Ctrl A
- Ctrl C
- Create New Text Document.txt

![000013-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000013-Generate-CodePipeline.png?width=90pc)

- Rename code_pipeline_fcj.yml

![000014-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000014-Generate-CodePipeline.png?width=90pc)
- Ctrl V

![000015-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000015-Generate-CodePipeline.png?width=90pc)
- Add in file : **rm -f /etc/apt/sources.list.d/sbt.list**
```
- rm -f /etc/apt/sources.list.d/sbt.list
```

![000016-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000016-Generate-CodePipeline.png?width=90pc)


  
2. In the [AWS Console](https://aws.amazon.com/console/)
- Find **CloudFormation**
- Select **CloudFormation**

![00002-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00002-Generate-CodePipeline.png?width=90pc)


3. In the **CloudFormation** interface
- Select **Stacks**
- Select **Create stack**
- Select **With new resources (standard)**

![00003-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00003-Generate-CodePipeline.png?width=90pc)

4. In the **Create stack** interface
- Select **Template is ready**
- Select **Upload a template file**
- Select **Choose file**
- Select the downloaded **CloudFormation template** file. Example `code_pipeline_fcj.yml`
- Select **Next**

![00004-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00004-Generate-CodePipeline.png?width=90pc)

5. In the **Stack name** section, enter `Eks-stack`

![00005-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00005-Generate-CodePipeline.png?width=90pc)


6. Next, fill in the following information:
**User name**, enter the name **Github Account**
- Enter **Access token** created
- Enter the name **Repository**
- Enter **Branch**
- Enter the name **EksCluster**
- Enter **EksDeployment**
- Enter **EksNamespace**
- Select **Next**

![00006-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00006-Generate-CodePipeline.png?width=90pc)


7. Scroll to the bottom of the page and select **Next**

![00007-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00007-Generate-CodePipeline.png?width=90pc)

8. Scroll to the bottom of the page and select **Create stack**

![00008-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00008-Generate-CodePipeline.png?width=90pc)

9.  Complete stack creation

![00009-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/00009-Generate-CodePipeline.png?width=90pc)

10. In the [AWS Console](https://aws.amazon.com/console/)
- Find **CodePipeline**
- Select **CodePipeline**

![000010-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000010-Generate-CodePipeline.png?width=90pc)

11. CI/CD . Process

![000011-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000011-Generate-CodePipeline.png?width=90pc)

12. CI/CD process completes when entering **Succeeded** state

![000012-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000012-Generate-CodePipeline.png?width=90pc)


13. Check
![000017-Generate-CodePipeline](../images/4-Generate-Code-Pipeline/6-Generate-CodePipeline/000017-Generate-CodePipeline.png?width=90pc)
