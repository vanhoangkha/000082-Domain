---
title : "Create ClodFront distribution"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Open [Amazon CloudFront console](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-southeast-1#/distributions)

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-1.png?featherlight=false&width=90pc)

2. Click **Create distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-2.png?featherlight=false&width=90pc)

3. Select the origin domain is **fcj-book-store** bucket

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-3.png?featherlight=false&width=90pc)

4. Select **Legacy access identities** to just allow access to the S3 bucket from CloudFront 
- Click **Create new OAI**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-4.png?featherlight=false&width=90pc)

- Click **Create**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-5.png?featherlight=false&width=90pc)

- Select OAI you just created
- Select **Yes, update the bucket policy**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-4-1.png?featherlight=false&width=90pc)

5. Scroll down, in **Default cache behavior** section, select **Redirect HTTP to HTTPS** for **Viewer protocol policy**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-6.png?featherlight=false&width=90pc)

6. Scroll down, in **Settings** section, click **Add item**
- Enter CNAME: `www.fcjbookstore.click` and `fcjbookstore.click`
- Select the SSL certificate you created in previous step

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-7.png?featherlight=false&width=90pc)

7. Scroll down to bottom, enter **index.html** for **Default root object** pattern
- Click **Create distribution**

![CreateDistribution](/images/4-create-cloud-front/4-create-cloud-front-8.png?featherlight=false&width=90pc)

8. Go back to the Route 53 console 
- Click **Create record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-9.png?featherlight=false&width=90pc)

9. Enter `www` for **Record name**
- Turn on **Alias**
- Select **Alias to CloudFront distribution**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-10.png?featherlight=false&width=90pc)

10. Select the newly created CloudFront distribution
- Click **Create records**
![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-11.png?featherlight=false&width=90pc)

11. Click **Create record**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-12.png?featherlight=false&width=90pc)

12. Turn on **Alias**
- Select **Alias to CloudFront distribution**
- Select the newly created CloudFront distribution
- Click **Create records**

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-13.png?featherlight=false&width=90pc)

13. Enter the following links in a new tab in your web browser: `http://DOMAIN`, `http://www.DOMAIN`, replace all **DOMAIN** with your domain name. All those links redirect to the new path, replace http with https

![CreateRecord](/images/4-create-cloud-front/4-create-cloud-front-14.png?featherlight=false&width=90pc)
