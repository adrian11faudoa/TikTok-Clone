# TikTok-Style Short-Form Video Platform — Infrastructure Prompt — Volume 1

# ROLE

You are the senior **Infrastructure, Cloud, DevOps, Security, and Reliability Engineering Agent** responsible for implementing the production-grade infrastructure foundation for a **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Principal Cloud Architect
* Staff DevOps Engineer
* Kubernetes Engineer
* Infrastructure-as-Code Engineer
* Cloud Security Engineer
* Network Engineer
* Database Reliability Engineer
* SRE
* Observability Engineer
* CI/CD Engineer
* Disaster Recovery Engineer
* Cost Optimization Engineer
* Performance Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the **infrastructure-as-code, containerization, environments, networking, deployment foundations, secrets/configuration boundaries, CI/CD foundations, observability infrastructure, and core operational controls** required to run the project's backend and supporting platform components.

This is a bounded infrastructure implementation milestone.

Do not implement the complete application.

Do not redesign backend, web, or mobile functionality.

Do not invent cloud resources as though they already exist.

Do not claim production infrastructure has been provisioned unless the execution environment actually verifies that provisioning.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator publishing;
* media processing;
* personalized content consumption;
* discovery;
* recommendations;
* social interaction;
* notifications;
* moderation;
* analytics;
* administration;
* production operations.

The completed system is intended to support:

* accounts and profiles;
* social graph;
* video publishing;
* media upload and processing;
* CDN-backed playback;
* feeds;
* recommendations;
* search;
* trending;
* likes;
* comments;
* replies;
* shares;
* favorites;
* notifications;
* moderation;
* reporting;
* creator analytics;
* administration;
* event streaming;
* background jobs;
* observability;
* deployment;
* disaster recovery.

This prompt implements the **infrastructure foundation** required to run these application components consistently across local development and cloud-oriented environments.

---

# TARGET USERS

Infrastructure must support:

* end users;
* creators;
* internal engineers;
* operators;
* moderators;
* administrators;
* CI/CD systems;
* observability systems;
* background workers;
* media-processing workers.

Infrastructure design must treat:

* public traffic;
* uploaded media;
* application payloads;
* background jobs;
* secrets;
* service-to-service communication

according to their security classification.

---

# SCALE TARGET

The completed platform is intended to evolve toward:

* millions to hundreds of millions of users;
* high API request volume;
* very high video playback bandwidth;
* large object-storage growth;
* large media-processing workloads;
* high event-stream throughput;
* high background-job throughput;
* large search infrastructure;
* large notification volume;
* geographically distributed traffic.

This milestone does not require actual global production-scale provisioning.

The infrastructure code must nevertheless avoid architectural decisions that fundamentally prevent:

* horizontal scaling;
* workload isolation;
* autoscaling;
* regional expansion;
* CDN delivery;
* independent worker scaling;
* database scaling;
* observability at high volume.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible and justified alternative, use an infrastructure direction based on:

* Docker;
* Kubernetes for scalable runtime orchestration;
* Helm or another coherent Kubernetes packaging approach;
* Terraform or another production-grade infrastructure-as-code tool;
* GitHub Actions or the repository's established CI/CD platform;
* PostgreSQL;
* Redis;
* Kafka or Redpanda;
* BullMQ-compatible worker workloads;
* S3-compatible object storage;
* CDN-backed media delivery;
* OpenTelemetry;
* Prometheus-compatible metrics;
* Grafana-compatible dashboards;
* centralized structured logging;
* distributed tracing.

The exact cloud provider may be selected by the repository or established project configuration.

If no provider is established, use a provider-neutral architecture where practical and document the provider assumptions necessary for deployment.

Do not deploy both Terraform and another competing IaC system for the same resources unless there is a clearly documented boundary.

---

# REPOSITORY INSPECTION

Before modifying infrastructure:

1. Inspect the repository.
2. Identify existing Dockerfiles.
3. Inspect compose/development configuration.
4. Inspect Kubernetes manifests.
5. Inspect Helm charts if present.
6. Inspect Terraform or other IaC.
7. Inspect CI workflows.
8. Inspect environment configuration.
9. Inspect backend and worker entry points.
10. Inspect database and Redis dependencies.
11. Inspect event-stream configuration.
12. Inspect object-storage configuration.
13. Inspect media-worker requirements.
14. Inspect observability integrations.
15. Inspect existing secrets/configuration handling.
16. Identify compatible existing infrastructure.
17. Preserve working infrastructure where appropriate.
18. Avoid unnecessary migration of IaC tooling.
19. Do not fabricate external infrastructure state.

The repository is authoritative for actual infrastructure state.

This prompt is authoritative for the current infrastructure scope.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the infrastructure foundation required for:

* local development;
* reproducible container builds;
* application runtime;
* background workers;
* media-processing workers;
* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* object storage;
* search infrastructure integration;
* network boundaries;
* ingress;
* TLS configuration boundaries;
* secrets;
* configuration;
* service accounts/IAM;
* health checks;
* autoscaling foundations;
* CI/CD;
* deployment strategies;
* observability infrastructure;
* backup foundations;
* operational documentation.

Do not claim that external resources are provisioned simply because Terraform or Kubernetes manifests exist.

---

# ENVIRONMENT MODEL

Define infrastructure for appropriate environments:

* local;
* development;
* test/CI;
* staging;
* production.

Clearly separate:

* environment configuration;
* secret values;
* resource sizing;
* network configuration;
* observability settings;
* domain names;
* storage buckets;
* database endpoints.

Do not hardcode production values into development configuration.

Do not allow staging to accidentally target production resources.

---

# LOCAL DEVELOPMENT

Implement a reproducible local environment for application dependencies.

Provide, where practical:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* S3-compatible object storage;
* search engine;
* observability dependencies where appropriate.

Use Docker Compose or the repository's established mechanism.

The local environment must allow backend and worker developers to exercise the major infrastructure dependencies without requiring real cloud credentials.

Do not use fake infrastructure when a real local equivalent is practical.

---

# CONTAINERIZATION

Create or refine production-ready container images for applicable workloads:

* backend API;
* background workers;
* media-processing workers;
* web application where infrastructure scope includes it;
* supporting services that must run as repository-owned containers.

Use:

* multi-stage builds where appropriate;
* minimal runtime images;
* non-root users;
* deterministic dependency installation;
* pinned or controlled base-image strategy;
* health checks where appropriate.

Do not include development tooling unnecessarily in production images.

---

# CONTAINER SECURITY

Production containers must:

* run with least privilege;
* avoid root where possible;
* use read-only filesystems where practical;
* drop unnecessary Linux capabilities;
* restrict writable paths;
* avoid privileged mode;
* avoid exposing unnecessary ports;
* avoid embedding secrets.

Media-processing workers require additional resource and isolation controls because they process untrusted files.

---

# IMAGE MANAGEMENT

Define a consistent image lifecycle.

Support:

* immutable image tags or digests;
* version traceability;
* provenance metadata where supported;
* vulnerability scanning;
* controlled promotion from build to deployment.

Do not deploy mutable `latest` tags as the production source of truth.

Do not claim images are vulnerability-free merely because a scanner ran.

---

# KUBERNETES ARCHITECTURE

Where Kubernetes is the selected production runtime, define workload resources for:

* API;
* background workers;
* media workers;
* web application;
* event consumers;
* indexing/recommendation workers where repository-owned infrastructure requires them.

Separate workloads when their:

* scaling patterns;
* resource requirements;
* security boundaries;
* failure characteristics

differ materially.

Do not create a separate deployment for every small application module.

---

# NAMESPACE AND RESOURCE ISOLATION

Use appropriate namespace/environment separation.

Define:

* namespaces;
* labels;
* annotations;
* resource ownership;
* service accounts;
* network policies.

Avoid placing unrelated environments into one shared namespace without clear isolation.

---

# RESOURCE REQUESTS AND LIMITS

Define appropriate Kubernetes:

* CPU requests;
* CPU limits where justified;
* memory requests;
* memory limits;
* ephemeral-storage controls.

Media workers require resource settings appropriate to:

* FFmpeg workload;
* temporary files;
* concurrent processing.

Do not set unlimited memory or CPU.

Do not use arbitrary identical resource values for all workloads.

---

# AUTOSCALING

Implement autoscaling foundations for workloads with variable traffic.

Consider:

* API replicas;
* event consumers;
* background workers;
* media workers.

Autoscaling signals may include:

* CPU;
* memory;
* queue depth;
* event lag;
* request rate;
* latency;
* custom metrics.

Do not autoscale stateful databases as though they were stateless workloads.

---

# NETWORK ARCHITECTURE

Define the production network architecture.

Cover:

* public ingress;
* private application network;
* database network;
* cache network;
* event-stream network;
* object-storage access;
* search access;
* worker network;
* administration access.

Separate public-facing traffic from internal service traffic.

Do not expose:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* internal worker ports

directly to the public internet.

---

# INGRESS

Implement a production ingress boundary.

Support:

* TLS termination;
* HTTP routing;
* backend routing;
* web routing where applicable;
* health checks;
* request-size limits;
* connection/timeouts;
* rate-limiting integration where appropriate.

Do not expose internal services directly when an ingress boundary is required.

---

# TLS

Define TLS infrastructure requirements.

Support:

* HTTPS;
* certificate management;
* secure redirects;
* modern protocol configuration;
* certificate rotation.

Do not commit private certificates or keys.

Infrastructure code may configure certificate resources or secret references without embedding private material.

---

# DNS

Define the required DNS architecture.

Support:

* application hostnames;
* API hostnames;
* media/CDN hostnames;
* administrative hostnames where required;
* environment-specific domains.

Do not hardcode provider credentials.

Do not claim DNS records have been created unless the execution environment verifies them.

---

# IAM / SERVICE ACCOUNTS

Define least-privilege identities for:

* API;
* workers;
* media workers;
* indexing workers;
* notification workers;
* CI/CD;
* infrastructure provisioning.

Each workload must receive only the permissions needed for its function.

Media workers should not receive broad administrative cloud permissions.

---

# OBJECT STORAGE

Define infrastructure integration for object storage.

Create repository-owned configuration or IaC for:

* source uploads;
* processed media;
* thumbnails;
* previews;
* lifecycle rules;
* access policy;
* encryption;
* versioning where justified.

Support secure separation between:

* private upload objects;
* public/CDN-delivered variants;
* temporary processing objects.

Do not expose storage credentials to application clients.

---

# OBJECT STORAGE LIFECYCLE

Define lifecycle policies for:

* abandoned uploads;
* temporary processing objects;
* obsolete variants;
* deleted content;
* stale thumbnails/previews where appropriate.

Avoid indefinite storage growth.

Do not physically delete objects before authoritative ownership/deletion requirements permit it.

---

# CDN

Define CDN integration for media delivery.

Support:

* media hostname;
* origin configuration;
* cache behavior;
* compression where appropriate;
* signed/authorized access;
* invalidation strategy;
* TLS;
* geographic delivery.

Do not assume the CDN is already provisioned.

Do not claim production traffic is flowing through it without verification.

---

# DATABASE INFRASTRUCTURE

Define production-oriented PostgreSQL infrastructure.

Address:

* primary instance;
* read replicas where justified;
* storage sizing;
* encryption;
* backups;
* maintenance;
* connection limits;
* failover;
* monitoring;
* migration execution.

Do not overprovision a large database for every non-production environment.

---

# DATABASE CONNECTION MANAGEMENT

The application infrastructure must prevent database connection exhaustion.

Consider:

* connection pool sizing;
* workload-specific limits;
* worker concurrency;
* autoscaling interaction;
* transaction duration;
* timeout behavior.

Do not multiply maximum connection pools blindly by maximum pod count.

---

# REDIS INFRASTRUCTURE

Define Redis infrastructure for:

* cache;
* rate limiting;
* ephemeral state;
* sessions where applicable;
* background jobs;
* feed/recommendation cache where applicable.

Configure:

* memory policy;
* persistence where required;
* replication/high availability where appropriate;
* network access;
* authentication;
* encryption in transit where supported;
* monitoring.

Do not treat Redis as a universal durable database.

---

# KAFKA / REDPANDA INFRASTRUCTURE

Define event-stream infrastructure for applicable workloads.

Address:

* brokers;
* topics;
* partitions;
* replication;
* retention;
* access control;
* encryption;
* monitoring.

Topics must align with the project's event contracts.

Do not claim a single partition is sufficient for global-scale behavioral events.

Do not create arbitrary partition counts without documenting the workload assumptions.

---

# EVENT RETENTION

Define retention according to event class.

Distinguish:

* behavioral events;
* durable domain events;
* audit-related data.

Do not use one retention policy for all event streams.

High-volume behavioral data requires bounded retention consistent with analytics/recommendation requirements.

---

# SEARCH INFRASTRUCTURE

Provide infrastructure integration for the selected search engine used by the project.

Define:

* node/workload requirements;
* storage;
* networking;
* credentials/identity;
* snapshots;
* monitoring;
* scaling direction.

Where the search provider is managed externally, configure integration boundaries without claiming that the external cluster exists.

---

# BACKGROUND WORKER INFRASTRUCTURE

Define independent worker deployments for:

* general jobs;
* media processing;
* event consumers;
* search indexing;
* analytics aggregation;
* notifications where applicable.

Separate workloads where resource profiles differ.

Media processing should not compete directly with API requests for the same constrained runtime resources.

---

# JOB QUEUE SCALING

Autoscale queue workers according to:

* queue depth;
* processing latency;
* concurrency;
* failure rate.

Define:

* minimum workers;
* maximum workers;
* backoff;
* graceful shutdown;
* termination handling.

Do not allow autoscaling to create an uncontrolled stampede against PostgreSQL, Redis, object storage, or external providers.

---

# GRACEFUL SHUTDOWN

Every long-running workload must support graceful shutdown.

On termination:

* stop accepting new work where appropriate;
* finish or safely abandon active jobs;
* release connections;
* flush telemetry;
* commit/rollback safely;
* acknowledge events only after durable handling.

Do not terminate active media-processing workers in a way that leaves unrecoverable state.

---

# HEALTH PROBES

Configure:

* liveness;
* readiness;
* startup probes where appropriate.

Health checks must test the actual requirements of the workload.

Do not mark an API ready when mandatory initialization or database connectivity is unavailable.

Do not make liveness probes depend on fragile downstream services unnecessarily.

---

# CONFIGURATION MANAGEMENT

Define environment-specific configuration for:

* API;
* web;
* workers;
* database;
* Redis;
* Kafka/Redpanda;
* search;
* object storage;
* CDN;
* authentication;
* notifications;
* observability;
* media processing.

Separate:

* non-secret configuration;
* secret configuration.

Do not commit real secret values.

---

# SECRET MANAGEMENT

Use a production-appropriate secret-management architecture.

Support:

* secret references;
* environment injection;
* workload identity where available;
* secret rotation;
* limited access;
* auditability.

Never hardcode:

* database passwords;
* Redis passwords;
* Kafka credentials;
* cloud access keys;
* signing secrets;
* push-provider credentials;
* TLS private keys.

---

# SECRETS IN CI/CD

CI/CD systems must use:

* federated identity/OIDC where supported;
* short-lived credentials;
* repository/environment secrets;
* least privilege.

Avoid long-lived cloud credentials in CI when workload identity is available.

Do not print secrets in build logs.

---

# NETWORK POLICIES

Define Kubernetes/network-level controls where applicable.

Restrict:

* public-to-internal access;
* service-to-service access;
* worker-to-database access;
* media-worker network access;
* administrative access.

Media-processing workers should have the minimum network access necessary.

---

# WAF / EDGE SECURITY

Where supported by the selected infrastructure, configure the edge security boundary for:

* malicious requests;
* common web attacks;
* request-size restrictions;
* rate limiting;
* IP-based controls where appropriate;
* bot/abuse mitigation.

Do not rely on the WAF as a substitute for application authorization.

---

# RATE-LIMIT INFRASTRUCTURE

Provide infrastructure support for application rate limiting through the project's Redis/edge architecture.

Ensure:

* bounded state;
* TTL;
* environment isolation;
* observability.

Do not implement rate limiting twice with conflicting limits unless each layer has a clearly documented purpose.

---

# OBSERVABILITY INFRASTRUCTURE

Implement repository-owned configuration for:

* metrics;
* logs;
* traces;
* dashboards;
* alerting;
* health monitoring.

Use OpenTelemetry-compatible instrumentation paths.

Support observability for:

* API;
* workers;
* media workers;
* database;
* Redis;
* Kafka/Redpanda;
* search;
* object storage;
* ingress.

---

# LOGGING

Define centralized structured logging.

Support:

* timestamp;
* severity;
* service;
* environment;
* request/correlation ID;
* trace ID;
* span ID;
* job ID;
* event ID.

Do not log:

* passwords;
* access tokens;
* refresh tokens;
* secrets;
* database credentials;
* push tokens;
* private cryptographic material.

---

# METRICS

Provide infrastructure metrics for:

* request rate;
* latency;
* errors;
* pod health;
* CPU;
* memory;
* restart count;
* queue depth;
* event lag;
* media-processing duration;
* database connections;
* Redis memory;
* search health;
* object-storage failures.

Define useful alert thresholds as configuration rather than undocumented tribal knowledge.

---

# TRACING

Configure distributed tracing propagation across:

* ingress;
* API;
* PostgreSQL;
* Redis;
* event producers/consumers;
* background jobs;
* media workers;
* external providers.

Do not collect unnecessary sensitive payload content inside traces.

---

# DASHBOARDS

Create operational dashboards for at least:

* API health;
* worker health;
* media-processing pipeline;
* database;
* Redis;
* Kafka/Redpanda;
* search;
* infrastructure resources.

Dashboards must measure real signals.

Do not create decorative dashboards with metrics that cannot be collected.

---

# ALERTING

Define alerts for meaningful incidents such as:

* high API error rate;
* elevated latency;
* database connection exhaustion;
* Redis memory pressure;
* event lag;
* queue backlog;
* media-processing failure spike;
* storage failure;
* search failure;
* pod crash loops;
* insufficient capacity;
* certificate expiration;
* backup failure.

Avoid alerting on every transient error.

Alerts should be actionable.

---

# CI/CD

Implement a production-oriented CI/CD pipeline.

Pipeline stages should include, as appropriate:

* dependency installation;
* formatting/linting;
* type checking;
* unit tests;
* integration tests;
* security scanning;
* container build;
* image vulnerability scanning;
* artifact publication;
* infrastructure validation;
* deployment validation.

Do not deploy code that fails required quality gates.

---

# INFRASTRUCTURE VALIDATION

CI should validate infrastructure changes through:

* formatting;
* static analysis;
* Terraform plan/validation where applicable;
* Kubernetes manifest validation;
* Helm validation where applicable;
* policy checks;
* security scanning.

Do not automatically apply infrastructure changes to production on every pull request.

---

# ENVIRONMENT PROMOTION

Use an explicit promotion model:

* build once;
* validate;
* promote the same artifact through environments where practical.

Do not rebuild materially different artifacts for every environment without a documented reason.

Separate environment configuration from immutable application artifacts.

---

# DEPLOYMENT STRATEGY

Implement a deployment strategy appropriate to the application.

Support:

* rolling deployments;
* health-gated rollout;
* graceful termination;
* rollback;
* backward-compatible database migrations.

Where useful, provide:

* canary;
* blue/green;
* controlled traffic shifting.

Do not introduce complex traffic strategies without a concrete operational need.

---

# DATABASE MIGRATION DEPLOYMENT

Infrastructure must support safe schema evolution.

Use ordering such as:

1. backward-compatible schema addition;
2. application rollout;
3. data migration/backfill;
4. cleanup/removal later.

Do not deploy destructive schema changes before compatible application versions are no longer running.

---

# BACKUP INFRASTRUCTURE

Implement backup configuration for:

* PostgreSQL;
* object storage where the provider requires additional backup protection;
* other durable infrastructure where appropriate.

Define:

* frequency;
* retention;
* encryption;
* storage location;
* restoration process.

Do not assume replication is equivalent to backup.

---

# RESTORE VALIDATION

Provide repository documentation and automation hooks for restore testing.

Restore procedures must verify:

* database integrity;
* application connectivity;
* object accessibility where applicable;
* required secrets/configuration;
* event/rebuild dependencies.

Do not claim backups are recoverable without restore verification.

---

# DISASTER RECOVERY FOUNDATION

Define infrastructure paths for:

* database failure;
* availability-zone failure;
* worker fleet failure;
* Redis loss;
* event-broker failure;
* search failure;
* object-storage disruption;
* regional outage where applicable.

Distinguish:

* durable systems;
* rebuildable derived systems;
* cache systems.

Do not attempt active-active multi-region deployment unless the current architecture and operational requirements justify its complexity.

---

# CAPACITY PLANNING

Define initial infrastructure capacity assumptions for:

* API;
* workers;
* media workers;
* database;
* Redis;
* event streaming;
* search;
* object storage;
* CDN.

Document:

* assumed baseline traffic;
* expected burst factor;
* scaling trigger;
* capacity expansion path.

Do not claim these values are production measurements.

---

# COST CONTROLS

Implement cost-aware infrastructure practices.

Consider:

* environment-specific sizing;
* autoscaling;
* log retention;
* metric/cardinality control;
* object-storage lifecycle;
* CDN caching;
* idle development resources;
* database right-sizing;
* worker concurrency.

Avoid creating production-sized infrastructure for local/test environments.

---

# SECURITY SCANNING

Add automated security checks where practical for:

* dependencies;
* container images;
* IaC;
* Kubernetes configuration;
* secrets;
* permissions.

Security scanning must fail or warn according to documented severity policy.

Do not automatically suppress vulnerabilities without a documented reason.

---

# SUPPLY-CHAIN SECURITY

Where practical implement:

* lockfiles;
* dependency pinning;
* trusted registries;
* provenance/attestation;
* image signing;
* SBOM generation.

Do not claim complete supply-chain security merely because an SBOM exists.

---

# RESOURCE TAGGING

Cloud resources should carry useful tags/labels such as:

* project;
* environment;
* component;
* owner;
* cost category;
* managed-by.

Use the provider's supported tagging model.

Do not introduce personally identifying information into tags unnecessarily.

---

# ENVIRONMENT ISOLATION

Ensure:

* development cannot accidentally target production;
* test data cannot overwrite production data;
* local credentials cannot grant production access;
* CI roles are scoped to intended environments.

Use separate accounts/projects/subscriptions where the cloud architecture warrants it.

---

# OPERATIONAL RUNBOOKS

Create runbooks for:

* deployment failure;
* rollback;
* database outage;
* Redis outage;
* event-broker outage;
* queue backlog;
* media-processing failure;
* object-storage outage;
* search outage;
* certificate expiration;
* excessive API errors;
* failed backups;
* restore.

Runbooks must contain actionable commands/procedures appropriate to the actual infrastructure.

Do not document commands for resources that do not exist.

---

# INFRASTRUCTURE TESTING

Implement tests appropriate to this milestone, including:

* IaC validation;
* policy validation;
* container build validation;
* image startup tests;
* Kubernetes manifest validation;
* Helm validation where applicable;
* Compose startup validation;
* configuration validation;
* health-check validation;
* deployment smoke tests;
* security scanning.

Where local integration infrastructure is available, verify that the backend can connect to:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* object storage;
* search.

Do not claim provider-level connectivity without actually testing it.

---

# CHAOS / FAILURE VALIDATION FOUNDATION

Where practical, create safe test procedures for:

* killing API instances;
* restarting workers;
* queue backlog;
* Redis interruption;
* event-broker interruption;
* database connection saturation;
* media-worker termination.

The objective is to verify graceful recovery behavior.

Do not conduct destructive tests against production unless explicit operational authorization and safeguards exist.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* local infrastructure;
* Dockerfiles;
* container hardening;
* container image workflow;
* Kubernetes workload foundations where selected;
* Helm packaging where selected;
* Terraform/IaC foundation;
* environment separation;
* networking;
* ingress;
* TLS configuration boundaries;
* DNS configuration boundaries;
* IAM/service identities;
* object-storage configuration;
* CDN integration configuration;
* PostgreSQL infrastructure configuration;
* Redis infrastructure configuration;
* Kafka/Redpanda infrastructure configuration;
* search infrastructure integration;
* background-worker deployments;
* media-worker deployments;
* autoscaling foundations;
* health probes;
* graceful shutdown infrastructure;
* configuration management;
* secret-management integration;
* network policies;
* edge/WAF configuration where appropriate;
* observability infrastructure;
* dashboards;
* alerts;
* CI/CD foundation;
* infrastructure validation;
* deployment strategy;
* migration-deployment strategy;
* backup configuration;
* restore procedures;
* disaster-recovery foundation;
* capacity-planning configuration;
* cost controls;
* supply-chain/security scanning;
* resource tagging;
* environment isolation;
* operational runbooks;
* infrastructure tests;
* safe failure-testing foundations;
* documentation.

This prompt does **not** implement:

* application business logic;
* backend domain functionality;
* web application functionality;
* mobile application functionality;
* advanced recommendation algorithms;
* complete search application behavior;
* complete moderation workflows;
* full QA automation;
* live cloud provisioning unless explicitly executed and verified;
* production credential creation;
* production certificate issuance without access to the required infrastructure;
* unrequested multi-region active-active deployment.

Create infrastructure interfaces that support the application components already defined by the project architecture.

---

# SECURITY

Infrastructure must enforce:

* least privilege;
* non-root containers where possible;
* encrypted transport;
* secret isolation;
* private service networking;
* workload identity where available;
* network segmentation;
* restricted administrative access;
* secure artifact handling;
* auditability.

Never commit:

* cloud secrets;
* database passwords;
* private keys;
* provider tokens;
* production certificates;
* push credentials.

Search the repository for accidental secrets before completion.

---

# RELIABILITY

Infrastructure must support:

* health-gated deployment;
* graceful shutdown;
* redundancy where justified;
* backup;
* restore;
* rollback;
* autoscaling;
* failure isolation;
* bounded retries;
* queue recovery;
* event recovery;
* database recovery.

Do not introduce single points of failure unnecessarily.

Do not overbuild highly available infrastructure for components whose data can be reconstructed cheaply.

---

# APPLICATION COMPATIBILITY

The infrastructure must support:

* backend API;
* web application;
* mobile API access;
* media upload;
* media processing;
* CDN playback;
* Redis;
* event streaming;
* background jobs;
* search;
* notifications;
* recommendation services;
* moderation services;
* analytics;
* observability.

Preserve the project's established ports, environment variables, service names, health endpoints, and connection conventions.

Do not invent incompatible service naming.

---

# EXTERNAL ENVIRONMENT REALISM

Distinguish clearly between:

* infrastructure code in the repository;
* local infrastructure;
* CI infrastructure;
* staging infrastructure;
* production infrastructure;
* externally managed services.

When provider credentials or access are unavailable:

* validate IaC syntax;
* validate policies;
* build containers;
* test local infrastructure;
* run static checks;
* report provider-level validation as unavailable.

Do not fabricate successful Terraform applies, Kubernetes rollouts, cloud resource creation, DNS propagation, certificate issuance, or CDN traffic.

---

# VALIDATION

After implementation:

1. Run infrastructure formatting.
2. Run IaC validation.
3. Run IaC security/policy checks where configured.
4. Validate Kubernetes manifests.
5. Validate Helm charts where used.
6. Validate Docker builds.
7. Run container security scanning.
8. Run secret scanning.
9. Validate local development infrastructure.
10. Start applicable local dependencies.
11. Validate health endpoints.
12. Validate backend connectivity to infrastructure dependencies where available.
13. Validate CI workflows syntactically.
14. Validate deployment manifests.
15. Validate configuration schemas.
16. Validate backup configuration.
17. Validate restore procedures where practical.
18. Run infrastructure smoke tests.
19. Run safe failure/recovery tests where practical.
20. Inspect the final diff.
21. Search for credentials and secrets.
22. Verify no production resource is claimed as provisioned without verification.
23. Verify no unrelated application subsystem was modified.

Do not hide infrastructure validation failures.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* local development infrastructure;
* Docker/container changes;
* Kubernetes resources;
* Helm resources;
* Terraform/IaC resources;
* environment configuration;
* networking;
* ingress;
* TLS;
* DNS;
* IAM/service identities;
* object-storage configuration;
* CDN configuration;
* PostgreSQL infrastructure;
* Redis infrastructure;
* Kafka/Redpanda infrastructure;
* search infrastructure;
* worker infrastructure;
* media-worker infrastructure;
* autoscaling;
* health probes;
* configuration/secrets;
* network policies;
* WAF/edge controls;
* observability;
* dashboards;
* alerts;
* CI/CD;
* deployment strategy;
* database migration strategy;
* backups;
* restore procedures;
* disaster-recovery foundations;
* cost controls;
* security scanning;
* supply-chain controls;
* runbooks;
* infrastructure tests;
* validation performed;
* external infrastructure that was not accessible;
* known limitations;
* unresolved issues.

Do not claim cloud infrastructure was provisioned unless the execution environment verified it.

---

# DEFINITION OF DONE

This infrastructure foundation milestone is complete only when:

* the repository was inspected;
* the infrastructure toolchain is coherent;
* local development dependencies are reproducible;
* production containers are implemented where required;
* containers use secure defaults;
* production workloads do not require root unnecessarily;
* image builds are deterministic enough for the project's requirements;
* image versioning is explicit;
* Kubernetes workload definitions exist where Kubernetes is selected;
* environments are separated;
* resource requests/limits are defined appropriately;
* autoscaling foundations exist where justified;
* ingress is defined;
* TLS is defined;
* DNS boundaries are defined;
* internal data services are not publicly exposed;
* IAM/service identities are least-privileged;
* object storage is configured appropriately;
* media storage lifecycle is bounded;
* CDN integration is defined;
* PostgreSQL infrastructure is defined;
* database connection capacity is considered;
* Redis infrastructure is defined;
* Kafka/Redpanda infrastructure is defined;
* event retention is defined;
* search infrastructure integration is defined;
* workers are independently deployable where justified;
* media workers have appropriate isolation and resource limits;
* graceful shutdown is configured;
* health/readiness/startup behavior is configured;
* application configuration is environment-specific;
* secrets are not hardcoded;
* secret management boundaries are defined;
* network policies are implemented where supported;
* edge/WAF controls are defined where appropriate;
* rate-limit infrastructure support is defined;
* metrics infrastructure is implemented;
* structured logging infrastructure is implemented;
* tracing infrastructure is implemented;
* operational dashboards exist;
* actionable alerts exist;
* CI/CD performs required validation;
* container and IaC security scanning exists;
* deployment strategy is defined;
* rollback behavior is supported;
* database migration deployment ordering is defined;
* backups are configured;
* restore procedures are documented/tested where practical;
* disaster-recovery foundations exist;
* capacity assumptions are documented;
* cost controls exist;
* supply-chain controls are implemented where practical;
* resource tagging is defined;
* environment isolation prevents accidental cross-environment access;
* operational runbooks exist;
* infrastructure tests exist;
* local or test infrastructure connectivity has been validated where available;
* provider-level limitations are accurately reported;
* no production provisioning is claimed without verification;
* no hardcoded credentials or secrets exist;
* no unrelated application subsystem was implemented;
* compatibility with backend, web, mobile, media, events, queues, search, recommendation, notifications, moderation, analytics, and QA is preserved;
* documentation reflects actual infrastructure;
* validation failures are accurately reported;
* the implementation report accurately reflects the work performed.

Implement **only the current prompt's scope**.

Do not expand this milestone into full application implementation or unverified cloud provisioning.
