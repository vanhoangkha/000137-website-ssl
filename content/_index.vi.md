---
title : "Serverless - Thiết lập trang web SSL S3 Static"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Serverless - Thiết lập trang web SSL S3 Static

#### Tổng quan

Trong bài này của series, chúng ta sẽ thiết lập để ứng dụng web bảo mật hơn khi transit bằng cách sử dụng SSL Certificate. SSL Certificate cho phép lưu lượng truy cập giữa người dùng và ứng dụng web host trên S3 bucket được mã hoá khi transit (in-flight encryption). 


Kiến trúc của ứng dụng web sẽ như sau:
![SeverlessExample](/images/serverless-diagram.png?featherlight=false&width=50pc)

- Tạo và quản lý chứng chỉ SSL với AWS Certificate Manager.
- Thiết lập một domain tuỳ chỉnh với Route 53 DNS
- Tạo một CloudFront CDN và liên kết noi với domain tuỳ chỉnh thông qua Route 53 DNS và bảo mật toàn bộ kết với chứng chỉ SSL.

#### Nội dung

1. [Chuẩn bị](1-preparation/)
2. [Tạo miền và Hosted zone](2-create-domain-hosted-zone/)
3. [Yêu cầu chứng chỉ SSL](3-request-certification/)
4. [Tạo CloudFront distribution](4-create-cloud-front/)
5. [Dọn dẹp tài nguyên](5-cleanup)
