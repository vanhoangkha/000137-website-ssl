---
title : "Yêu Cầu Chứng Chỉ SSL"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---
1. Mở bảng điiều khiển của [AWS Certificate Manager](https://ap-southeast-1.console.aws.amazon.com/acm/home?region=ap-southeast-1#/welcome)

{{% notice note %}}
Vùng để tạo certificate bắt buộc là N.Virginia (us-east-1)
{{% /notice %}}

2. Ấn **Request a certificate**

![DeployFunction](/images/3-request-certification/3-request-certification-1.png?featherlight=false&width=90pc)

3. Ấn **Next**

![DeployFunction](/images/3-request-certification/3-request-certification-2.png?featherlight=false&width=90pc)

4. Nhập tên miền: `fcjdms.click`
- Ấn **Add another name to this certificate**
- Nhập tên miền khác: `*.fcjdms.click`
- Kéo xuống cuối trang, ấn nút **Request**

![DeployFunction](/images/3-request-certification/3-request-certification-3.png?featherlight=false&width=90pc)

5. Ấn chọn vào certificate bạn vừa tạo
- Đợi một lát để khởi tạo CNAME cho miền, sau đó ấn **Create records in 53**

![DeployFunction](/images/3-request-certification/3-request-certification-4.png?featherlight=false&width=90pc)

6. Ấn **Create records**

![DeployFunction](/images/3-request-certification/3-request-certification-5.png?featherlight=false&width=90pc)

7. Đợi một lát để AWS xác nhận miền của bạn, sau khi xác nhận thành công chuyển trạng thái sang **Success**

![DeployFunction](/images/3-request-certification/3-request-certification-6.png?featherlight=false&width=90pc)

Chúng ta đã yêu cầu một SSL certificate thành công. Certificate này sẽ được CloudFront sử dụng ở bước tiếp theo