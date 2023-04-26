---
title : "Chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
Trước khi thực hiện nội dung chính của workshop này, chúng ta cần thiết lập lại ứng dụng web bằng AWS SAM.
1. Tải source code dưới đây

{{%attachments title="Source code" pattern=".*\.(zip)$"/%}}

2. Chạy các câu lệnh dưới đây
```
sam build
sam deploy --guided
```

3. Nhập nội dung như sau:
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
4. Mở bảng điều khiển của [AWS API Gateway](https://ap-southeast-1.console.aws.amazon.com/apigateway/main/apis?region=ap-southeast-1)

5. Ấn chọn **API Gateway REST API to Lambda**

![CreateUserPool](/images/1-preparation/1-preparation-1.png?featherlight=false&width=90pc)

6. Ấn chọn **Stage** ở menu phía bên trái
- Ấn chọn **dev**
- Ghi lại **InvokeURL**

![CreateUserPool](/images/1-preparation/1-preparation-2.png?featherlight=false&width=90pc)

7. Nếu bạn chưa tải code của ứng dụng thì chạy các command dưới đây:
```
git clone https://github.com/AWS-First-Cloud-Journey/
FCJ-Serverless-DMS.git
cd FCJ-Serverless-DMS
npm install
```
8. Mở tệp **src/constant.js**, thay giá trị của **APP_API_URL** bằng **InvokeURL**

![CreateUserPool](/images/1-preparation/1-preparation-3.png?featherlight=false&width=90pc)

9. Thực hiện các câu lệnh dưới đây để build project
```
cd FCJ-Serverless-DMS
yarn build
```
10. Chúng ta đã build xong front-end. Tiếp theo thực hiện câu lệnh sau để tải thư mục **build** lên S3 bucket
```
aws s3 cp build s3://fcjdmswebstore --recursive
```

Vậy là chúng ta đã tạo lại xong ứng dụng web.
