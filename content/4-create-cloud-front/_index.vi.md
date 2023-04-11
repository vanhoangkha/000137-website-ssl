---
title : "Tạo CloudFront Distribution"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

1. Mở bảng điều khiển của [Amazon CloudFront](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/)
2. Ấn **Create a CloudFront distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-1.png?featherlight=false&width=90pc)

3. Chọn origin domain là S3 bucket **fcjdmswebstore**, sau đó ấn **Use website endpoint**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-2.png?featherlight=false&width=90pc)


4. Kéo xuống dưới, tại phần **Default cache behavior** chọn **Redirect HTTP to HTTPS** cho **Viewer protocol policy**
5. Chọn **CORS-S3Origin** cho mục **Origin request policy**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-3.png?featherlight=false&width=90pc)

6. Kéo xuống dưới, tại phần **Settings**, ấn **Add item**
- Nhập CNAME: `www.fcjdms.click` và `fcjdms.click`
- Chọn SSL certificate vừa tạo ở phần trước

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-4.png?featherlight=false&width=90pc)

7. Kéo xuống cuối trang, nhập **index.html** cho mục **Default root object**
- Ấn **Create distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-5.png?featherlight=false&width=90pc)

8. Quay trở lại với bảng điều khiển của Route 53
- Chọn **Hosted zone** ở menu phía bên trái và chọn hosted zone đã tạo.
- Ấn **Create record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-6.png?featherlight=false&width=90pc)

9. Bật **Alias**
10. Chọn **Alias to CloudFront distribution**
- Chọn CloudFront distribution vừa tạo
- Ấn **Add another record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-7.png?featherlight=false&width=90pc)

11. Nhập `www` cho tên của record.
- Bật **Alias**
- Chọn **Alias to CloudFront distribution**
- Chọn CloudFront distribution vừa tạo
- Ấn **Create record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-8.png?featherlight=false&width=90pc)

12. Bạn đã tạo xong record cho CloudFront distribution

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-9.png?featherlight=false&width=90pc)

13. Nhập các đường dẫn sau vào một tab mới trong trình duyệt web của bạn: `http://DOMAIN`, `http://www.DOMAIN`, thay toàn bộ `DOMAIN` bằng tên domain của bạn. Tất cả các đường dẫn đó đều chuyển hướng đến đường dẫn mới, thay http bằng https

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-10.png?featherlight=false&width=90pc)

Bạn đã hoàn thành xong workshop giúp ứng dụng bảo mật hơn. Bài tiếp theo chúng ta sẽ cùng nhau triển khai tính năng tìm kiếm với Amazon OpenSearch Service cho ứng dụng.