# Quick Revision Topics — 03 DevOps and Cloud

---
---

# DevOps

---

## 01 DevOps Fundamentals

- What is DevOps? Culture + Automation + Measurement
- DevOps vs Traditional (Waterfall, Agile alone)
- CI/CD — Continuous Integration vs Continuous Delivery vs Continuous Deployment
- DevOps lifecycle — Plan, Code, Build, Test, Release, Deploy, Operate, Monitor
- Infrastructure as Code (IaC) — why and what
- Configuration Management — Ansible, Chef, Puppet
- Version Control — Git basics for DevOps
- Shift Left — testing and security earlier
- DevSecOps — security in pipeline
- Monitoring vs Observability
- SLA vs SLO vs SLI
- MTTR vs MTBF — reliability metrics
- Blue-Green vs Canary vs Rolling deployment

---

## 02 Docker

- What is Docker? Containers vs VMs
- Docker Image vs Container
- `Dockerfile` — `FROM`, `COPY`, `RUN`, `CMD`, `ENTRYPOINT`, `EXPOSE`, `WORKDIR`
- `CMD` vs `ENTRYPOINT` — differences
- Docker layers — caching, layer order optimization
- Multi-stage builds — smaller images
- `docker build`, `docker run`, `docker ps`, `docker exec`
- `docker-compose` — multi-container orchestration
- `docker-compose.yml` — services, networks, volumes
- Volumes — persistent data, bind mounts vs named volumes
- Networking — bridge, host, overlay
- Port mapping — `-p 8080:80`
- Environment variables — `-e`, `.env` file
- Docker Hub — push, pull, tagging
- `.dockerignore` — excluding files
- Container health checks
- Docker best practices — non-root user, minimal base image, no secrets in image

---

## 03 Kubernetes (Basic)

- What is Kubernetes (K8s)? Container orchestration
- K8s Architecture — Control Plane + Worker Nodes
- Control Plane — API Server, etcd, Scheduler, Controller Manager
- Worker Node — kubelet, kube-proxy, Container Runtime
- Pod — smallest deployable unit
- ReplicaSet — desired state, scaling
- Deployment — rolling updates, rollback
- Service — ClusterIP, NodePort, LoadBalancer
- Ingress — routing external traffic
- ConfigMap vs Secret
- Namespace — resource isolation
- `kubectl` commands — `get`, `describe`, `apply`, `delete`, `logs`, `exec`
- YAML manifests — `kind`, `metadata`, `spec`
- Liveness Probe vs Readiness Probe vs Startup Probe
- Horizontal Pod Autoscaler (HPA)
- Persistent Volume (PV) vs Persistent Volume Claim (PVC)
- StatefulSet vs Deployment — when to use
- DaemonSet — one pod per node
- Job vs CronJob — batch workloads
- Helm — package manager for K8s

---

## 04 CI/CD Pipelines

- Pipeline stages — Build → Test → Package → Deploy
- Build triggers — push, PR, schedule, manual
- Artifact — build output, versioned packages
- Pipeline as Code — YAML-based pipelines
- Environment variables & secrets in pipeline
- Build agents — self-hosted vs cloud-hosted
- Parallel jobs — faster pipelines
- Gate/Approval — manual approval before production
- Pipeline caching — dependencies, Docker layers
- Rollback strategy — automated vs manual
- Feature flags — deploy without releasing
- Smoke tests vs Integration tests in pipeline

---

## 05 Azure DevOps

- Azure DevOps services — Boards, Repos, Pipelines, Artifacts, Test Plans
- Azure Repos — Git repos, branch policies
- Azure Pipelines — YAML vs Classic (UI)
- Pipeline stages, jobs, steps
- `trigger`, `pool`, `variables`, `stages`
- Service Connections — connecting to Azure, Docker Hub
- Release Pipelines — multi-stage deployment
- Environments — approvals and checks
- Variable Groups — shared variables across pipelines
- Azure Artifacts — NuGet, npm feeds
- Branch policies — PR reviews, build validation
- Pipeline templates — reusable YAML
- Self-hosted agents vs Microsoft-hosted agents

---

## 06 Git (DevOps Perspective)

- Branching strategies — GitFlow, GitHub Flow, Trunk-Based Development
- Feature branch → PR → merge
- `git rebase` vs `git merge`
- Squash commits — clean history
- Cherry-pick — selective commit
- Tags — version releases
- `.gitignore` — patterns
- Monorepo vs Multi-repo
- Conventional Commits — `feat:`, `fix:`, `chore:`
- Pre-commit hooks — linting, formatting
- Protected branches — enforce reviews

---

## 07 Infrastructure as Code (IaC)

- What is IaC? Declarative vs Imperative
- Terraform — `plan`, `apply`, `destroy`
- Terraform state — `.tfstate`, remote backend
- Terraform modules — reusability
- ARM Templates (Azure) — JSON-based
- Bicep (Azure) — simplified ARM
- Ansible — agentless, playbooks, inventory
- IaC best practices — version control, modular, idempotent
- Drift detection — actual vs desired state
- Terraform vs ARM vs Bicep vs Pulumi

---

## 08 Monitoring & Observability

- Three Pillars — Logs, Metrics, Traces
- Logging — structured vs unstructured
- Centralized logging — ELK Stack, Azure Monitor, CloudWatch
- Metrics — counters, gauges, histograms
- Application Performance Monitoring (APM)
- Distributed tracing — correlation IDs, OpenTelemetry
- Alerting — thresholds, anomaly detection
- Dashboards — Grafana, Azure Dashboard
- Health checks — liveness, readiness
- Log levels — Debug, Info, Warning, Error, Critical
- Prometheus + Grafana — metrics stack
- Jaeger / Zipkin — tracing tools

---

## 09 Security in DevOps (DevSecOps)

- Shift Left security — scan early
- SAST — Static Application Security Testing
- DAST — Dynamic Application Security Testing
- SCA — Software Composition Analysis (dependency scanning)
- Secret management — Azure Key Vault, AWS Secrets Manager, HashiCorp Vault
- Container security — image scanning, non-root, minimal images
- RBAC — Role-Based Access Control in pipelines
- Least privilege principle
- Network policies — zero trust
- Vulnerability scanning — Trivy, Snyk
- Compliance as Code

---
---

# Cloud — AWS

---

## 01 AWS Fundamentals

- AWS Global Infrastructure — Regions, Availability Zones, Edge Locations
- AWS Account structure — root, IAM users, organizations
- AWS Free Tier — what's included
- AWS Well-Architected Framework — 6 pillars
- Shared Responsibility Model — AWS vs Customer
- AWS Console vs CLI vs SDK
- AWS pricing — On-Demand, Reserved, Spot instances
- Tags — resource organization and cost tracking

---

## 02 Compute

- EC2 — instance types, AMI, key pairs, security groups
- EC2 Auto Scaling — scaling policies, launch templates
- Elastic Load Balancer — ALB vs NLB vs CLB
- Lambda — serverless compute, triggers, cold start
- Lambda layers, timeout, memory config
- Elastic Beanstalk — PaaS, managed deployment
- ECS — Elastic Container Service, tasks, services
- EKS — Elastic Kubernetes Service
- Fargate — serverless containers (no EC2 management)
- EC2 vs Lambda vs ECS vs Fargate — when to use

---

## 03 Storage

- S3 — Simple Storage Service, buckets, objects
- S3 storage classes — Standard, IA, Glacier, Deep Archive
- S3 lifecycle policies — transition and expiration
- S3 versioning, encryption, access policies
- S3 pre-signed URLs — temporary access
- EBS — Elastic Block Store, volume types (gp3, io2, st1)
- EFS — Elastic File System, shared NFS
- S3 vs EBS vs EFS — comparison

---

## 04 Database

- RDS — Relational Database Service, multi-AZ, read replicas
- RDS engines — MySQL, PostgreSQL, SQL Server, Aurora
- Aurora — MySQL/PostgreSQL compatible, serverless option
- DynamoDB — NoSQL, key-value, partition key, sort key
- DynamoDB — capacity modes (On-Demand vs Provisioned)
- ElastiCache — Redis, Memcached
- Redshift — data warehouse
- RDS vs DynamoDB — when to use which

---

## 05 Messaging & Integration

- SQS — Simple Queue Service, standard vs FIFO
- SNS — Simple Notification Service, topics, subscriptions
- SQS vs SNS — pull vs push
- EventBridge — event bus, rules, targets
- Step Functions — workflow orchestration
- API Gateway — REST/HTTP API, throttling, stages
- Kinesis — real-time streaming

---

## 06 Networking

- VPC — Virtual Private Cloud, subnets (public/private)
- Internet Gateway vs NAT Gateway
- Security Groups vs NACLs — stateful vs stateless
- Route Tables — routing traffic
- VPC Peering — cross-VPC communication
- Elastic IP — static public IP
- Route 53 — DNS, routing policies (simple, weighted, failover, latency)
- CloudFront — CDN, edge locations, caching
- VPN vs Direct Connect — hybrid connectivity

---

## 07 Security & Identity

- IAM — Users, Groups, Roles, Policies
- IAM Policy — JSON structure, `Effect`, `Action`, `Resource`
- Least privilege principle
- IAM Roles — cross-account, for services
- MFA — multi-factor authentication
- AWS Organizations — SCPs (Service Control Policies)
- KMS — Key Management Service, encryption
- Secrets Manager vs Parameter Store
- Cognito — user pools, identity pools
- WAF — Web Application Firewall
- Shield — DDoS protection
- GuardDuty — threat detection

---

## 08 Monitoring & DevOps (AWS)

- CloudWatch — metrics, logs, alarms, dashboards
- CloudWatch Logs — log groups, log streams, insights
- CloudTrail — API call auditing
- X-Ray — distributed tracing
- CodePipeline — CI/CD orchestration
- CodeBuild — build service
- CodeDeploy — deployment automation
- CodeCommit — Git repository (deprecated, use others)
- CloudFormation — IaC, stacks, templates
- SAM — Serverless Application Model
- Systems Manager — patch, run command, parameter store

---
---

# Cloud — Azure

---

## 01 Azure Fundamentals

- Azure Global Infrastructure — Regions, Availability Zones, Region Pairs
- Azure Resource Manager (ARM) — resource groups, subscriptions, management groups
- Azure pricing — Pay-as-you-go, Reserved, Spot
- Azure Free Tier — 12 months free, always free
- Azure Portal vs CLI (`az`) vs PowerShell vs SDK
- Azure Well-Architected Framework — 5 pillars
- Shared Responsibility Model
- Tags — cost management, organization

---

## 02 Compute (Azure)

- Virtual Machines — sizes, availability sets, scale sets
- VM Scale Sets — auto-scaling
- App Service — PaaS, deployment slots, scaling
- App Service Plan — pricing tiers, shared vs dedicated
- Azure Functions — serverless, triggers, bindings, Durable Functions
- Azure Functions — Consumption vs Premium vs Dedicated plan
- Azure Container Instances (ACI) — simple container hosting
- Azure Kubernetes Service (AKS) — managed K8s
- Azure Container Apps — serverless containers
- App Service vs Functions vs ACI vs AKS vs Container Apps — when to use

---

## 03 Storage (Azure)

- Azure Storage Account — Blob, Table, Queue, File
- Blob Storage — Block, Append, Page blobs
- Blob access tiers — Hot, Cool, Cold, Archive
- Lifecycle management policies
- Storage redundancy — LRS, ZRS, GRS, RA-GRS
- Azure Files — SMB/NFS file shares
- Azure Disk — Managed Disks, Ultra, Premium SSD, Standard
- Storage security — SAS tokens, access keys, Azure AD
- CDN — content delivery, caching at edge

---

## 04 Database (Azure)

- Azure SQL Database — single, elastic pool, managed instance
- Azure SQL vs SQL Server on VM
- DTU vs vCore pricing model
- Cosmos DB — globally distributed, multi-model NoSQL
- Cosmos DB APIs — SQL, MongoDB, Cassandra, Gremlin, Table
- Cosmos DB — partition key, RU/s, consistency levels (5 levels)
- Azure Cache for Redis — managed Redis
- Azure Database for MySQL/PostgreSQL — managed open-source
- Azure SQL vs Cosmos DB — when to use which

---

## 05 Networking (Azure)

- Virtual Network (VNet) — subnets, address space
- NSG — Network Security Groups, inbound/outbound rules
- Azure Load Balancer — Layer 4, public vs internal
- Application Gateway — Layer 7, WAF, URL routing
- Azure Front Door — global load balancing, CDN, WAF
- VNet Peering — cross-VNet connectivity
- VPN Gateway — site-to-site, point-to-site
- ExpressRoute — private dedicated connection
- Azure DNS — custom domain hosting
- Private Endpoints — private access to PaaS services
- Service Endpoints vs Private Endpoints

---

## 06 Integration (Azure)

- Azure Service Bus — queues, topics, sessions, dead-letter
- Azure Queue Storage vs Service Bus — comparison
- Azure Event Grid — event-based, reactive programming
- Azure Event Hubs — big data streaming, Kafka protocol
- Logic Apps — workflow automation, connectors
- API Management (APIM) — gateway, policies, rate limiting
- Azure SignalR Service — managed real-time
- Event Grid vs Event Hubs vs Service Bus — when to use

---

## 07 Identity & Security (Azure)

- Azure Active Directory (Entra ID) — identity platform
- Azure AD vs on-premises AD
- Authentication — OAuth 2.0, OpenID Connect, SAML
- App Registrations — client ID, tenant ID, secrets
- Managed Identity — system-assigned vs user-assigned
- Azure RBAC — roles, scope (management group, subscription, resource group, resource)
- Built-in roles — Owner, Contributor, Reader
- Azure Key Vault — secrets, keys, certificates
- Azure Policy — compliance, enforce standards
- Azure Defender / Microsoft Defender for Cloud
- Conditional Access — policies, MFA enforcement
- Service Principal vs Managed Identity

---

## 08 Monitoring (Azure)

- Azure Monitor — metrics, logs, alerts
- Log Analytics workspace — KQL queries
- Application Insights — APM, telemetry, live metrics
- Application Insights — request tracking, dependency tracking, exceptions
- Azure Alerts — metric, log, activity log alerts
- Action Groups — email, SMS, webhook, Logic App
- Diagnostic Settings — route logs to Log Analytics, Storage, Event Hub
- Azure Dashboard — custom visualizations
- Azure Advisor — cost, security, reliability recommendations

---

## 09 DevOps & Containers (Azure)

- Azure DevOps — Boards, Repos, Pipelines, Artifacts, Test Plans
- Azure Container Registry (ACR) — private Docker registry
- AKS — managed Kubernetes, node pools, RBAC
- Azure Container Apps — microservices, Dapr sidecar
- Deployment Center — GitHub Actions integration
- Azure Bicep — IaC for Azure (simplified ARM)
- ARM Templates — JSON-based IaC
- GitHub Actions vs Azure Pipelines
- Terraform with Azure — `azurerm` provider

---
---

# Quick Comparisons — DevOps & Cloud

---

## Rapid Fire

- Docker vs VM
- Docker Compose vs Kubernetes
- Pod vs Container
- Deployment vs StatefulSet
- ConfigMap vs Secret
- ClusterIP vs NodePort vs LoadBalancer
- CI vs CD
- Blue-Green vs Canary deployment
- Terraform vs ARM/Bicep
- AWS vs Azure — service mapping
- EC2 vs Azure VM
- S3 vs Azure Blob Storage
- Lambda vs Azure Functions
- RDS vs Azure SQL
- DynamoDB vs Cosmos DB
- SQS vs Azure Service Bus
- CloudWatch vs Azure Monitor
- IAM (AWS) vs Azure RBAC
- ECS/EKS vs AKS
- API Gateway (AWS) vs Azure APIM
- CodePipeline vs Azure Pipelines
- CloudFormation vs ARM/Bicep vs Terraform
- Monolith deployment vs Containerized deployment
- Self-hosted runner vs Cloud-hosted agent
