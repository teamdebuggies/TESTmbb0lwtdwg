graph TD
    A[VPC]
    A --> B[Public Subnet]
    A --> C[Private Subnet]
    B -->|Internet Gateway| D[Load Balancer]
    D --> E[Web Application Servers (EC2)]
    C --> F[Microservices (ECS)]
    C --> G[Database (RDS)]
    C --> H[Cache (ElastiCache)]
    I[Security Group] --> E
    I --> F
    I --> G
    I --> H
    J[IAM Role] --> E
    J --> F
    J --> G
    J --> H
    K[CI/CD Pipeline] --> L[GitHub Actions]
    L -->|Build| M[Container Registry]
    L -->|Deploy| F