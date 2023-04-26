---
title : "Preparation"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Before we get to the main content of this workshop, we need to reset the web application.
1. Download the below source code

{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

2. Run the below commands
```
sam build
sam deploy --guided
```

3. Enter the following content:
- Stack Name []: `fcjdmsapp`
    - AWS Region []: `ap-southeast-1`
    - Parameter DocumentStoreBucketName [fcjdmsstore]: *return*
    - Parameter WebStoreBucketName [fcjdmswebstore]: *return*
    - Confirm changes before deploy [y/N]: `y`
    - Allow SAM CLI IAM role creation [Y/n]: `y`
    - Disable rollback [y/N]: `n`
    - DocsList may not have authorization defined, Is this okay? [y/N]: `y`
    - DocsUpload may not have authorization defined, Is this okay? [y/N]: `y`
    - DocsDelete may not have authorization defined, Is this okay? [y/N]: `y`
    - GeneralInforUpload may not have authorization defined, Is this okay? [y/N]: `y`
    - GeneralInforGet may not have authorization defined, Is this okay? [y/N]: `y`
    - Save arguments to configuration file [Y/n]: `y`
    - SAM configuration file [samconfig.toml]: *return*
    - SAM configuration environment [default]: *return*
    - Deploy this changeset? [y/N]: `y`
4. Open [AWS API Gateway console](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/apis?region=ap-southeast-1)

5. Click **API Gateway REST API to Lambda**

![CreateUserPool](/images/1-preparation/1-preparation-1.png?featherlight=false&width=90pc)

6. Click **Stage** on the left menu
- Click **dev**
- Note down the **InvokeURL**

![CreateUserPool](/images/1-preparation/1-preparation-2.png?featherlight=false&width=90pc)

7. If you have not downloaded the application code, run the commands below:
```
git clone https://github.com/AWS-First-Cloud-Journey/
FCJ-Serverless-DMS.git
cd FCJ-Serverless-DMS
npm install
```
8. Open the **src/constant.js** file, replace the value of **APP_API_URL** with **InvokeURL**

![CreateUserPool](/images/1-preparation/1-preparation-3.png?featherlight=false&width=90pc)

9. Run the below commands to build project
```
yarn build
```
10. We have finished building the front-end. Next, run the below command to upload **build** folder to S3 bucket
```
aws s3 cp build s3://fcjdmswebstore --recursive
```

So we have rebuilt the web application.
