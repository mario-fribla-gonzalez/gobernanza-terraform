# Repostorio de Gobernanza Terraform.

## Google Cloud Platform (GCP), estructura del directorio de modulos de Terraform.

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
 │   ├── gcp/
 │   │   ├── modules/
 │   │   │   │
 │   │   │   ├── networking/                      # 🌐 Redes y conectividad
 │   │   │   │    ├── vpc/                          # Red Virtual Privada
 │   │   │   │    ├── subnet/                       # Subredes
 │   │   │   │    ├── firewall/                     # Reglas de firewall
 │   │   │   │    ├── nat/                          # Cloud NAT
 │   │   │   │    ├── vpn/                          # Cloud VPN (HA, Classic)
 │   │   │   │    ├── interconnect/                 # Cloud Interconnect ⚠️
 │   │   │   │    ├── dns/                          # Cloud DNS (zonas, registros)
 │   │   │   │    └── load-balancing/               # Balanceadores (ver load-balancing/)
 │   │   │   ├── compute/                         # 💻 Cómputo
 │   │   │   │   ├── gce-instance/                  # VM individual
 │   │   │   │   ├── gce-template/                  # Plantilla de instancias
 │   │   │   │   ├── mig/                           # Grupo de instancias gestionado
 │   │   │   │   ├── sole-tenant/                   # Nodo dedicado
 │   │   │   │   ├── gke-cluster/                   # Cluster Kubernetes
 │   │   │   │   ├── gke-nodepool/                  # Node pool de GKE
 │   │   │   │   └── vmware-engine/                 # VMware Engine ⚠️
 │   │   │   ├── paas/                            # 🚀 Plataforma como Servicio
 │   │   │   │   ├── cloud-run/                     # Cloud Run (serverless containers)
 │   │   │   │   ├── cloud-functions/               # Cloud Functions (2da gen)
 │   │   │   │   ├── app-engine/                    # App Engine (flex/standard)
 │   │   │   │   ├── artifact-registry/             # Repositorio de artefactos
 │   │   │   │   ├── cloud-build/                   # CI/CD pipelines
 │   │   │   │   └── workflows/                     # Workflows (orquestación)
 │   │   │   ├── database/                        # 🗄️ Bases de Datos
 │   │   │   │   ├── cloud-sql/                     # Cloud SQL (MySQL, PG, SQL Server)
 │   │   │   │   ├── spanner/                       # Spanner (distribuido, global)
 │   │   │   │   ├── bigtable/                      # Bigtable (NoSQL, alta perf)
 │   │   │   │   ├── firestore/                     # Firestore (serverless NoSQL)
 │   │   │   │   ├── memorystore/                   # Memorystore (Redis, Memcached)
 │   │   │   │   ├── alloydb/                       # AlloyDB (PostgreSQL compatible)
 │   │   │   │   └── datastore/                     # Datastore (NoSQL legacy)
 │   │   │   ├── load-balancing/                  # ⚖️ Balanceo de Carga
 │   │   │   │   ├── lb-https/                      # HTTPS Load Balancer (global)
 │   │   │   │   ├── lb-tcp/                        # TCP Load Balancer (regional)
 │   │   │   │   ├── lb-internal/                   # Internal Load Balancer
 │   │   │   │   ├── lb-urlmask/                    # URL Mask (path/host routing)
 │   │   │   │   ├── backend-service/               # Backend service con NEGs
 │   │   │   │   ├── serverless-neg/                # Serverless NEG para Cloud Run
 │   │   │   │   └── traffic-director/              # Traffic Director (service mesh)
 │   │   │   ├── security/                        # 🔒 Seguridad
 │   │   │   │   ├── iam/                           # IAM (roles, bindings, policies)
 │   │   │   │   ├── service-account/               # Cuentas de servicio
 │   │   │   │   ├── cloud-armor/                   # Cloud Armor (WAF, DDoS)
 │   │   │   │   ├── certificate-manager/           # Certificados SSL/TLS
 │   │   │   │   └── access-context-manager/        # VPC Service Controls
 │   │   │   ├── storage/                           # 💾 Almacenamiento
 │   │   │   │   ├── gcs-bucket/                    # Cloud Storage (buckets, objects)
 │   │   │   │   ├── filestore/                     # Filestore (NFS managed)
 │   │   │   │   ├── persistent-disk/               # Persistent Disk (disco adicional)
 │   │   │   │   ├── backup/                        # Backup for GKE, Cloud SQL
 │   │   │   │   └── transfer/                      # Storage Transfer Service
 │   │   │   ├── data/                            # 📈 Data & Analytics
 │   │   │   │   ├── bigquery/                      # BigQuery (dataset, tables)
 │   │   │   │   ├── dataflow/                      # Dataflow (streaming/batch)
 │   │   │   │   ├── dataproc/                      # Dataproc (Spark, Hadoop)
 │   │   │   │   ├── pubsub/                        # Pub/Sub (topics, subscriptions)
 │   │   │   │   ├── datacatalog/                   # Data Catalog
 │   │   │   │   ├── dataplex/                      # Dataplex (data mesh)
 │   │   │   │   ├── datastream/                    # Datastream (CDC)
 │   │   │   │   └── looker/                        # Looker (BI, dashboards)
 │   │   │   ├── integration/                     # 🔌 Integración
 │   │   │   │   ├── apigee/                        # Apigee (API management)
 │   │   │   │   ├── endpoints/                     # Cloud Endpoints
 │   │   │   │   ├── cloud-build/                   # Cloud Build (CI/CD)
 │   │   │   │   ├── source-repos/                  # Cloud Source Repositories
 │   │   │   │   ├── artifact-registry/             # Artifact Registry
 │   │   │   │   └── container-registry/            # Container Registry (legacy)
 │   │   │   ├── migration/                       # 🚚 Migración
 │   │   │   │   ├── transfer/                      # Storage Transfer Service
 │   │   │   │   ├── dms/                           # Database Migration Service ⚠️
 │   │   │   │   ├── datastream/                    # Datastream (CDC) ⚠️
 │   │   │   │   ├── bigquery-migration/            # BigQuery Migration Service
 │   │   │   │   └── vm-migration/                  # Migrate for Compute Engine ⚠️
 │   │   │   ├── governance/                      # 📋 Gobernanza
 │   │   │   │   ├── policy/                        # Organization policies
 │   │   │   │   ├── folder/                        # Resource Manager folders
 │   │   │   │   ├── project/                       # Projects (creación, configuración)
 │   │   │   │   ├── budget/                        # Budgets and alerts ⚠️
 │   │   │   │   ├── billing/                       # Billing accounts ⚠️
 │   │   │   │   ├── quota/                         # Quota management ⚠️
 │   │   │   │   └── tags/                          # Resource tags
```
---
### Declaración

Los directorios de estos modulos se complementaran con el tiempo, si usted considera que puede ser un aportar en unos de estos modules, contacteme.

Los directorios que esten para su referencia, en este readme se indocaran con un ✅ y aquellos que se desconoce si se implementaran con ⚠️.

---

Mario Fribla

***DevOps***
