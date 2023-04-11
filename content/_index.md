---
title : "Serverless - Set Up An S3 Static SSL Website"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Serverless - Set Up An S3 Static SSL Website

#### Overview

In this workshop in the serverless series, we will set up website application to be more sercure in transit by using an SSL certificate. An SSL Certificate allows traffic between a user and a website application hosted on an S3 bucket to be encrypted in transit (in-flight encryption).

The architecture of the web application will look like this:
![SeverlessExample](/images/serverless-diagram.png?featherlight=false&width=50pc)

- Creating and management a SSL certificate with AWS Certificate Manager.
- Setting up a custom domain together with Route 53 DNS
- Creating a CloudFront CDN, linking it with our custom domain via Route 53, and securing the whole connection using an SSL certificate


#### Content

 1. [Preparation](1-preparation/)
 2. [Create Domain and Hosted zone](2-create-domain-hosted-zone/)
 3. [Request SSL certificate](3-request-certificate/)
 4. [Create CloudFront distribution](4-create-cloud-front/)
 5. [Cleanup](5-cleanup)
