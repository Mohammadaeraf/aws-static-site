# ☁️ AWS Responsive Static Portfolio
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![CloudFront](https://img.shields.io/badge/CloudFront-Secure-blue?style=for-the-badge&logo=amazon-cloudfront&logoColor=white)
![Linux](https://img.shields.io/badge/MX_Linux-A81D33?style=for-the-badge&logo=debian&logoColor=white)

A high-availability portfolio website architected using the AWS Global Infrastructure and optimized for all devices.

## 🚀 Live Demo
**[Click Here to Visit the Site](https://drb1333ec2o5.cloudfront.net)**

## 🏗️ Architecture Diagram
This diagram shows the secure flow from the user to the content hosted on AWS.

```mermaid
architecture-beta
    group vpc(cloud)[AWS Cloud]

    service s3(disk)[S3 Bucket] in vpc
    service cf(cloud)[CloudFront] in vpc
    service r53(internet)[Route 53] in vpc
    service user(internet)[User Browser]

    user -- "HTTPS Request" --> r53
    r53 -- "DNS Alias" --> cf
    cf -- "OAC Auth" --> s3
