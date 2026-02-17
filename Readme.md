graph TD
    User([User Browser]) -- "HTTPS" --> R53{Route 53}
    R53 -- "DNS Alias" --> CF[CloudFront Distribution]
    CF -- "S3 Origin Access" --> S3[(S3 Bucket)]

    subgraph AWS_Cloud [AWS Global Infrastructure]
        R53
        CF
        S3
    end

    style AWS_Cloud fill:#f9f,stroke:#333,stroke-width:2px
    style CF fill:#ff9900,color:#fff
    style S3 fill:#ff9900,color:#fff
