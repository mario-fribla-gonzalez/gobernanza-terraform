# Repositorio de Gobernanza Terraform.

# 🌐 Estructura de Modules de Terraform 
---

### 🔄 Tabla Comparativa GCP → Azure → AWS

| **Categoría** | **GCP** | **Azure** | **AWS** |
|---------------|---------|-----------|---------|
| **🌐 Red** | VPC | VNet | VPC |
| | Subnet | Subnet | Subnet |
| | Firewall | NSG | Security Group |
| | Cloud NAT | NAT Gateway | NAT Gateway |
| | Cloud VPN | VPN Gateway | VPN Connection |
| | Cloud Interconnect | ExpressRoute | Direct Connect |
| | Cloud DNS | Azure DNS | Route53 |
| | Load Balancer | Load Balancer / App Gateway | ALB / NLB |
| **💻 Cómputo** | GCE Instance | VM | EC2 |
| | MIG | VMSS | ASG |
| | GKE | AKS | EKS |
| | Cloud Run | Container Apps | App Runner |
| | Cloud Functions | Functions | Lambda |
| | App Engine | App Service | Elastic Beanstalk |
| **🗄️ DB** | Cloud SQL | SQL Database / PostgreSQL | RDS |
| | Spanner | Cosmos DB (multi-master) | Aurora Global |
| | Bigtable | Cosmos DB (NoSQL) | DynamoDB |
| | Firestore | Cosmos DB (NoSQL) | DynamoDB |
| | Memorystore | Redis Cache | ElastiCache |
| | AlloyDB | PostgreSQL Flexible | Aurora PostgreSQL |
| **💾 Storage** | GCS | Storage Account (Blob) | S3 |
| | Filestore | Azure Files | EFS |
| | Persistent Disk | Managed Disks | EBS |
| **📈 Analytics** | BigQuery | Synapse | Redshift / Athena |
| | Dataflow | Data Factory | Glue |
| | Dataproc | Databricks | EMR |
| | Pub/Sub | Event Hubs / Service Bus | SNS / SQS / EventBridge |
| **🔒 Security** | IAM | Azure AD (RBAC) | IAM |
| | Service Account | Managed Identity | IAM Role |
| | Cloud Armor | WAF Policy | WAF / Shield |
| | Certificate Manager | Key Vault (Certs) | ACM |
| | VPC Service Controls | Private Endpoints | PrivateLink |
| **📋 Governance** | Org Policies | Azure Policy | SCP |
| | Folders | Management Groups | OU |
| | Projects | Subscriptions | Accounts |
| | Budgets | Budgets | Budgets |
| | Billing | Cost Management | Cost Explorer |
| | Tags | Tags | Tags |

---

Mario Fribla

***DevOps***
