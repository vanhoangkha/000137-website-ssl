---
title : "Create Domain And Hosted Zone"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 2. </b> "
---
In this step, we will create a Domain and Hosted zone with Amazon Route 53.

{{% notice warning %}}
Domain creation will cost you.
{{% /notice %}}

1. Open [Amazon Route 53](https://us-east-1.console.aws.amazon.com/route53/home?region=ap-southeast-1#)

2. Select **Registered domains** on the left menu
- Click **Register Domain**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-1.png?featherlight=false&width=90pc)

3. Enter the domain name you want to create, ví dụ: `fcjdms`
- Select the appropriate Top Level Domain
- Click **Check** to check the domain name is available
- Click **Add to cart**
- Click **Continue**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-2.png?featherlight=false&width=90pc)


4. Enter your personal information, then click **Continue** to continue.

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-3.png?featherlight=false&width=90pc)

5. Click **Disable** to not automatically renew the domain after it expires
6. At **Terms and Conditions** section, check to agree to the terms
7. Click **Complete Order**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-4.png?featherlight=false&width=90pc)


8. Click **Close**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-5.png?featherlight=false&width=90pc)

9. Click **Go To Domains**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-6.png?featherlight=false&width=90pc)

10. Then, you will see a domain being processed under **Pending requests**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-7.png?featherlight=false&width=90pc)

11. Wait for a while, your domain will be ready to use
- Select **Registered domains** on the left menu

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-8.png?featherlight=false&width=90pc)

12. Select **Hosted zones** on the left menu, you will see a hosted zone automatically created. We will delete and manually create a new hosted zone.
- Click **Create hosted zone**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-9.png?featherlight=false&width=90pc)

13. Enter domain name you registered
- Enter description: `The hosted zone is used for FCJ Document Management System`
- Click **Create hosted zone**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-10.png?featherlight=false&width=90pc)

{{% notice note %}}
Enter the exact domain name you registered
{{% /notice %}}

14. We are done creating a hosted name, next step we will request a SSL certificate with AWS Certificate Manager

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-11.png?featherlight=false&width=90pc)

15. Next, we will update the DNS of the domain to match the hosted zone
16. Select **Resgisterd domains** on the left menu and select the domain you just created.
17. Click **Add or edit name servers**

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-12.png?featherlight=false&width=90pc)

18. Paste the Name Servers of the hosted zone into the cells. Then press **Update**.

![CreateDomain](/images/2-create-domain-hosted-zone/2-create-domain-hosted-zone-13.png?featherlight=false&width=90pc)

19. Check the email you used to register the domain, if you receive an update confirmation email, you have successfully updated.