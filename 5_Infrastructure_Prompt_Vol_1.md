You are operating in Senior Engineering Team Mode.

Build the production-ready cloud infrastructure foundation for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

This is an INFRASTRUCTURE PHASE.

Implement the infrastructure required by the approved backend, web frontend, mobile applications, video-processing platform, CDN delivery architecture, feed and recommendation systems, search platform, messaging system, moderation platform, analytics platform, advertising platform, administration system, privacy architecture, and Project Index.

Do not redesign the application architecture.

Do not implement backend business logic.

Do not implement frontend business logic.

Do not implement mobile business logic.

Infrastructure implementation is allowed in this phase.

────────────────────────────────────────

MISSION

Build the foundational AWS, Terraform, Docker, Kubernetes, networking, storage, database, cache, event-streaming, search, media-processing, CDN, security, observability, and deployment infrastructure.

Support:

• Consumer web
• Creator web
• Admin web
• Consumer mobile
• Creator mobile
• API gateway
• Identity services
• Profile services
• Social graph
• Video APIs
• Upload services
• Video-processing workers
• Transcoding workers
• Thumbnail workers
• Caption workers
• Feed services
• Recommendation services
• Search services
• Messaging
• Notifications
• Moderation
• Rights
• Advertising
• Analytics
• Privacy workers
• Administration

Environments:

• Local
• Development
• Test
• Staging
• Production
• Disaster Recovery

────────────────────────────────────────

PRIMARY CLOUD STACK

Cloud:

• AWS

Infrastructure as Code:

• Terraform

Containers:

• Docker

Orchestration:

• Kubernetes
• Amazon EKS

Packaging:

• Helm

Container Registry:

• Amazon ECR

Database:

• Amazon Aurora/RDS PostgreSQL

Cache:

• Amazon ElastiCache for Redis

Event streaming:

• Managed Kafka/Redpanda or approved AWS-compatible implementation

Search:

• Amazon OpenSearch

Object storage:

• Amazon S3

CDN:

• Amazon CloudFront

DNS:

• Amazon Route 53

TLS:

• AWS Certificate Manager

Secrets:

• AWS Secrets Manager

Encryption:

• AWS KMS

Security:

• IAM
• WAF
• Security Groups
• Network ACLs
• Kubernetes RBAC
• NetworkPolicies
• Pod Security Standards

Observability:

• OpenTelemetry
• Prometheus
• Grafana
• Loki
• Tempo

CI/CD foundation:

• GitHub Actions

────────────────────────────────────────

IMPLEMENTATION RULES

Never generate pseudo-configuration.

Never generate placeholders.

Never generate TODO infrastructure.

Never omit required resources.

Every Terraform file must be syntactically valid.

Every Helm template must be complete.

Every Dockerfile must build.

Never hard-code:

• AWS credentials
• Database passwords
• API keys
• Private keys
• Certificates
• Payment secrets
• Provider secrets

Never commit secrets.

Prefer:

• OIDC
• Short-lived credentials
• Workload identity
• Managed services
• Immutable artifacts

Never regenerate unchanged files.

Only modify existing files when required.

────────────────────────────────────────

INFRASTRUCTURE ARCHITECTURE

Create a modular infrastructure architecture using:

• Reusable Terraform modules
• Environment-specific Terraform roots
• Region-specific configuration
• Global resources
• Shared resources
• Application infrastructure
• Media infrastructure
• Data infrastructure
• Observability infrastructure
• Security infrastructure
• Disaster-recovery infrastructure

Separate:

• Global
• Regional
• Environment
• Workload

Avoid unnecessary duplication.

────────────────────────────────────────

AWS ACCOUNT STRATEGY

Prepare for:

• Management
• Security
• Log/archive
• Shared services
• Development
• Test
• Staging
• Production
• Disaster recovery

Define:

• Account ownership
• Cross-account roles
• IAM boundaries
• Centralized logging
• Security ownership
• Billing ownership

Do not require all accounts for local development.

────────────────────────────────────────

REGION STRATEGY

Define:

• Primary production region
• Secondary DR region

Prepare regional infrastructure for:

• API workloads
• Web workloads
• WebSockets
• Feed
• Recommendation
• Search
• Media processing
• Moderation
• Analytics
• Workers

Keep latency-sensitive workloads near their users where practical.

────────────────────────────────────────

ENVIRONMENT STRATEGY

LOCAL

Provide Docker Compose for:

• PostgreSQL
• Redis
• Kafka/Redpanda
• OpenSearch
• S3-compatible storage

DEVELOPMENT

Use lower-scale cloud resources.

TEST

Use isolated integration resources.

STAGING

Closely represent production architecture.

PRODUCTION

Use:

• Multi-AZ
• Encryption
• High availability
• Backups
• Monitoring
• Security controls

DISASTER RECOVERY

Provide:

• Recovery infrastructure
• Backup dependencies
• Infrastructure reconstruction path

────────────────────────────────────────

TERRAFORM STRUCTURE

Create:

terraform/

modules/

environments/

global/

regional/

shared/

application/

media/

data/

security/

observability/

backup/

disaster-recovery/

Terraform must separate reusable modules from environment compositions.

────────────────────────────────────────

TERRAFORM MODULES

Create modules for:

• Provider
• Naming
• Tags
• VPC
• Subnets
• Routing
• NAT
• Internet Gateway
• VPC endpoints
• Security groups
• IAM
• OIDC
• EKS
• Node groups
• Autoscaling
• Aurora/PostgreSQL
• ElastiCache
• Kafka
• OpenSearch
• S3
• CloudFront
• Route 53
• ACM
• WAF
• ECR
• Secrets Manager
• KMS
• Backup
• Logging
• Monitoring

────────────────────────────────────────

TERRAFORM STATE

Implement secure remote state using:

• S3
• Versioning
• Encryption
• Restricted IAM
• State isolation
• Approved locking mechanism

Do not put plaintext secrets into Terraform state unnecessarily.

────────────────────────────────────────

RESOURCE TAGGING

Standardize:

• Project
• Environment
• Region
• Service
• Team
• Owner
• CostCenter
• ManagedBy
• DataClassification

Use consistent naming conventions.

────────────────────────────────────────

NETWORK FOUNDATION

Create a VPC with:

• Public subnets
• Private application subnets
• Private data subnets
• Multi-AZ design
• Internet Gateway
• NAT
• Route tables
• VPC endpoints

Separate:

• Edge
• Application
• Data
• Management

────────────────────────────────────────

NETWORK SEGMENTATION

Create network boundaries for:

• Load balancers
• EKS
• APIs
• Workers
• Media workers
• PostgreSQL
• Redis
• Kafka
• OpenSearch

Do not permit unrestricted east-west traffic.

────────────────────────────────────────

SECURITY GROUPS

Create dedicated security groups for:

• ALB
• NLB
• EKS
• PostgreSQL
• Redis
• Kafka
• OpenSearch
• Management

Allow only required communication paths.

Internal data services must remain private.

────────────────────────────────────────

VPC ENDPOINTS

Use private AWS connectivity where practical for:

• S3
• ECR
• Secrets Manager
• KMS
• CloudWatch-related services
• STS
• Other required AWS services

Reduce unnecessary public internet dependency.

────────────────────────────────────────

EKS FOUNDATION

Create Amazon EKS infrastructure.

Support:

• Multi-AZ
• Private networking
• Cluster logging
• Kubernetes RBAC
• Workload identity
• NetworkPolicies
• Pod Security Standards
• Managed node groups

Namespaces should include:

• gateway
• application
• workers
• media
• feed
• recommendation
• search
• messaging
• moderation
• analytics
• observability
• ingress
• security
• operations

────────────────────────────────────────

NODE GROUP ARCHITECTURE

Define workload pools:

GENERAL

• API
• Web

COMPUTE

• Feed
• Recommendation
• CPU-heavy processing

MEDIA

• Transcoding
• FFmpeg
• Thumbnail processing

MEMORY

• Recommendation features
• Search-related services

ANALYTICS

• Stream/batch workloads

OBSERVABILITY

• Monitoring stack where justified

Define:

• Labels
• Taints
• Tolerations
• Affinity
• Anti-affinity
• Topology spread
• Scaling limits

────────────────────────────────────────

KUBERNETES GOVERNANCE

Configure:

• ResourceQuota
• LimitRange
• Resource requests
• Resource limits
• PodDisruptionBudget
• ServiceAccounts
• RBAC
• NetworkPolicies
• Pod Security Standards

Prevent:

• Privileged containers
• Unbounded resource use
• Cross-namespace access
• Service-account overpermission

────────────────────────────────────────

EDGE / INGRESS

Provide ingress for:

• Public APIs
• Web application
• Creator web
• Admin web
• WebSocket services
• Upload initialization
• Playback authorization

Support:

• TLS
• Health checks
• WebSocket upgrades
• Timeouts
• Rate limiting integration
• Connection draining

────────────────────────────────────────

LOAD BALANCING

Use:

• ALB for HTTP/HTTPS workloads
• NLB where high-throughput or connection-oriented traffic requires it

Configure:

• TLS
• Health checks
• Idle timeouts
• Access logs
• Security controls

────────────────────────────────────────

POSTGRESQL

Deploy managed PostgreSQL infrastructure.

Support:

• Multi-AZ
• Encryption
• TLS
• Automated backups
• PITR
• Parameter groups
• Monitoring
• Read replicas where required
• Performance monitoring
• Maintenance windows

Database remains private.

────────────────────────────────────────

DATABASE OPERATIONS FOUNDATION

Prepare:

• Connection pooling
• Connection limits
• Query monitoring
• Slow-query visibility
• Performance Insights
• Backup retention
• Replica lag monitoring

Support future:

• Partitioning
• Read replicas
• Archival
• Large-table management

────────────────────────────────────────

ELASTICACHE REDIS

Create Redis infrastructure supporting:

• Replication
• Multi-AZ
• Automatic failover
• Encryption at rest
• TLS
• Authentication
• Monitoring

Prepare for:

• Feed cache
• Recommendation cache
• Upload sessions
• Rate limits
• Messaging coordination
• Notification deduplication
• WebSocket coordination

────────────────────────────────────────

KAFKA / REDPANDA

Create infrastructure supporting:

• Multiple brokers
• Multi-AZ
• Replication
• Persistent storage
• TLS
• Authentication
• Monitoring

Prepare topics for:

• Video
• Engagement
• Feed
• Recommendation
• Search
• Messaging
• Notifications
• Moderation
• Rights
• Advertising
• Analytics
• Privacy

────────────────────────────────────────

OPENSEARCH

Create search infrastructure supporting:

• Multi-node
• Multi-AZ
• Encryption
• Access policies
• Shards
• Replicas
• Snapshots
• Monitoring

Indexes should be rebuildable from authoritative data.

────────────────────────────────────────

S3 MEDIA ARCHITECTURE

Create secure storage for:

• Original uploads
• Processing artifacts
• Master videos
• Renditions
• Manifests
• Segments
• Thumbnails
• Posters
• Previews
• Captions
• Creator assets
• Reports
• Privacy exports

Use:

• Encryption
• Versioning where justified
• Lifecycle rules
• Block public access
• Access policies
• Replication where required

────────────────────────────────────────

S3 BUCKET SEPARATION

Separate high-risk object classes where appropriate:

• Media
• Private creator documents
• Reports
• Privacy exports
• System artifacts
• Backups

Do not create one unrestricted bucket for every workload.

────────────────────────────────────────

CLOUDFRONT

Create CDN architecture for:

• Video manifests
• Video segments
• Thumbnails
• Posters
• Preview assets
• Static web assets

Configure:

• Origin Access Control
• Cache policies
• Response headers
• TLS
• WAF
• Logging

Private/restricted media requires secure authorization.

────────────────────────────────────────

ROUTE 53

Support:

• Consumer domain
• Creator domain if separate
• API domain
• Admin domain
• CDN domain
• Regional endpoints

Configure:

• Health checks
• Latency routing
• Failover
• Weighted traffic

────────────────────────────────────────

ACM

Create managed TLS certificates for:

• Web
• API
• Admin
• CDN
• WebSocket endpoints where applicable

Automate renewal.

────────────────────────────────────────

WAF

Protect:

• Public web
• Public API
• Admin
• Upload endpoints
• Webhook endpoints

Use:

• Managed rules
• Rate-based rules
• IP restrictions
• Request-size restrictions
• Bot controls where appropriate

Admin traffic requires stronger controls.

────────────────────────────────────────

IAM

Create least-privilege identities for:

• Terraform
• GitHub Actions
• EKS
• APIs
• Feed
• Recommendation
• Media workers
• Search workers
• Analytics workers
• Moderation workers
• Notification workers
• Privacy workers
• Backup jobs
• Observability

Prefer:

• OIDC
• EKS workload identity
• Short-lived credentials

────────────────────────────────────────

KMS

Create encryption keys for:

• S3
• PostgreSQL
• Redis where supported
• EBS
• Secrets
• Logs
• Backups
• Terraform state where applicable

Define:

• Key policy
• Rotation
• Access boundaries
• Environment isolation

────────────────────────────────────────

SECRETS MANAGER

Store:

• Database credentials
• Redis credentials
• Kafka credentials
• Search credentials
• Provider credentials
• Notification secrets
• OAuth secrets
• Webhook signing secrets
• Other application secrets

Integrate securely into Kubernetes.

Never put production secrets into:

• Git
• Docker images
• Helm values
• Public Terraform variables

────────────────────────────────────────

DOCKER FOUNDATION

Create production image standards for:

• API services
• Web application
• Feed services
• Recommendation services
• Search services
• Messaging
• Moderation
• Analytics
• Media workers

Use:

• Multi-stage builds
• Minimal runtime
• Non-root
• Reproducible builds
• Signal handling
• Health checks
• Dependency pinning

────────────────────────────────────────

MEDIA WORKER CONTAINERS

Create dedicated standards for FFmpeg workers.

Support:

• CPU optimization
• Temporary storage
• Resource limits
• Process isolation
• Graceful cancellation
• Input/output cleanup

Do not run heavy media processing in API containers.

────────────────────────────────────────

ECR

Create repositories for:

• API
• Web
• Feed
• Recommendation
• Search
• Messaging
• Moderation
• Analytics
• Media processing
• Transcoding
• Thumbnail
• Caption
• Privacy workers

Configure:

• Scan on push
• Lifecycle rules
• Access policies
• Immutable tags where appropriate

────────────────────────────────────────

LOCAL DEVELOPMENT

Create Docker Compose supporting:

• PostgreSQL
• Redis
• Kafka/Redpanda
• OpenSearch
• MinIO or approved S3-compatible storage

Provide:

• Persistent volumes
• Health checks
• Local credentials
• Network configuration
• Service dependencies

Never use production credentials.

────────────────────────────────────────

OBSERVABILITY FOUNDATION

Deploy and configure:

• OpenTelemetry Collector
• Prometheus
• Grafana
• Loki
• Tempo

Collect:

• Application metrics
• Node metrics
• Pod metrics
• PostgreSQL metrics
• Redis metrics
• Kafka metrics
• OpenSearch metrics
• EKS metrics
• Load-balancer metrics
• CDN metrics where available

────────────────────────────────────────

MEDIA OBSERVABILITY

Track:

• Upload rate
• Upload failure
• Processing backlog
• Transcoding duration
• Rendition generation
• Processing failure
• Worker saturation
• Storage growth

────────────────────────────────────────

FEED / RECOMMENDATION OBSERVABILITY

Track:

• Feed request rate
• Feed latency
• Candidate generation latency
• Ranking latency
• Recommendation latency
• Cache hit/miss
• Worker backlog
• Kafka lag

────────────────────────────────────────

SEARCH OBSERVABILITY

Track:

• Query rate
• Latency
• Indexing throughput
• Search freshness
• Cluster health
• Disk utilization
• JVM utilization

────────────────────────────────────────

HEALTH CHECKS

Configure:

• Startup
• Readiness
• Liveness

Readiness may include essential dependencies.

Liveness should not fail because a third-party provider temporarily fails.

────────────────────────────────────────

AUTOSCALING FOUNDATION

Prepare:

• HPA
• Karpenter or Cluster Autoscaler
• Queue-based scaling
• Kafka-lag scaling

Scale services based on:

• CPU
• Memory
• Request rate
• Queue depth
• Kafka lag
• WebSocket connections
• Media-processing load
• Recommendation load

────────────────────────────────────────

VIDEO PROCESSING AUTOSCALING

Scale media workers based on:

• Queue depth
• Processing latency
• CPU
• Memory
• GPU/hardware utilization where available

Use separate pools for:

• Standard
• High-throughput
• Priority

────────────────────────────────────────

RECOMMENDATION AUTOSCALING

Scale using:

• Request rate
• Candidate-generation latency
• Ranking latency
• CPU
• Memory
• Queue depth

Prevent recommendation workloads from consuming all general compute capacity.

────────────────────────────────────────

WEBSOCKET SCALING

Prepare:

• Horizontal replicas
• Connection draining
• Redis coordination
• Health-based routing
• Reconnect handling

Authoritative messaging/feed/trip state must not live only in process memory.

────────────────────────────────────────

BACKUP FOUNDATION

Configure:

• PostgreSQL automated backups
• PITR
• S3 versioning
• S3 replication where required
• OpenSearch snapshots
• Terraform state protection
• Critical configuration backup

Everything must be encrypted.

────────────────────────────────────────

DISASTER RECOVERY FOUNDATION

Prepare recovery for:

• AZ failure
• Kubernetes node failure
• EKS failure
• PostgreSQL failure
• Redis failure
• Kafka failure
• OpenSearch failure
• S3 disruption
• Region failure

Define:

• Dependency order
• Recovery source
• Validation
• Reconciliation

────────────────────────────────────────

SECURITY BASELINE

Implement:

• Least-privilege IAM
• Private networking
• Encryption at rest
• Encryption in transit
• WAF
• Security Groups
• NetworkPolicies
• Pod security
• Secrets management
• Audit logging
• Container security

────────────────────────────────────────

CLOUD AUDIT

Enable appropriate:

• CloudTrail
• EKS audit logs
• AWS Config
• Security findings integration
• Centralized log archive

Protect logs from unauthorized modification.

────────────────────────────────────────

INFRASTRUCTURE TESTING

Validate:

• Terraform fmt
• Terraform validate
• Terraform plan
• Terraform module tests
• Helm lint
• Kubernetes schema validation
• Docker builds
• Container scans
• IAM policy validation
• Security-group validation
• NetworkPolicy validation

────────────────────────────────────────

DOCUMENTATION

Generate:

• AWS architecture
• Account strategy
• Region strategy
• Environment strategy
• Terraform architecture
• VPC
• Networking
• EKS
• Kubernetes
• PostgreSQL
• Redis
• Kafka
• OpenSearch
• S3
• CloudFront
• Route 53
• ACM
• WAF
• IAM
• KMS
• Secrets Manager
• Docker
• ECR
• Media infrastructure
• Feed infrastructure
• Recommendation infrastructure
• Search infrastructure
• Observability
• Backup
• Disaster recovery
• Local development
• Infrastructure testing
• Security baseline

────────────────────────────────────────

PROJECT INDEX

Update the infrastructure Project Index with:

• AWS accounts
• Regions
• Environments
• VPCs
• Subnets
• Route tables
• NAT
• VPC endpoints
• Security groups
• IAM roles
• OIDC
• KMS
• Secrets
• EKS
• Node groups
• Namespaces
• Terraform modules
• Helm structure
• Dockerfiles
• ECR repositories
• PostgreSQL
• Redis
• Kafka/Redpanda
• OpenSearch
• S3 buckets
• CloudFront distributions
• Route 53
• ACM
• WAF
• Media-processing infrastructure
• Feed infrastructure
• Recommendation infrastructure
• Search infrastructure
• Observability
• Backups
• Disaster recovery
• Infrastructure tests
• Generated files
• Modified files
• Remaining work
• Current milestone
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

INFRASTRUCTURE MILESTONE 1

Terraform foundation, remote state, provider configuration, naming, tagging, global/regional/environment structure, reusable modules.

INFRASTRUCTURE MILESTONE 2

AWS networking: VPC, subnets, route tables, NAT, Internet Gateway, VPC endpoints, security groups, network segmentation.

INFRASTRUCTURE MILESTONE 3

IAM, OIDC, workload identity, KMS, Secrets Manager, ECR, CloudTrail, AWS Config, and security baseline.

INFRASTRUCTURE MILESTONE 4

EKS cluster, node groups, namespaces, RBAC, NetworkPolicies, Pod Security Standards, resource governance, ingress, and load balancing.

INFRASTRUCTURE MILESTONE 5

PostgreSQL/Aurora, Redis, Kafka/Redpanda, OpenSearch, encryption, monitoring, backup foundation, and database security.

INFRASTRUCTURE MILESTONE 6

S3 media storage, upload infrastructure, media-processing worker pools, transcoding infrastructure, thumbnail/caption workers, and CDN architecture.

INFRASTRUCTURE MILESTONE 7

CloudFront, Route 53, ACM, WAF, global routing, secure playback-origin architecture, static web delivery, and edge optimization.

INFRASTRUCTURE MILESTONE 8

Docker, ECR, local development, image hardening, container scanning, workload-specific containers, and resource policies.

INFRASTRUCTURE MILESTONE 9

Observability platform, OpenTelemetry Collector, Prometheus, Grafana, Loki, Tempo, dashboards, metrics, traces, logs, and health checks.

INFRASTRUCTURE MILESTONE 10

Autoscaling foundation, backup validation foundation, disaster-recovery preparation, infrastructure testing, security validation, documentation, and Project Index completion.

Each milestone should contain approximately 20–40 files where practical.

Every milestone must pass infrastructure validation before proceeding.

────────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never truncate files.

Never summarize configuration instead of generating it.

Never generate pseudo-configuration.

Never generate placeholders.

Never generate TODO implementations.

When modifying an existing file:

1. Provide the exact file path.
2. State why it must change.
3. Provide the complete updated file.

Never regenerate unchanged files.

────────────────────────────────────────

SCOPE RESTRICTION

This volume covers infrastructure foundations:

• AWS
• Terraform
• Networking
• IAM
• OIDC
• KMS
• Secrets Manager
• EKS
• Kubernetes foundations
• PostgreSQL
• Redis
• Kafka/Redpanda
• OpenSearch
• S3
• CloudFront
• Route 53
• ACM
• WAF
• Docker
• ECR
• Media-processing infrastructure
• Feed/recommendation workload infrastructure
• Search infrastructure
• Observability foundation
• Backup foundation
• Disaster-recovery foundation
• Infrastructure security
• Infrastructure testing
• Local development

Do not implement:

• Backend business logic
• Frontend business logic
• Mobile business logic
• Feed-ranking logic
• Recommendation algorithms
• Video-processing application logic
• Search business logic
• Moderation business logic
• Advertising business logic

Those belong to application layers.

────────────────────────────────────────

QUALITY BAR

Treat this infrastructure as the foundation for a globally distributed social-video platform supporting:

• Hundreds of millions of users
• Millions of creators
• Millions of videos per day
• Billions of video impressions
• Massive video-processing workloads
• Massive CDN traffic
• Massive feed traffic
• Large recommendation workloads
• Large search traffic
• Massive messaging traffic
• Multiple regions
• High availability
• Disaster recovery
• Strict privacy
• Strict security

Prioritize:

• Availability
• Security
• Scalability
• Media-processing isolation
• CDN efficiency
• Private networking
• Least privilege
• Observability
• Disaster recovery
• Cost awareness
• Automation
• Maintainability
• Production readiness
