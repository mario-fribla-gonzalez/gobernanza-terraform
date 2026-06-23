# Repositorio de Gobernanza Terraform.

# 🌐 Estructura de Modules de Terraform 
---

### 🔄 Tabla Comparativa GCP → Azure → AWS → vSphere → Hyper-V

| **Categoría** | **GCP** | **Azure** | **AWS** | **vSphere** | **Hyper-V** |
|---------------|---------|-----------|---------|-------------|-------------|
| **🌐 Red** | VPC | VNet | VPC | Distributed Switch (vDS) | Virtual Switch (External/Internal/Private) |
| | Subnet | Subnet | Subnet | Port Group | VLAN / Port Group |
| | Firewall | NSG | Security Group | Distributed Firewall (NSX) | Windows Firewall / ACLs |
| | Cloud NAT | NAT Gateway | NAT Gateway | NAT / Edge Gateway (NSX) | NAT Switch / Static Mapping |
| | Cloud VPN | VPN Gateway | VPN Connection | | |
| | Cloud Interconnect | ExpressRoute | Direct Connect |
| | Cloud DNS | Azure DNS | Route53 |
| | Load Balancer | Load Balancer / App Gateway | ALB / NLB | NSX Load Balancer | NLB / Load Balancer |
| **💻 Cómputo** | GCE Instance | VM | EC2 | Virtual Machine (VM) | Virtual Machine (Generation 1/2) |
| | GCE Template |  |  | Virtual Template | VM Template / VHD Base |
| | MIG | VMSS | ASG | | Cluster / Resource Pools | VM Cluster / Resource Pools |
| | Sole-Tenant Node | | | Dedicated Host | Dedicated Host |
| | GKE | AKS | EKS | Tanzu Kubernetes Grid (TKG) | Kubernetes en VM (k3s, RKE2) |
| | Cloud Run | Container Apps | App Runner |
| | Cloud Functions | Functions | Lambda |
| | App Engine | App Service | Elastic Beanstalk |
| **🗄️ DB** | Cloud SQL | SQL Database / PostgreSQL | RDS |
| | Spanner | Cosmos DB (multi-master) | Aurora Global |
| | Bigtable | Cosmos DB (NoSQL) | DynamoDB |
| | Firestore | Cosmos DB (NoSQL) | DynamoDB |
| | Memorystore | Redis Cache | ElastiCache |
| | AlloyDB | PostgreSQL Flexible | Aurora PostgreSQL |
| **💾 Storage** | GCS | Storage Account (Blob) | S3 | Datastore (VMFS/NFS/vSAN) | VHD/VHDX (disco virtual) |
| | Persistent Disk | Managed Disks | EBS | Virtual Disk (VMDK) | VHD/VHDX |
| | Backup |  |  | Snapshot / Backup (vADP) | Checkpoints / Backup |
| | Filestore | Azure Files | EFS | NFS Datastore | SMB/File Share |
| **📈 Analytics** | BigQuery | Synapse | Redshift / Athena |
| | Dataflow | Data Factory | Glue |
| | Dataproc | Databricks | EMR |
| | Pub/Sub | Event Hubs / Service Bus | SNS / SQS / EventBridge |
| **🔒 Security** | IAM | Azure AD (RBAC) | IAM | Roles / Permissions | Hyper-V Administrators / Permissions |
| | Service Account | Managed Identity | IAM Role | Service Account (vCenter) | Service Account (Windows) |
| | Cloud Armor | WAF Policy | WAF / Shield | NSX Distributed Firewall | Shielded VMs / Encryption |
| | Certificate Manager | Key Vault (Certs) | ACM | Certificate Manager| Certificados SSL/TLS |
| | VPC Service Controls | Private Endpoints | PrivateLink |
| **📋 Governance** | Org Policies | Azure Policy | SCP |
| | Folders | Management Groups | OU |
| | Projects | Subscriptions | Accounts |
| | Budgets | Budgets | Budgets |
| | Billing | Cost Management | Cost Explorer |
| | Tags | Tags | Tags | Tags / Categories | Tags (Custom Properties) |
| | Organization Policies |  |  | Policies (vCenter) | Local Policies / GPOs |
| **🏗️ Infraestructura** | Project / Organization |  |  | Datacenter / Cluster | Hyper-V Host / Cluster |
| | Folder |  |  | Folder | |
| | Region / Zone |  |  | Cluster / Host | Hyper-V Host |
---

Mario Fribla

***DevOps***
