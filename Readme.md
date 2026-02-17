# AWS Static Website Deployment 🚀

This project demonstrates how to deploy a static website on AWS using:

- Amazon S3 (Static Website Hosting)
- Amazon CloudFront (CDN)
- Amazon Route 53 (DNS Management)
- AWS Certificate Manager (HTTPS)

---

## 🏗 Architecture Overview

```mermaid
graph TD
    User[User Browser] -->|HTTPS| R53[Route 53]
    R53 -->|DNS Alias| CF[CloudFront Distribution]
    CF -->|Origin Access| S3[S3 Bucket]

    subgraph AWS Cloud
        R53
        CF
        S3
    end

