architecture-beta
    group vpc(cloud)[AWS Cloud]

    service s3(disk)[S3 Bucket] in vpc
    service cf(cloud)[CloudFront] in vpc
    service r53(internet)[Route 53] in vpc
    service user(internet)[User Browser]

    user:R -- L:r53
    r53:B -- T:cf
    cf:R -- L:s3
