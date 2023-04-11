---
title : "Create CloudFront Distribution"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Open [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/)
2. Click **Create distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-1.png?featherlight=false&width=90pc)

3. Select the origin domain is **fcjdmswebstore** bucket, then click **Use website endpoint**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-2.png?featherlight=false&width=90pc)


4. Scroll down, in **Default cache behavior** section, select **Redirect HTTP to HTTPS** for **Viewer protocol policy**
5. Select **CORS-S3Origin** for **Origin request policy** part

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-3.png?featherlight=false&width=90pc)

6. Scroll down, in **Settings** section, click **Add item**
- Enter CNAME: `www.fcjdms.click` and `fcjdms.click`
- Select the SSL certificate you created in previous step

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-4.png?featherlight=false&width=90pc)

7. Scroll down to bottom, enter **index.html** for **Default root object** pattern
- Click **Create distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-5.png?featherlight=false&width=90pc)

8. Go back to the Route 53 console
- Select **Hosted zone** in the left menu and select the created hosted zone.
- Click **Create record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-6.png?featherlight=false&width=90pc)

9. Turn on **Alias**
10. Select **Alias to CloudFront distribution**
- Select the newly created CloudFront distribution
- Click **Add another record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-7.png?featherlight=false&width=90pc)


11. Enter `www` for record name.
- Turn on **Alias**
- Select **Alias to CloudFront distribution**
- Select the newly created CloudFront distribution
- Click **Create records**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-12.png?featherlight=false&width=90pc)

12. You have created the records for CloudFront distribution.

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-9.png?featherlight=false&width=90pc)

13. Enter the following links in a new tab in your web browser: `http://DOMAIN`, `http://www.DOMAIN`, replace all `DOMAIN` with your domain name. All those links redirect to the new path, replace http with https.

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-10.png?featherlight=false&width=90pc)

You have completed the workshop to make the application more secure. In the next workshop, we will implement the search feature with Amazon OpenSearch Service for the application.