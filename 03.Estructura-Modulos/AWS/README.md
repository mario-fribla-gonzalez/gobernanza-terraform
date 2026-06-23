# Repostorio de Gobernanza Terraform.

## Amazon Web Services (AWS), estructura del directorio de modulos de Terraform.

La siguiente estructura de directorios representa como se desea reflejar en este respositorio y como haremos referencia posteriormente en las practicas a esta estructura.

Cada directorio, tendrá como mínimo estos archivos obligatorios y otros opcionales de Terraform:
```text
- main.tf                 # (obligatorio)
- outputs.tf              # (obligatorio)
- variables.tf            # (obligatorio)
- backend.tf              # (opcional)
- locals.tf               # (opcional)
- providers.tf            # (opcional)
```

También en algunos directorios opcionales como: 

```text
 ├── templates/ 
 ├── format/
 ├── resource/
```
---

```text
 aprende-gobernanza-terraform/
 │
 ├── terraform/
 │   │
 │   ├── aws/
 │   │   ├── modules/
 │   │   │   │
 │   │   │   ├── networking/                      # 🌐 Redes y conectividad
 │   │   │   │    ├── vpc/                          # Virtual Private Cloud (VPC)
 │   │   │   │    ├── subnet/                       # Subredes (públicas, privadas, aisladas)
 │   │   │   │    ├── internet-gateway/             # Internet Gateway (IGW)
 │   │   │   │    ├── nat-gateway/                  # NAT Gateway (en subred pública)
 │   │   │   │    ├── nat-instance/                 # NAT Instance (EC2 con NAT)
 │   │   │   │    ├── egress-only-gateway/          # Egress-Only Gateway (IPv6)
 │   │   │   │    ├── vpn-connection/               # VPN (Site-to-Site, Client)
 │   │   │   │    ├── transit-gateway/              # Transit Gateway (hub de red)
 │   │   │   │    ├── direct-connect/               # Direct Connect (conexión dedicada)
 │   │   │   │    ├── route53/                      # Route53 (DNS, zonas, registros)
 │   │   │   │    ├── route53-resolver/             # Route53 Resolver (DNS híbrido)
 │   │   │   │    ├── privatelink/                  # PrivateLink (Endpoint Services)
 │   │   │   │    ├── vpc-endpoint/                 # VPC Endpoints (Gateway/Interface)
 │   │   │   │    ├── vpc-peering/                  # VPC Peering
 │   │   │   │    ├── network-acl/                  # Network ACLs (subnet-level firewall)
 │   │   │   │    ├── security-group/               # Security Groups (instance-level firewall)
 │   │   │   │    ├── elastic-ip/                   # Elastic IP (EIP)
 │   │   │   │    ├── elastic-network-interface/    # Elastic Network Interface (ENI) ⚠️
 │   │   │   │    ├── load-balancer/                # Load Balancer (ver load-balancing/)
 │   │   │   │    ├── cloudfront/                   # CloudFront (CDN global)
 │   │   │   │    ├── global-accelerator/           # Global Accelerator (anycast IPs) ⚠️
 │   │   │   │    └── api-gateway/                  # API Gateway (ver integration/)
 │   │   │   ├── compute/                         # 💻 Cómputo
 │   │   │   │   ├── ec2-instance/                  # EC2 Instance (VM individual)
 │   │   │   │   ├── ec2-template/                  # Launch Template (plantilla de instancia)
 │   │   │   │   ├── asg/                           # Auto Scaling Group
 │   │   │   │   ├── launch-configuration/          # Launch Configuration (legacy)
 │   │   │   │   ├── spot-instance/                 # Spot Instance (instancias spot)
 │   │   │   │   ├── dedicated-host/                # Dedicated Host
 │   │   │   │   ├── capacity-reservation/          # Capacity Reservation
 │   │   │   │   ├── eks-cluster/                   # Amazon EKS (Kubernetes)
 │   │   │   │   ├── eks-nodegroup/                 # EKS Node Group
 │   │   │   │   ├── eks-fargate/                   # EKS Fargate (serverless K8s)
 │   │   │   │   ├── ecs-cluster/                   # Amazon ECS (Elastic Container Service)
 │   │   │   │   ├── ecs-service/                   # ECS Service (Fargate/EC2)
 │   │   │   │   ├── ecs-task/                      # ECS Task Definition
 │   │   │   │   ├── ecs-capacity-provider/         # ECS Capacity Provider
 │   │   │   │   ├── lambda/                        # AWS Lambda (serverless functions)
 │   │   │   │   ├── batch/                         # AWS Batch (HPC, batch jobs)
 │   │   │   │   ├── elastic-beanstalk/             # Elastic Beanstalk (PaaS)
 │   │   │   │   ├── lightsail/                     # Lightsail (simple VPS)
 │   │   │   │   ├── outposts/                      # AWS Outposts (on-premise)
 │   │   │   │   └── vmware-cloud/                  # VMware Cloud on AWS
 │   │   │   ├── paas/                            # 🚀 Plataforma como Servicio
 │   │   │   │   ├── elastic-beanstalk/             # Elastic Beanstalk
 │   │   │   │   ├── apprunner/                     # App Runner (containerized apps)
 │   │   │   │   ├── amplify/                       # Amplify (web/mobile apps)
 │   │   │   │   ├── lambda/                        # Lambda (serverless functions)
 │   │   │   │   ├── api-gateway/                   # API Gateway (REST/WebSocket)
 │   │   │   │   ├── step-functions/                # Step Functions (workflows)
 │   │   │   │   ├── sns/                           # SNS (Simple Notification Service)
 │   │   │   │   ├── sqs/                           # SQS (Simple Queue Service)
 │   │   │   │   ├── eventbridge/                   # EventBridge (event bus) ⚠️
 │   │   │   │   ├── mq/                            # Amazon MQ (message broker)
 │   │   │   │   ├── appflow/                       # AppFlow (SaaS integration) ⚠️
 │   │   │   │   ├── pinpoint/                      # Pinpoint (engagement) ⚠️
 │   │   │   │   ├── connect/                       # Connect (contact center) ⚠️
 │   │   │   │   ├── chatbot/                       # Lex/Connect Chatbot ⚠️
 │   │   │   │   └── rekognition/                   # Rekognition (AI/ML vision) ⚠️
 │   │   │   ├── database/                        # 🗄️ Bases de Datos
 │   │   │   │   ├── rds/                           # RDS (MySQL, PG, Oracle, SQL Server)
 │   │   │   │   ├── rds-proxy/                     # RDS Proxy (connection pooling)
 │   │   │   │   ├── aurora/                        # Aurora (MySQL/PG compatible)
 │   │   │   │   ├── aurora-serverless/             # Aurora Serverless
 │   │   │   │   ├── dynamodb/                      # DynamoDB (NoSQL)
 │   │   │   │   ├── dynamodb-table/                # DynamoDB Table
 │   │   │   │   ├── dynamodb-streams/              # DynamoDB Streams
 │   │   │   │   ├── elasticache/                   # ElastiCache (Redis, Memcached)
 │   │   │   │   ├── redshift/                      # Redshift (Data Warehouse)
 │   │   │   │   ├── redshift-serverless/           # Redshift Serverless
 │   │   │   │   ├── documentdb/                    # DocumentDB (MongoDB compatible)
 │   │   │   │   ├── keyspaces/                     # Keyspaces (Cassandra compatible)
 │   │   │   │   ├── neptune/                       # Neptune (Graph DB)
 │   │   │   │   ├── timestream/                    # Timestream (Time Series DB)
 │   │   │   │   ├── qldb/                          # QLDB (Ledger DB)
 │   │   │   │   ├── dms/                           # DMS (Database Migration Service)
 │   │   │   │   ├── rds-snapshot/                  # RDS Snapshot
 │   │   │   │   └── database-migration/            # Database Migration (ver dms/)
 │   │   │   ├── load-balancing/                  # ⚖️ Balanceo de Carga
 │   │   │   │   ├── alb/                           # Application Load Balancer (L7)
 │   │   │   │   ├── nlb/                           # Network Load Balancer (L4)
 │   │   │   │   ├── gwlb/                          # Gateway Load Balancer (L3/GW)
 │   │   │   │   ├── target-group/                  # Target Groups (backends)
 │   │   │   │   ├── alb-listener/                  # ALB Listener (HTTP/HTTPS)
 │   │   │   │   ├── nlb-listener/                  # NLB Listener (TCP/UDP/TLS)
 │   │   │   │   ├── alb-rule/                      # ALB Rules (path/host routing)
 │   │   │   │   ├── cloudfront/                    # CloudFront (global CDN)
 │   │   │   │   ├── global-accelerator/            # Global Accelerator (anycast)
 │   │   │   │   ├── route53/                       # Route53 (DNS-based routing)
 │   │   │   │   └── api-gateway/                   # API Gateway (REST/HTTP/WebSocket)
 │   │   │   ├── security/                        # 🔒 Seguridad
 │   │   │   │   ├── iam/                           # IAM (Users, Groups, Roles, Policies)
 │   │   │   │   ├── iam-role/                      # IAM Role
 │   │   │   │   ├── iam-policy/                    # IAM Policy (inline/managed)
 │   │   │   │   ├── iam-user/                      # IAM User
 │   │   │   │   ├── iam-group/                     # IAM Group
 │   │   │   │   ├── iam-instance-profile/          # Instance Profile (EC2 IAM roles)
 │   │   │   │   ├── secrets-manager/               # Secrets Manager
 │   │   │   │   ├── parameter-store/               # Parameter Store (SSM)
 │   │   │   │   ├── kms/                           # KMS (Key Management Service)
 │   │   │   │   ├── certificate-manager/           # ACM (Certificate Manager)
 │   │   │   │   ├── waf/                           # WAF (Web Application Firewall)
 │   │   │   │   ├── wafv2/                         # WAF v2
 │   │   │   │   ├── shield/                        # Shield (DDoS Protection)
 │   │   │   │   ├── firewall/                      # Network Firewall
 │   │   │   │   ├── guardduty/                     # GuardDuty (threat detection)
 │   │   │   │   ├── inspector/                     # Inspector (vulnerability)
 │   │   │   │   ├── macie/                         # Macie (data discovery)
 │   │   │   │   ├── security-hub/                  # Security Hub
 │   │   │   │   ├── detective/                     # Detective (investigation)
 │   │   │   │   ├── config/                        # AWS Config (compliance)
 │   │   │   │   ├── cloudtrail/                    # CloudTrail (audit logging)
 │   │   │   │   ├── organizations/                 # Organizations (multi-account)
 │   │   │   │   ├── sso/                           # AWS SSO (identity federation)
 │   │   │   │   ├── cognito/                       # Cognito (user pools, identity pools)
 │   │   │   │   ├── access-analyzer/               # Access Analyzer
 │   │   │   │   ├── vpc-endpoint/                  # VPC Endpoints (PrivateLink)
 │   │   │   │   └── security-group/                # Security Groups (instance firewall)
 │   │   │   ├── storage/                         # 💾 Almacenamiento
 │   │   │   │   ├── s3-bucket/                     # S3 Bucket (object storage)
 │   │   │   │   ├── s3-object/                     # S3 Object (individual files)
 │   │   │   │   ├── s3-replication/                # S3 Replication
 │   │   │   │   ├── s3-lifecycle/                  # S3 Lifecycle Rules
 │   │   │   │   ├── s3-website/                    # S3 Static Website
 │   │   │   │   ├── ebs-volume/                    # EBS Volume (block storage)
 │   │   │   │   ├── ebs-snapshot/                  # EBS Snapshot ⚠️
 │   │   │   │   ├── efs/                           # EFS (Elastic File System, NFS) ⚠️
 │   │   │   │   ├── fsx/                           # FSx (Windows, Lustre, OpenZFS) ⚠️
 │   │   │   │   ├── storage-gateway/               # Storage Gateway (hybrid) ⚠️
 │   │   │   │   ├── glacier/                       # Glacier (archival storage) ⚠️
 │   │   │   │   ├── backup/                        # AWS Backup
 │   │   │   │   ├── backup-plan/                   # Backup Plan
 │   │   │   │   ├── datasync/                      # DataSync (data transfer)
 │   │   │   │   ├── snow-family/                   # Snow Family (edge/offline)
 │   │   │   │   └── transfer-family/               # Transfer Family (SFTP, FTPS, FTP)
 │   │   │   ├── data/                            # 📈 Data & Analytics
 │   │   │   │   ├── s3/                            # S3 (data lake)
 │   │   │   │   ├── athena/                        # Athena (SQL queries on S3)
 │   │   │   │   ├── glue/                          # Glue (ETL, catalog, crawlers)
 │   │   │   │   ├── redshift/                      # Redshift (data warehouse)
 │   │   │   │   ├── redshift-spectrum/             # Redshift Spectrum (S3 queries)
 │   │   │   │   ├── emr/                           # EMR (Spark, Hadoop, Hive)
 │   │   │   │   ├── kinesis/                       # Kinesis (streaming)
 │   │   │   │   ├── kinesis-firehose/              # Kinesis Firehose (delivery)
 │   │   │   │   ├── kinesis-analytics/             # Kinesis Analytics (SQL on streams)
 │   │   │   │   ├── msk/                           # Managed Streaming for Kafka (MSK)
 │   │   │   │   ├── quicksight/                    # QuickSight (BI dashboards)
 │   │   │   │   ├── data-pipeline/                 # Data Pipeline (orchestration)
 │   │   │   │   ├── lake-formation/                # Lake Formation (data lake)
 │   │   │   │   ├── sagemaker/                     # SageMaker (ML platform)
 │   │   │   │   ├── ground-truth/                  # Ground Truth (data labeling)
 │   │   │   │   ├── comprehend/                    # Comprehend (NLP)
 │   │   │   │   └── forecast/                      # Forecast (time-series prediction)
 │   │   │   ├── integration/                     # 🔌 Integración
 │   │   │   │   ├── api-gateway/                   # API Gateway
 │   │   │   │   ├── appsync/                       # AppSync (GraphQL)
 │   │   │   │   ├── step-functions/                # Step Functions
 │   │   │   │   ├── sns/                           # SNS (pub/sub)
 │   │   │   │   ├── sqs/                           # SQS (queue)
 │   │   │   │   ├── eventbridge/                   # EventBridge (event bus)
 │   │   │   │   ├── mq/                            # MQ (message broker)
 │   │   │   │   ├── appflow/                       # AppFlow (SaaS integration)
 │   │   │   │   ├── codebuild/                     # CodeBuild (CI)
 │   │   │   │   ├── codepipeline/                  # CodePipeline (CI/CD)
 │   │   │   │   ├── codedeploy/                    # CodeDeploy (deployment)
 │   │   │   │   ├── codecommit/                    # CodeCommit (Git repos)
 │   │   │   │   ├── codeartifact/                  # CodeArtifact (artifact repo)
 │   │   │   │   ├── ecr/                           # ECR (Container Registry)
 │   │   │   │   ├── ecr-public/                    # ECR Public (public images)
 │   │   │   │   ├── codeguru/                      # CodeGuru (code review)
 │   │   │   │   └── cloud9/                        # Cloud9 (IDE in cloud)
 │   │   │   ├── migration/                       # 🚚 Migración
 │   │   │   │   ├── dms/                           # DMS (Database Migration)
 │   │   │   │   ├── sms/                           # SMS (Server Migration)
 │   │   │   │   ├── mighub/                        # Migration Hub
 │   │   │   │   ├── datasync/                      # DataSync (data migration)
 │   │   │   │   ├── transfer-family/               # Transfer Family (SFTP)
 │   │   │   │   ├── application-migration/         # Application Migration Service (MGN) ⚠️
 │   │   │   │   ├── snow-family/                   # Snow Family (offline) ⚠️
 │   │   │   │   ├── storage-gateway/               # Storage Gateway (hybrid) ⚠️
 │   │   │   │   ├── s3-transfer/                   # S3 Transfer Acceleration
 │   │   │   │   └── cloud-endure/                  # CloudEndure (DR/migration)  ⚠️
 │   │   │   ├── governance/                      # 📋 Gobernanza
 │   │   │   │   ├── organizations/                 # Organizations (multi-account)
 │   │   │   │   ├── scp/                           # Service Control Policies (SCP)  ⚠️
 │   │   │   │   ├── accounts/                      # Accounts (creation, management)
 │   │   │   │   ├── ou/                            # Organizational Units (OU)  ⚠️
 │   │   │   │   ├── config/                        # AWS Config (compliance) ⚠️
 │   │   │   │   ├── config-rule/                   # Config Rules
 │   │   │   │   ├── config-agg/                    # Config Aggregator
 │   │   │   │   ├── cloudtrail/                    # CloudTrail (audit)
 │   │   │   │   ├── cloudwatch/                    # CloudWatch (monitoring)
 │   │   │   │   ├── cloudwatch-alarm/              # CloudWatch Alarms
 │   │   │   │   ├── cloudwatch-dashboard/          # CloudWatch Dashboards  ⚠️
 │   │   │   │   ├── cloudwatch-logs/               # CloudWatch Logs
 │   │   │   │   ├── cloudwatch-metrics/            # CloudWatch Metrics
 │   │   │   │   ├── budget/                        # AWS Budgets
 │   │   │   │   ├── cost-explorer/                 # Cost Explorer
 │   │   │   │   ├── cost-usage-report/             # Cost and Usage Report (CUR)  ⚠️
 │   │   │   │   ├── tags/                          # Resource Tags
 │   │   │   │   ├── service-catalog/               # Service Catalog
 │   │   │   │   ├── control-tower/                 # Control Tower (landing zone)
 │   │   │   │   ├── resource-groups/               # Resource Groups
 │   │   │   │   └── resource-locks/                # Resource Locks (prevent deletion) ⚠️
 │   │   │   └── hybrid/                          # 🔄 Híbrido
 │   │   │       ├── outposts/                      # AWS Outposts (on-premise) ⚠️
 │   │   │       ├── storage-gateway/               # Storage Gateway (hybrid) ⚠️
 │   │   │       ├── snow-family/                   # Snow Family (edge) ⚠️
 │   │   │       ├── iot-core/                      # IoT Core (devices) ⚠️
 │   │   │       ├── iot-greengrass/                # Greengrass (edge computing) ⚠️
 │   │   │       ├── iot-analytics/                 # IoT Analytics ⚠️
 │   │   │       ├── iot-events/                    # IoT Events ⚠️
 │   │   │       ├── iot-sitewise/                  # IoT SiteWise (industrial) ⚠️
 │   │   │       ├── direct-connect/                # Direct Connect
 │   │   │       ├── vpn-connection/                # VPN
 │   │   │       ├── transit-gateway/               # Transit Gateway 
 │   │   │       ├── route53-resolver/              # Route53 Resolver (hybrid DNS) ⚠️
 │   │   │       ├── app-mesh/                      # App Mesh (service mesh) ⚠️
 │   │   │       ├── cloud-map/                     # Cloud Map (service discovery) ⚠️
 │   │   │       └── wafv2/                         # WAF v2 (edge security) ⚠️
```
---
### Declaración

Los directorios de estos modulos se complementaran con el tiempo, si usted considera que puede ser un aportar en unos de estos modules, contacteme.

Los directorios que esten para su referencia, en este readme se indocaran con un ✅ y aquellos que se desconoce si se implementaran con ⚠️.

---

Mario Fribla

***DevOps***
