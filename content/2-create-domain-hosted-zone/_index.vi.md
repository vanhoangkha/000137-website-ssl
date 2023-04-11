---
title : "Tạo Miền Và Hosted Zone"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
Trong bước này, chúng ta sẽ tạo một Domain và Hosted zone với Amazon Route 53.

{{% notice warning %}}
Việc tạo miền sẽ tốn chi phí của bạn.
{{% /notice %}}

1. Mở bảng điều khiển của [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=ap-southeast-1#)

2. Chọn **Registered domains** ở phía menu phía bên trái
- Ấn **Register Domain**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-1.png?featherlight=false&width=90pc)

3. Nhập tên miền mà bạn muốn tạo, ví dụ: `fcjdms`
- Lựa chọn Top Level Domain phù hợp.
- Ấn **Check** để kiểm tra xem tên miền có đang có sẵn không
- Ấn **Add to cart**
- Ấn **Continue** để tiếp tục

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-2.png?featherlight=false&width=90pc)


4. Nhập các thông tin các nhân của bạn, sau đó ấn **Continue** để tiếp tục.

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-3.png?featherlight=false&width=90pc)

5. Chọn **Disable** để không tự động gia hạn tên miền sau khi nó hết hạn
6. Tại mục **Terms and Conditions**, tích chọn đồng ý với các điều khoản
7. Ấn **Complete Order**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-4.png?featherlight=false&width=90pc)

8. Ấn **Close**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-5.png?featherlight=false&width=90pc)

9. Ấn **Go To Domains**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-6.png?featherlight=false&width=90pc)

10. Sau đó, bạn sẽ thấy một miền đang được xử lý trong mục **Pending requests**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-7.png?featherlight=false&width=90pc)

11. Đợi một lúc, miền của bạn sẽ sẵn sàng để sử dụng
- Ấn chọn **Registered domains** ở menu phía bên trái

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-8.png?featherlight=false&width=90pc)

12. Ấn chọn **Hosted zones** ở menu phía bên trái, bạn sẽ thấy một hosted zone được tạo tự động. Chúng ta sẽ xoá và tự tạo một hosted zone mới.
- Ấn **Create hosted zone**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-9.png?featherlight=false&width=90pc)

13. Nhập tên của miền đã đăng ký.
- Nhập mô tả: `The hosted zone is used for FCJ Document Management System`
- Ấn **Create hosted zone**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-10.png?featherlight=false&width=90pc)

{{% notice note %}}
Nhập chính xác tên miền mà bạn đã đăng ký.
{{% /notice %}}

14. Chúng ta đã hoàn thành tạo một hosted zone, sao chép tất cả Name Servers.

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-11.png?featherlight=false&width=90pc)

15. Tiếp theo chúng ta sẽ cập nhật lại DNS của domain khớp với hosted zone
16. Chọn **Resgisterd domains** ở menu bên trái và chọn domain vừa tạo.
17. Ấn **Add or edit name servers**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-12.png?featherlight=false&width=90pc)

18. Dán Name Servers của hosted zone vào các ô. Sau đó ấn **Update**. 

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-13.png?featherlight=false&width=90pc)

19. Kiểm tra email mà bạn đã dùng để đăng ký domain, nếu nhận được mail xác nhận việc cập nhật là bạn đã cập nhật thành công.
