You are operating in Senior Engineering Team Mode.

Complete the production-grade infrastructure, DevOps, CI/CD, multi-region deployment, autoscaling, media-processing infrastructure, observability, security operations, disaster recovery, backup validation, cost optimization, incident response, and production-release system for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

Use the previously approved infrastructure architecture as the source of truth.

Do not redesign the application architecture.

Do not implement backend business logic.

Do not implement frontend code.

Do not implement mobile code.

Infrastructure implementation is allowed in this phase.

────────────────────────────────────────

MISSION

Complete the infrastructure required for:

• Production deployment
• Consumer web
• Creator web
• Administration web
• API services
• Video upload services
• Video-processing workers
• FFmpeg/transcoding workers
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
• Background workers
• WebSockets
• CDN
• Global traffic management
• Multi-region deployment
• Continuous delivery
• Automated rollback
• Observability
• Security operations
• Disaster recovery
• Capacity management
• Cost management
• Incident response
• Production certification

────────────────────────────────────────

PRIMARY TECHNOLOGY STACK

Cloud:

• AWS

Infrastructure as Code:

• Terraform

Containers:

• Docker
• Amazon ECR

Orchestration:

• Kubernetes
• Amazon EKS

Packaging:

• Helm

CI/CD:

• GitHub Actions

Database:

• Amazon Aurora/RDS PostgreSQL

Cache:

• Amazon ElastiCache for Redis

Event streaming:

• Managed Kafka/Redpanda or approved equivalent

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

────────────────────────────────────────

IMPLEMENTATION RULES

Never generate pseudo-configuration.

Never generate placeholders.

Never generate TODO infrastructure.

Never omit required configuration.

Every Terraform file must be syntactically valid.

Every Helm template must be complete.

Every Dockerfile must build.

Every CI/CD workflow must be complete.

Never hard-code secrets.

Never commit:

• AWS credentials
• Database credentials
• API keys
• Private keys
• Certificates
• Provider credentials

Prefer:

• OIDC
• Short-lived credentials
• Workload identity
• Immutable artifacts
• Managed services

Never regenerate unchanged files.

Only modify existing files when required.

────────────────────────────────────────

PRODUCTION KUBERNETES

Complete Helm/Kubernetes deployment architecture for:

• API gateway
• Identity services
• Profile services
• Social graph
• Video services
• Upload services
• Media-processing services
• Transcoding
• Thumbnails
• Captions
• Feed
• Recommendation
• Ranking
• Trending
• Search
• Messaging
• Notifications
• Moderation
• Rights
• Advertising
• Analytics
• Privacy workers
• Administration
• Web application
• Scheduled jobs
• Reconciliation workers

For every workload define:

• Deployment
• Service
• ServiceAccount
• ConfigMap where appropriate
• Secret references
• Startup probe
• Readiness probe
• Liveness probe
• Resource requests
• Resource limits
• HPA where applicable
• PDB
• NetworkPolicy
• Topology spread
• Affinity
• Anti-affinity
• Graceful termination

────────────────────────────────────────

KUBERNETES NAMESPACES

Use separate namespaces or carefully defined boundaries for:

• gateway
• web
• application
• media
• feed
• recommendation
• search
• messaging
• moderation
• analytics
• workers
• observability
• ingress
• security
• operations

Do not create namespaces solely for cosmetic separation.

Use namespace boundaries where they provide real security or operational value.

────────────────────────────────────────

RESOURCE GOVERNANCE

Configure:

• ResourceQuota
• LimitRange
• CPU limits
• Memory limits
• Ephemeral-storage limits
• PodDisruptionBudget

Prevent:

• Noisy neighbors
• Resource exhaustion
• Runaway workers
• Unbounded media-processing jobs

────────────────────────────────────────

MEDIA WORKER POOLS

Create dedicated worker node pools for:

• Standard media processing
• High-CPU transcoding
• Hardware-accelerated/GPU processing where justified
• Thumbnail generation
• Caption processing
• Moderation processing

Define:

• Instance classes
• Scaling bounds
• Labels
• Taints
• Tolerations
• Priority classes
• Topology spread

Do not allow FFmpeg jobs to consume API capacity.

────────────────────────────────────────

MEDIA TEMPORARY STORAGE

Provide isolated temporary storage for processing workloads.

Support:

• Adequate ephemeral storage
• Cleanup
• Size limits
• Failure recovery
• Encryption where required

Avoid writing large media-processing intermediates into PostgreSQL.

────────────────────────────────────────

FFMPEG SECURITY

Infrastructure must assume media files are untrusted.

Use:

• Non-root containers
• Restricted capabilities
• Seccomp
• Read-only filesystem where possible
• Resource limits
• Process limits
• Network restrictions
• Temporary storage limits

Do not allow arbitrary outbound network access from transcoding workers unless required.

────────────────────────────────────────

GPU / HARDWARE ACCELERATION

Prepare infrastructure for hardware acceleration where economically justified.

Support:

• Dedicated GPU node pools
• GPU resource requests
• Taints/tolerations
• Autoscaling
• Separate workload scheduling
• Capacity limits

Do not force GPU infrastructure onto all environments.

────────────────────────────────────────

DEPLOYMENT STRATEGIES

Support:

• Rolling
• Canary
• Blue-green where justified

Use controlled rollout for:

• Recommendation services
• Feed services
• Search
• Moderation
• Financially adjacent services
• Media processing changes

Real-time systems must support connection draining.

────────────────────────────────────────

ZERO-DOWNTIME DEPLOYMENTS

Ensure:

• Multiple replicas
• Readiness probes
• Startup probes
• PDB
• Graceful shutdown
• Connection draining
• Backward-compatible schema
• Safe migration sequence

Use expand-and-contract database migrations.

────────────────────────────────────────

CI/CD

Create complete GitHub Actions pipelines.

PULL REQUEST:

• Formatting
• Type checking
• Unit tests
• Integration tests
• Contract tests
• Security scans
• Secret scans
• Dependency scanning
• Docker builds
• Terraform validation
• Helm lint
• Kubernetes schema validation

BUILD:

• Build containers
• Generate SBOM
• Scan images
• Sign images
• Publish to ECR
• Generate provenance metadata

DEPLOYMENT:

• Development
• Test
• Staging
• Production

────────────────────────────────────────

CI/CD SECURITY

Use:

• GitHub OIDC
• Minimal GitHub permissions
• Protected environments
• Required approvals
• Environment-specific IAM roles
• Immutable artifacts

Do not use long-lived AWS credentials in GitHub secrets.

────────────────────────────────────────

ARTIFACT PROMOTION

Use:

Development
→ Test
→ Staging
→ Production

Promote the same immutable container artifact between environments whenever practical.

Validate:

• Image digest
• SBOM
• Security result
• Tests
• Approvals

────────────────────────────────────────

DEPLOYMENT VERIFICATION

After deployment automatically verify:

• Pods healthy
• Readiness healthy
• Error rate
• Latency
• Queue depth
• Kafka lag
• Database connectivity
• Redis connectivity
• WebSocket connectivity

Failed deployments must stop promotion.

────────────────────────────────────────

ROLLBACK

Support:

• Helm rollback
• Canary rollback
• Traffic rollback
• Version rollback

Do not automatically reverse non-reversible database migrations.

Use backward-compatible migrations.

────────────────────────────────────────

GLOBAL TRAFFIC MANAGEMENT

Configure:

• Route 53 latency routing
• Health checks
• Failover routing
• Weighted traffic
• Region draining
• Controlled failback

Support separate endpoints for:

• Consumer web
• Creator web
• Admin
• API
• WebSockets

────────────────────────────────────────

MULTI-REGION

Create regional infrastructure for:

• EKS
• APIs
• WebSockets
• Feed
• Recommendation
• Search
• Media processing
• Analytics
• Workers
• Moderation

Use global:

• Route 53
• CloudFront
• Artifact replication where required

────────────────────────────────────────

REGIONAL DATA STRATEGY

Define ownership for:

• User metadata
• Creator metadata
• Video metadata
• Feed state
• Recommendation state
• Search indexes
• Analytics
• Media processing

Avoid unnecessary cross-region synchronous requests.

────────────────────────────────────────

REGIONAL FAILOVER

Define:

• Detection
• Traffic drain
• Traffic redirection
• Service recovery
• State reconciliation
• Failback

Prevent:

• Split-brain feed ownership
• Duplicate processing
• Conflicting publication
• Duplicate analytics processing

────────────────────────────────────────

POSTGRESQL PRODUCTION

Complete production infrastructure for PostgreSQL.

Support:

• Multi-AZ
• Encryption
• TLS
• Automated backup
• PITR
• Read replicas
• Monitoring
• Parameter groups
• Connection management
• Performance monitoring
• Maintenance windows

Monitor:

• CPU
• Memory
• Storage
• IOPS
• Connections
• Query latency
• Locks
• Deadlocks
• Replica lag

────────────────────────────────────────

DATABASE MIGRATION PIPELINE

Integrate safe migration workflows:

1. Expand schema.
2. Deploy compatible application.
3. Backfill asynchronously.
4. Validate.
5. Switch usage.
6. Contract old schema later.

Do not run dangerous schema changes automatically without validation.

────────────────────────────────────────

REDIS PRODUCTION

Complete:

• Multi-AZ
• Replication
• Automatic failover
• Encryption
• TLS
• Authentication
• Monitoring

Monitor:

• Memory
• Evictions
• Connections
• Latency
• Replication
• Hot keys

Prepare capacity for:

• Feed
• Recommendation
• Trending
• Upload sessions
• Rate limiting
• Messaging
• WebSockets
• Notification deduplication

────────────────────────────────────────

KAFKA / REDPANDA PRODUCTION

Complete:

• Multi-broker
• Multi-AZ
• Replication
• TLS
• Authentication
• Persistent storage
• Monitoring

Monitor:

• Consumer lag
• Broker health
• Disk
• Throughput
• Under-replicated partitions
• Partition skew

────────────────────────────────────────

OPENSEARCH PRODUCTION

Complete:

• Multi-node
• Multi-AZ
• Encryption
• Access policy
• Snapshots
• Monitoring

Monitor:

• JVM
• CPU
• Memory
• Disk
• Indexing latency
• Search latency
• Cluster health

Search indexes remain rebuildable.

────────────────────────────────────────

S3 MEDIA INFRASTRUCTURE

Complete storage for:

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
• Lifecycle
• Versioning where required
• Replication where required
• Block public access

────────────────────────────────────────

S3 LIFECYCLE

Define separate retention for:

• Abandoned uploads
• Temporary processing assets
• Failed processing
• Masters
• Renditions
• Reports
• Privacy exports

Do not delete authoritative media without verification.

────────────────────────────────────────

CDN

Complete CloudFront for:

• Video
• HLS manifests
• Video segments
• Thumbnails
• Posters
• Static web assets

Configure:

• Origin Access Control
• Cache policies
• Response headers
• TLS
• WAF
• Access logging where appropriate

────────────────────────────────────────

PLAYBACK ACCESS

Infrastructure must support secure playback using:

• Short-lived signed URLs/cookies
• Origin protection
• No public S3 origin
• Cache-safe media paths

Do not expose origin storage publicly.

────────────────────────────────────────

WAF

Protect:

• Web
• Public APIs
• Upload APIs
• Admin APIs
• Webhooks

Use:

• Managed rules
• Rate-based rules
• Request-size limits
• IP rules
• Bot controls where appropriate

────────────────────────────────────────

SECRETS

Use AWS Secrets Manager for:

• Database
• Redis
• Kafka
• Search
• Maps
• Notification
• Moderation providers
• Rights providers
• Advertising providers
• OAuth
• Webhook secrets

Integrate into Kubernetes through approved secret-management mechanisms.

────────────────────────────────────────

SECRETS ROTATION

Design safe rotation for:

• Database credentials
• Redis credentials
• Kafka credentials
• Search credentials
• Provider credentials
• Webhook signing secrets

Applications must tolerate credential rotation without destructive restarts where practical.

────────────────────────────────────────

CONTAINER SECURITY

Implement:

• Minimal base images
• Multi-stage builds
• Non-root
• Read-only filesystem where possible
• Dropped capabilities
• Seccomp
• Dependency pinning
• SBOM
• Vulnerability scanning
• Image signing
• Provenance

Block release according to security policy thresholds.

────────────────────────────────────────

AUTOSCALING

Configure:

• HPA
• Karpenter or Cluster Autoscaler
• Queue-based scaling
• Kafka-lag scaling

Scale by:

• CPU
• Memory
• Requests
• Queue depth
• Kafka lag
• WebSocket count
• Media-processing throughput
• Recommendation workload

────────────────────────────────────────

FEED AUTOSCALING

Scale feed workloads according to:

• Requests per second
• Feed latency
• Candidate-generation latency
• Cache misses
• CPU
• Memory

Avoid scaling only on CPU.

────────────────────────────────────────

RECOMMENDATION AUTOSCALING

Scale by:

• Recommendation request rate
• Candidate generation latency
• Ranking latency
• Queue depth
• CPU
• Memory

Separate high-cost ranking infrastructure from general API capacity.

────────────────────────────────────────

SEARCH AUTOSCALING

Scale where supported using:

• Search throughput
• Indexing throughput
• Latency
• JVM/CPU
• Queue depth

Do not overload the cluster during reindexing.

────────────────────────────────────────

NOTIFICATION AUTOSCALING

Scale workers according to:

• Queue depth
• Delivery latency
• Provider throttling
• Failure rate

Protect external providers with controlled concurrency.

────────────────────────────────────────

OBSERVABILITY

Complete:

• OpenTelemetry Collector
• Prometheus
• Grafana
• Loki
• Tempo

Create dashboards for:

PLATFORM

• Request rate
• Latency
• Error rate
• Saturation

MEDIA

• Upload rate
• Processing backlog
• Processing duration
• Transcoding utilization
• Failed jobs

FEED

• Feed request rate
• Feed latency
• Candidate latency
• Ranking latency
• Cache hit ratio

RECOMMENDATION

• Request rate
• Model latency
• Feature latency
• Cache
• Queue

SEARCH

• Query rate
• Latency
• Indexing
• Freshness
• Cluster health

MESSAGING

• Connections
• Throughput
• Delivery latency

MODERATION

• Queue
• Processing latency
• Failure

ANALYTICS

• Event rate
• Consumer lag
• Processing lag

ADVERTISING

• Request rate
• Impression processing
• Queue lag

────────────────────────────────────────

TRACING

Propagate trace context across:

• HTTP
• WebSockets where feasible
• Kafka
• BullMQ
• Database calls
• Redis
• External providers

Correlate:

• Request ID
• Correlation ID
• Trace ID
• Event ID
• Job ID

────────────────────────────────────────

SLO / SLI

Define SLOs for:

• Authentication
• Feed
• Recommendation
• Search
• Upload initialization
• Media processing
• Playback authorization
• Messaging
• Notifications
• Moderation
• Analytics ingestion
• Advertising APIs
• Privacy operations

For each define:

• SLI
• Measurement source
• Target
• Alert threshold
• Error budget

────────────────────────────────────────

ALERTS

Create alerts for:

• API outage
• Elevated API errors
• High latency
• Feed degradation
• Recommendation failures
• Search failures
• Upload failures
• Media backlog
• Transcoding backlog
• Kafka lag
• Queue backlog
• Redis memory pressure
• Database saturation
• OpenSearch degradation
• WebSocket drops
• CDN errors
• Payment/advertising-provider dependency failure where infrastructure visibility exists
• Backup failure
• Certificate expiration
• Region health degradation
• Security findings

────────────────────────────────────────

BACKUP

Configure:

• PostgreSQL backups
• PITR
• S3 versioning
• S3 replication where required
• OpenSearch snapshots
• Terraform state protection
• Configuration backup

Encrypt all backups.

────────────────────────────────────────

RESTORE TESTING

Validate actual restoration for:

• PostgreSQL
• S3
• OpenSearch
• Terraform state
• Critical configuration

Record:

• Start
• Duration
• Result
• RTO
• RPO
• Recovery dependencies

A backup is not considered operationally valid until restoration succeeds.

────────────────────────────────────────

DISASTER RECOVERY

Test recovery from:

• Pod loss
• Node failure
• AZ failure
• EKS failure
• PostgreSQL failure
• Redis failure
• Kafka failure
• Search failure
• S3 disruption
• Region failure

Recovery must include:

• Detection
• Failover
• Restoration
• Reconciliation
• Validation
• Failback

────────────────────────────────────────

CHAOS / RESILIENCE

Create controlled resilience scenarios for:

• Pod termination
• Node termination
• Media-worker failure
• Feed-worker failure
• Recommendation-worker failure
• Search degradation
• Kafka broker failure
• Redis failover
• PostgreSQL failover
• WebSocket gateway failure
• Region failure

Run first in:

• Test
• Staging

Promote scenarios to production only under controlled operational procedures.

────────────────────────────────────────

INCIDENT RESPONSE

Create operational procedures for:

• API outage
• Feed outage
• Recommendation outage
• Search outage
• Media-processing outage
• Messaging outage
• Notification outage
• Region outage
• Database outage
• Redis outage
• Kafka outage
• Security incident
• Credential compromise

Each incident process includes:

• Detection
• Severity
• Assignment
• Containment
• Mitigation
• Communication
• Recovery
• Validation
• Postmortem
• Corrective action

────────────────────────────────────────

RUNBOOKS

Create runbooks for:

• Failed deployment
• Helm rollback
• Database failover
• Database restore
• Redis failover
• Kafka broker failure
• OpenSearch recovery
• Media backlog
• Recommendation backlog
• Search backlog
• Notification backlog
• Secret rotation
• Certificate renewal
• Region failover
• Backup failure
• EKS outage
• CDN/origin failure

Each runbook must contain:

• Symptoms
• Detection
• Diagnosis
• Immediate mitigation
• Recovery
• Validation
• Escalation

────────────────────────────────────────

COST OPTIMIZATION

Evaluate:

• EKS node right-sizing
• Karpenter
• Spot instances for safe worker workloads
• Reserved capacity
• Savings Plans
• Database right-sizing
• Redis right-sizing
• OpenSearch right-sizing
• S3 lifecycle
• CDN caching
• NAT Gateway cost
• Cross-region transfer
• Log retention
• Media-worker utilization

Never sacrifice:

• Safety
• Security
• Financial integrity
• Required availability
• Required disaster recovery

solely for cost savings.

────────────────────────────────────────

CAPACITY PLANNING

Model:

• Daily active users
• Creators
• Uploads/day
• Video bytes/day
• Watch minutes
• Feed requests
• Recommendation requests
• Search requests
• WebSocket connections
• Messages
• Notifications
• Moderation events
• Analytics events

Estimate:

• Compute
• Memory
• Storage
• Bandwidth
• Kafka throughput
• Redis memory
• Search capacity
• Database capacity

Define:

• Normal
• Peak
• Burst
• Headroom
• Scaling threshold

────────────────────────────────────────

SECURITY OPERATIONS

Implement recurring operational checks for:

• IAM
• OIDC
• KMS
• Secrets
• Security Groups
• NetworkPolicies
• WAF
• Container images
• Dependencies
• EKS
• CloudTrail
• Audit logs

Support:

• Access review
• Credential rotation
• Vulnerability remediation
• Drift detection

────────────────────────────────────────

COMPLIANCE PREPARATION

Prepare infrastructure controls/evidence for:

• SOC 2
• ISO 27001
• GDPR
• PCI DSS scope minimization

Do not claim formal certification without formal assessment.

────────────────────────────────────────

PRODUCTION SMOKE TESTS

After every production deployment validate safely:

• Web
• Authentication
• Video discovery
• Feed
• Search
• Upload initialization
• Media-processing health
• Playback authorization
• Messaging
• Notifications
• Creator APIs
• Advertising APIs
• Admin
• Privacy endpoints

Use synthetic/non-destructive checks wherever possible.

────────────────────────────────────────

INFRASTRUCTURE VALIDATION

Automate:

• Terraform fmt
• Terraform validate
• Terraform plan
• Terraform policy checks
• Helm lint
• Kubernetes schema validation
• Kubernetes security checks
• Docker build
• Container scan
• Image signing validation
• IAM policy validation
• Security-group validation
• NetworkPolicy validation
• WAF validation
• Backup-policy validation

────────────────────────────────────────

RELEASE GATES

Production deployment requires:

• Passing automated tests
• Passing security checks
• Valid artifact signature
• Valid infrastructure state
• Successful staging deployment
• Smoke-test success
• Observability available
• Backup health
• Rollback procedure available
• Required approvals
• Known-risk documentation

────────────────────────────────────────

DOCUMENTATION

Generate:

• Production infrastructure guide
• Terraform operations
• Helm operations
• Kubernetes operations
• CI/CD guide
• Media-processing infrastructure guide
• Autoscaling guide
• Global routing guide
• Multi-region guide
• PostgreSQL operations
• Redis operations
• Kafka operations
• OpenSearch operations
• S3 operations
• CloudFront operations
• WAF operations
• Secrets rotation
• Backup/restore
• Disaster recovery
• Observability
• SLO/SLI
• Alerting
• Incident response
• Runbooks
• Capacity planning
• Cost optimization
• Security operations
• Compliance preparation
• Release management

────────────────────────────────────────

PROJECT INDEX

Update the infrastructure Project Index with:

• AWS accounts
• Regions
• Environments
• VPCs
• Network components
• Security Groups
• IAM roles
• OIDC
• KMS
• Secrets
• EKS clusters
• Node groups
• Namespaces
• Helm charts
• Terraform modules
• Dockerfiles
• ECR repositories
• PostgreSQL
• Redis
• Kafka/Redpanda
• OpenSearch
• S3
• CloudFront
• Route 53
• ACM
• WAF
• Media infrastructure
• Feed infrastructure
• Recommendation infrastructure
• Search infrastructure
• Messaging infrastructure
• Moderation infrastructure
• Analytics infrastructure
• Autoscaling
• CI/CD
• Security scanning
• Observability
• Dashboards
• Alerts
• SLOs
• Backups
• Disaster recovery
• Chaos tests
• Runbooks
• Incident response
• Capacity planning
• Cost controls
• Infrastructure validation
• Production smoke tests
• Release gates
• Generated files
• Modified files
• Remaining work
• Known risks
• Current milestone
• Production-readiness status
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

INFRASTRUCTURE MILESTONE 11

Production Helm charts, workload deployments, worker deployments, resource governance, probes, PDBs, NetworkPolicies, workload identity, and production configuration.

INFRASTRUCTURE MILESTONE 12

Media-processing node pools, FFmpeg worker infrastructure, GPU/hardware acceleration where justified, temporary storage, worker priority, and media autoscaling.

INFRASTRUCTURE MILESTONE 13

Feed, recommendation, search, messaging, moderation, notification, analytics, and privacy workload deployment plus specialized autoscaling.

INFRASTRUCTURE MILESTONE 14

Global traffic management, CloudFront, Route 53, ACM, WAF, ingress, WebSockets, connection draining, weighted rollout, and regional failover.

INFRASTRUCTURE MILESTONE 15

GitHub Actions, OIDC, artifact promotion, ECR, SBOM, image scanning, signing, staging deployment, production deployment, smoke tests, and rollback.

INFRASTRUCTURE MILESTONE 16

Database, Redis, Kafka, OpenSearch, and S3 operational hardening, backup automation, restore testing, migration workflows, and reconciliation support.

INFRASTRUCTURE MILESTONE 17

Observability, tracing, metrics, dashboards, alerts, SLOs, SLIs, capacity metrics, and production diagnostics.

INFRASTRUCTURE MILESTONE 18

Security operations, secrets rotation, IAM reviews, image security, WAF hardening, CloudTrail, audit logging, vulnerability management, and compliance preparation.

INFRASTRUCTURE MILESTONE 19

Multi-region disaster recovery, chaos/resilience scenarios, incident response, runbooks, capacity planning, cost optimization, and regional recovery drills.

INFRASTRUCTURE MILESTONE 20

Production smoke testing, release certification, restore validation, failover validation, final security review, operational audit, documentation, and Project Index completion.

Each milestone should contain approximately 20–40 files where practical.

Every milestone must pass infrastructure validation before proceeding.

────────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never truncate files.

Never summarize infrastructure configuration instead of generating it.

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

This volume completes the production infrastructure and DevOps implementation.

It covers:

• Production Kubernetes
• Helm
• Media-processing infrastructure
• Specialized worker pools
• Autoscaling
• Global traffic
• Multi-region
• CI/CD
• GitHub Actions
• ECR
• Container security
• PostgreSQL operations
• Redis operations
• Kafka operations
• OpenSearch operations
• S3 operations
• CDN
• WAF
• Secrets
• Observability
• SLO/SLI
• Alerts
• Backups
• Restore validation
• Disaster recovery
• Chaos/resilience
• Incident response
• Runbooks
• Capacity planning
• Cost optimization
• Security operations
• Compliance preparation
• Production smoke testing
• Release gates

Do not implement:

• Backend business logic
• Frontend business logic
• Mobile business logic
• Feed algorithms
• Recommendation algorithms
• Video-processing application logic
• Search business logic
• Moderation business logic
• Advertising business logic

Those belong to application layers.

────────────────────────────────────────

QUALITY BAR

Treat this infrastructure as mission-critical global social-video infrastructure supporting:

• Hundreds of millions of users
• Millions of creators
• Millions of uploads per day
• Billions of video impressions
• Massive feed traffic
• Massive recommendation traffic
• Massive CDN traffic
• Large search traffic
• Massive messaging traffic
• Large moderation workloads
• Large analytics workloads
• Multiple regions
• High availability
• Strict privacy
• Strict security
• Disaster recovery
• Continuous delivery

Prioritize:

• Availability
• Security
• Reliability
• Scalability
• Media-processing isolation
• CDN performance
• Regional resilience
• Observability
• Recoverability
• Automation
• Cost awareness
• Maintainability
• Production readiness
