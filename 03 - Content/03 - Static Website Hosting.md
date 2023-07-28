---
creation date: July 27th 2023
last modified date: July 27th 2023
aliases: []
tags: #📖
---

Primary Categories: [[02 - Amazon Web Services (AWS)]] 
Secondary Categories: [[01 - Cloud]] | [[000 - Cybersecurity Materials]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - Static Website Hosting]]  

- [x] Buy domain on AWS using Route 53;
- [ ] Create a hosted zone and manage its DNS records;
- [ ] Create S3 Buckets to host website pages;
- [ ] Configure Route 53 to link the domain name to the website;
- [ ] Create an SSL certificate for the website using AWS Certificate Manager (ACM);
- [ ] Create CloudFront distributions to secure the website in HTTPS.

Infrastructure deployed with this project :

![Infrastructure](https://cloudisfree.com/projects/project-1/part-1/images/infrastructure.png)


### Buy domain on AWS using Route 53

This was a pretty easy task, and luckily and kind of funny... iamjoshgilman.com was available. I can now also have the most epic email address - Josh@IAmJoshGilman[.]com

###  Create a hosted zone and manage its DNS records

 What is a hosted zone? 
>*A hosted zone is a container for records, and records contain information about how you want to route traffic for a specific domain, such as example.com, and its subdomains (acme.example.com, zenith.example.com). A hosted zone and the corresponding domain have the same name.*

Luckily for us, registering our domain name through Route 53 automatically gains us a hosted zone so no setup is needed.

### Create S3 Buckets to host website pages

What is a S3 Bucket?
>*An Amazon S3 bucket is a storage space within Amazon's Simple Storage Service (S3) where data is stored as objects (akin to files) in the cloud. Each object consists of a file and optionally any metadata that describes that file. S3 buckets can be uniquely named and configured with rules for storage management and access control for security. They provide high scalability, data availability, and performance for various use-cases such as backup and restore, archive, enterprise applications, IoT devices, and websites.*

We will need to create an S3 Bucket containing the pages of the website, then we will put the Bucket in public to make it accessible to all. We will make two separate S3 Buckets to capture the www name of the website and the www-less of the website, we will **redirect** to the **main Bucket**.

Setting up this Bucket is easy, except we need to make a single change and that exposing it to the internet!

![[Pasted image 20230727215916.png]]



### Configure Route 53 to link the domain name to the website






### Create an SSL certificate for the website using AWS Certificate Manager (ACM)





### Create CloudFront distributions to secure the website in HTTPS




























___

## Resources:

| Hyperlink                                           | Info          |
| --------------------------------------------------- | ------------- |
| https://cloudisfree.com/#/projects/project-1/README | Project guide |
|                                                     |               |


Created Date: July 27th 2023 (09:45 pm) 
Last Modified Date: July 27th 2023 (09:45 pm)
