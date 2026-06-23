# Repostorio de Gobernanza Terraform.

## Microsoft Azure, estructura del directorio de modulos de Terraform.

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
 │   ├── azure/
 │   │   ├── modules/
 │   │   │   │
 │   │   │   ├── networking/                      # 🌐 Redes y conectividad
 │   │   │   │    ├── vnet/                         # Virtual Network (VNet)
 │   │   │   │    ├── subnet/                       # Subredes
 │   │   │   │    ├── nsg/                          # Network Security Groups (Firewall)
 │   │   │   │    ├── asg/                          # Application Security Groups
 │   │   │   │    ├── nat-gateway/                  # NAT Gateway
 │   │   │   │    ├── vpn-gateway/                  # VPN Gateway (Site-to-Site, P2S)
 │   │   │   │    ├── express-route/                # ExpressRoute (conexión dedicada)
 │   │   │   │    ├── dns/                          # Azure DNS (zonas, registros)
 │   │   │   │    ├── private-dns/                  # Private DNS Zones
 │   │   │   │    ├── load-balancer/                # Load Balancer (ver load-balancing/)
 │   │   │   │    ├── application-gateway/          # Application Gateway (WAF)
 │   │   │   │    ├── front-door/                   # Azure Front Door (CDN global)
 │   │   │   │    ├── cdn/                          # Azure CDN
 │   │   │   │    ├── traffic-manager/              # Traffic Manager (DNS routing)
 │   │   │   │    └── bastion/                      # Azure Bastion (SSH/RDP sin IP pública)
 │   │   │   ├── compute/                         # 💻 Cómputo
 │   │   │   │   ├── vm/                            # Virtual Machine (VM individual)
 │   │   │   │   ├── vm-scale-set/                  # Virtual Machine Scale Set (VMSS)
 │   │   │   │   ├── availability-set/              # Availability Set
 │   │   │   │   ├── proximity-placement/           # Proximity Placement Groups
 │   │   │   │   ├── dedicated-host/                # Dedicated Host
 │   │   │   │   ├── aks-cluster/                   # Azure Kubernetes Service (AKS)
 │   │   │   │   ├── aks-nodepool/                  # AKS Node Pool
 │   │   │   │   ├── container-apps/                # Container Apps (serverless containers)
 │   │   │   │   ├── container-instances/           # Container Instances (ACI)
 │   │   │   │   ├── app-service/                   # App Service (Web Apps)
 │   │   │   │   ├── app-service-plan/              # App Service Plan
 │   │   │   │   ├── functions/                     # Azure Functions (serverless)
 │   │   │   │   ├── logic-apps/                    # Logic Apps (workflow automation)
 │   │   │   │   ├── batch/                         # Azure Batch (HPC)
 │   │   │   │   └── vmware-solution/               # Azure VMware Solution (AVS)
 │   │   │   ├── paas/                            # 🚀 Plataforma como Servicio
 │   │   │   │   ├── app-service/                   # App Service (Web Apps, API Apps)
 │   │   │   │   ├── functions/                     # Azure Functions
 │   │   │   │   ├── container-apps/                # Container Apps
 │   │   │   │   ├── container-instances/           # Container Instances
 │   │   │   │   ├── logic-apps/                    # Logic Apps
 │   │   │   │   ├── api-management/                # API Management
 │   │   │   │   ├── signalr/                       # SignalR Service (real-time)
 │   │   │   │   ├── notification-hubs/             # Notification Hubs ⚠️
 │   │   │   │   ├── event-grid/                    # Event Grid (event routing) ⚠️
 │   │   │   │   ├── service-bus/                   # Service Bus (message queue)
 │   │   │   │   └── cognitive-services/            # Cognitive Services (AI/ML APIs) ⚠️
 │   │   │   ├── database/                        # 🗄️ Bases de Datos
 │   │   │   │   ├── sql-server/                    # SQL Server (IaaS)
 │   │   │   │   ├── sql-database/                  # SQL Database (PaaS)
 │   │   │   │   ├── sql-managed-instance/          # SQL Managed Instance
 │   │   │   │   ├── postgresql/                    # PostgreSQL (Flexible Server)
 │   │   │   │   ├── mysql/                         # MySQL (Flexible Server)
 │   │   │   │   ├── mariadb/                       # MariaDB
 │   │   │   │   ├── cosmosdb/                      # Cosmos DB (NoSQL, MongoDB, etc.)
 │   │   │   │   ├── redis-cache/                   # Azure Cache for Redis
 │   │   │   │   ├── storage-account/               # Storage Account (blob, file, queue, table)
 │   │   │   │   ├── data-lake/                     # Data Lake Storage Gen2
 │   │   │   │   ├── synapse/                       # Azure Synapse Analytics
 │   │   │   │   ├── elastic-pool/                  # Elastic Pool (SQL) ⚠️
 │   │   │   │   ├── managed-database/              # Managed Database (general) ⚠️
 │   │   │   │   └── database-migration/            # Database Migration Service ⚠️
 │   │   │   ├── load-balancing/                  # ⚖️ Balanceo de Carga
 │   │   │   │   ├── lb-public/                     # Public Load Balancer
 │   │   │   │   ├── lb-internal/                   # Internal Load Balancer
 │   │   │   │   ├── app-gateway/                   # Application Gateway (L7)
 │   │   │   │   ├── front-door/                    # Front Door (global L7)
 │   │   │   │   ├── traffic-manager/               # Traffic Manager (DNS routing)
 │   │   │   │   ├── cdn/                           # CDN (content delivery)
 │   │   │   │   ├── backend-pool/                  # Backend pools para LB/AG
 │   │   │   │   ├── health-probe/                  # Health probes ⚠️
 │   │   │   │   └── load-balancer-rules/           # Load balancing rules
 │   │   │   ├── security/                        # 🔒 Seguridad
 │   │   │   │   ├── azure-ad/                      # Azure AD (Entra ID)
 │   │   │   │   ├── role-assignments/              # RBAC (Role Assignments)
 │   │   │   │   ├── managed-identity/              # Managed Identities
 │   │   │   │   ├── service-principal/             # Service Principals
 │   │   │   │   ├── key-vault/                     # Key Vault (secrets, keys, certs)
 │   │   │   │   ├── key-vault-access/              # Key Vault Access Policies
 │   │   │   │   ├── private-endpoint/              # Private Endpoints
 │   │   │   │   ├── private-link/                  # Private Link Service
 │   │   │   │   ├── azure-policy/                  # Azure Policy (governance) ⚠️
 │   │   │   │   ├── azure-blueprints/              # Blueprints (compliance) ⚠️
 │   │   │   │   ├── security-center/               # Microsoft Defender for Cloud ⚠️
 │   │   │   │   ├── sentinel/                      # Azure Sentinel (SIEM) ⚠️
 │   │   │   │   ├── waf-policy/                    # WAF Policy (Application Gateway)
 │   │   │   │   ├── firewall/                      # Azure Firewall
 │   │   │   │   ├── ddos-protection/               # DDoS Protection Plan
 │   │   │   │   ├── azure-ad-b2c/                  # Azure AD B2C ⚠️
 │   │   │   │   └── conditional-access/            # Conditional Access Policies ⚠️
 │   │   │   ├── storage/                         # 💾 Almacenamiento
 │   │   │   │   ├── storage-account/               # Storage Account (general)
 │   │   │   │   ├── blob-container/                # Blob Containers
 │   │   │   │   ├── file-share/                    # File Shares (SMB)
 │   │   │   │   ├── queue/                         # Queue Storage
 │   │   │   │   ├── table/                         # Table Storage
 │   │   │   │   ├── data-lake/                     # Data Lake Storage Gen2
 │   │   │   │   ├── managed-disk/                  # Managed Disks (VM)
 │   │   │   │   ├── snapshot/                      # Disk Snapshots ⚠️
 │   │   │   │   ├── backup-vault/                  # Backup Vault
 │   │   │   │   ├── backup-policy/                 # Backup Policies
 │   │   │   │   ├── site-recovery/                 # Azure Site Recovery (DR)
 │   │   │   │   ├── storage-sync/                  # Azure File Sync
 │   │   │   │   ├── databox/                       # Azure Data Box (offline transfer) ⚠️
 │   │   │   │   └── import-export/                 # Import/Export Service ⚠️
 │   │   │   ├── data/                            # 📈 Data & Analytics
 │   │   │   │   ├── sql-database/                  # SQL Database
 │   │   │   │   ├── synapse/                       # Azure Synapse (data warehouse) ⚠️
 │   │   │   │   ├── databricks/                    # Azure Databricks (Spark) ⚠️
 │   │   │   │   ├── data-factory/                  # Data Factory (ETL/ELT)
 │   │   │   │   ├── event-hubs/                    # Event Hubs (streaming) ⚠️
 │   │   │   │   ├── iot-hub/                       # IoT Hub ⚠️
 │   │   │   │   ├── stream-analytics/              # Stream Analytics ⚠️
 │   │   │   │   ├── data-lake/                     # Data Lake Storage
 │   │   │   │   ├── data-explorer/                 # Data Explorer (Kusto)
 │   │   │   │   ├── purview/                       # Microsoft Purview (data governance) ⚠️
 │   │   │   │   ├── analytics/                     # Log Analytics Workspace ⚠️
 │   │   │   │   └── power-bi/                      # Power BI Embedded
 │   │   │   ├── integration/                       # 🔌 Integración
 │   │   │   │   ├── api-management/                # API Management
 │   │   │   │   ├── logic-apps/                    # Logic Apps
 │   │   │   │   ├── event-grid/                    # Event Grid
 │   │   │   │   ├── service-bus/                   # Service Bus
 │   │   │   │   ├── event-hubs/                    # Event Hubs
 │   │   │   │   ├── data-factory/                  # Data Factory
 │   │   │   │   ├── synapse/                       # Synapse Pipelines
 │   │   │   │   ├── devops/                        # Azure DevOps (pipelines, repos)
 │   │   │   │   ├── github-actions/                # GitHub Actions integration
 │   │   │   │   ├── container-registry/            # Container Registry (ACR)
 │   │   │   │   ├── container-instances/           # Container Instances
 │   │   │   │   └── web-apps/                      # Web Apps (deployment slots)
 │   │   │   ├── migration/                       # 🚚 Migración
 │   │   │   │   ├── azure-migrate/                 # Azure Migrate (discovery/assessment)
 │   │   │   │   ├── dms/                           # Database Migration Service
 │   │   │   │   ├── data-box/                      # Data Box (offline migration)
 │   │   │   │   ├── site-recovery/                 # Site Recovery (DR, migration)
 │   │   │   │   ├── storage-mover/                 # Storage Mover (file migration)
 │   │   │   │   ├── app-service-migration/         # App Service Migration Assistant
 │   │   │   │   └── cosmos-migration/              # Cosmos DB Migration (Mongo, etc.)
 │   │   │   ├── governance/                      # 📋 Gobernanza
 │   │   │   │   ├── management-group/              # Management Groups (jerarquía)
 │   │   │   │   ├── subscription/                  # Subscriptions (creación, configuración)
 │   │   │   │   ├── resource-group/                # Resource Groups
 │   │   │   │   ├── policy/                        # Azure Policy (definiciones, asignaciones)
 │   │   │   │   ├── initiative/                    # Policy Initiatives (sets)
 │   │   │   │   ├── blueprint/                     # Blueprints (compliance)
 │   │   │   │   ├── tags/                          # Resource Tags
 │   │   │   │   ├── budget/                        # Budgets and alerts
 │   │   │   │   ├── cost-management/               # Cost Management (exports, views)
 │   │   │   │   ├── advisor/                       # Azure Advisor (recommendations)
 │   │   │   │   ├── monitor/                       # Azure Monitor (alerts, metrics)
 │   │   │   │   ├── log-analytics/                 # Log Analytics Workspace
 │   │   │   │   ├── application-insights/          # Application Insights (APM)
 │   │   │   │   ├── dashboard/                     # Shared Dashboards
 │   │   │   │   └── resource-locks/                # Resource Locks (prevent deletion)
 │   │   │   └── hybrid/                          # 🔄 Híbrido ⚠️
 │   │   │       ├── arc/                           # Azure Arc ⚠️(servers, k8s, data)
 │   │   │       ├── arc-servers/                   # Arc-enabled servers ⚠️
 │   │   │       ├── arc-kubernetes/                # Arc-enabled Kubernetes ⚠️
 │   │   │       ├── arc-data/                      # Arc-enabled data services ⚠️
 │   │   │       ├── hybrid-connections/            # Hybrid Connections (Azure Relay) ⚠️
 │   │   │       ├── vpn-gateway/                   # VPN Gateway (Site-to-Site) ⚠️
 │   │   │       ├── express-route/                 # ExpressRoute
 │   │   │       ├── site-recovery/                 # Site Recovery (hybrid DR) ⚠️
 │   │   │       └── stack-hci/                     # Azure Stack HCI (on-premise hyperconverged) ⚠️

```
---
### Declaración

Los directorios de estos modulos se complementaran con el tiempo, si usted considera que puede ser un aportar en unos de estos modules, contacteme.

Los directorios que esten para su referencia, en este readme se indocaran con un ✅ y aquellos que se desconoce si se implementaran con ⚠️.

---

Mario Fribla

***DevOps***
