# TikTok-Style Short-Form Video Platform — Infrastructure Prompt — Volume 2

# ROLE

You are the senior **Production Infrastructure, Reliability, Observability, Security, Disaster Recovery, and Operational Readiness Engineering Agent** responsible for completing the production-operational infrastructure of a **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Principal Cloud Architect
* Staff SRE
* Staff DevOps Engineer
* Kubernetes Engineer
* Database Reliability Engineer
* Distributed Systems Operations Engineer
* Media Infrastructure Engineer
* Security Engineer
* Observability Engineer
* CI/CD Engineer
* Disaster Recovery Engineer
* Performance / Capacity Engineer
* Cost Optimization Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the **advanced production operations, workload scaling, stateful-service reliability, observability, backup/restore automation, disaster-recovery mechanisms, resilience validation, deployment safety, security hardening, capacity management, and operational tooling** required to operate the platform reliably at its intended scale.

This is a bounded infrastructure implementation milestone.

Do not implement application business logic.

Do not redesign backend, web, or mobile functionality.

Do not claim that external cloud resources, production clusters, DNS records, certificates, databases, or third-party services have been provisioned unless the execution environment actually verifies them.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator publishing;
* media ingestion and processing;
* personalized content consumption;
* discovery;
* recommendations;
* social interaction;
* notifications;
* moderation;
* analytics;
* administration;
* production operations.

The completed platform is intended to support:

* accounts and profiles;
* social graph;
* short-form video publishing;
* secure media uploads;
* transcoding;
* thumbnails and variants;
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
* behavioral events;
* notifications;
* moderation;
* reporting;
* administration;
* creator analytics;
* event streaming;
* background jobs;
* observability;
* deployment;
* backup and recovery.

This prompt completes the **advanced infrastructure and operational engineering required to make those application systems resilient, observable, scalable, recoverable, and safely deployable**.

---

# TARGET USERS

Infrastructure must support:

* end users;
* creators;
* application workloads;
* asynchronous workers;
* media-processing workers;
* search and recommendation workloads;
* moderators;
* administrators;
* internal engineering teams;
* SRE/operations teams;
* CI/CD systems.

Operational infrastructure must protect sensitive workloads and isolate administrative access.

---

# SCALE TARGET

The completed infrastructure must be capable of evolving toward:

* millions to hundreds of millions of users;
* very high API request volume;
* high concurrent feed consumption;
* substantial upload volume;
* very high media-processing throughput;
* large object-storage growth;
* large CDN traffic;
* high event-stream throughput;
* large search workloads;
* high notification throughput;
* geographically distributed traffic;
* burst traffic caused by viral content.

This milestone does not require physically provisioning that full scale.

It must establish the infrastructure mechanisms required to **approach and validate** the stated scale progressively.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible and justified alternative, use the infrastructure architecture already established by the project, including:

* Docker;
* Kubernetes;
* Helm or the established Kubernetes packaging mechanism;
* Terraform or the repository's established infrastructure-as-code tool;
* CI/CD through the repository's established platform;
* PostgreSQL;
* Redis;
* Kafka or Redpanda;
* object storage;
* CDN;
* search infrastructure;
* OpenTelemetry;
* Prometheus-compatible metrics;
* Grafana-compatible dashboards;
* centralized structured logging;
* distributed tracing.

Preserve compatible infrastructure tooling.

Do not introduce a second competing deployment platform or IaC system.

---

# REPOSITORY INSPECTION

Before implementation:

1. Inspect the repository's infrastructure from end to end.
2. Inspect Dockerfiles and image definitions.
3. Inspect Kubernetes manifests.
4. Inspect Helm charts where present.
5. Inspect Terraform or other IaC.
6. Inspect CI/CD workflows.
7. Inspect environment-specific configuration.
8. Inspect service accounts and IAM definitions.
9. Inspect network policies.
10. Inspect observability configuration.
11. Inspect backup and restore configuration.
12. Inspect deployment and rollback mechanisms.
13. Inspect PostgreSQL, Redis, event-streaming, search, and object-storage infrastructure.
14. Inspect autoscaling.
15. Inspect existing runbooks and operational documentation.
16. Inspect infrastructure tests.
17. Inspect current security scans and policy checks.
18. Identify incomplete or conflicting operational infrastructure.
19. Preserve compatible infrastructure.
20. Do not fabricate repository state.

The repository is authoritative for actual infrastructure state.

This prompt is authoritative for the current infrastructure milestone.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement or complete the infrastructure required for:

* production-grade workload scaling;
* advanced autoscaling;
* queue/event-driven scaling;
* stateful-service reliability;
* PostgreSQL high availability;
* PostgreSQL backup and recovery;
* Redis resilience;
* event-stream resilience;
* search resilience;
* object-storage lifecycle and recovery;
* media-worker isolation;
* CDN operational controls;
* production observability;
* SLO/SLI monitoring;
* alerting;
* incident diagnostics;
* deployment safety;
* rollback;
* progressive delivery;
* disaster recovery;
* restore automation;
* resilience testing;
* capacity planning;
* cost controls;
* security hardening;
* policy enforcement;
* auditability;
* operational runbooks;
* infrastructure-level integration testing.

---

# PRODUCTION WORKLOAD TOPOLOGY

Refine the runtime topology for:

* web application;
* API;
* background jobs;
* media-processing workers;
* event consumers;
* search indexing workers;
* recommendation workers;
* notification workers;
* analytics workers;
* moderation workers where infrastructure is repository-owned.

Workloads with different:

* CPU;
* memory;
* I/O;
* network;
* concurrency;
* scaling

profiles must not unnecessarily share the same worker pool.

---

# WORKLOAD SCALING

Implement explicit scaling behavior for stateless workloads.

Scale using appropriate metrics such as:

* CPU;
* memory;
* request rate;
* queue depth;
* event lag;
* processing latency;
* custom application metrics.

Avoid scaling every workload from CPU alone.

Do not configure aggressive autoscaling without considering downstream capacity.

---

# QUEUE-AWARE AUTOSCALING

Where supported by the infrastructure stack, implement scaling based on:

* queue depth;
* oldest-job age;
* processing latency;
* consumer lag.

Apply this to workloads such as:

* media processing;
* notifications;
* analytics aggregation;
* search indexing;
* event consumers.

Do not let autoscaling exceed safe limits for:

* PostgreSQL;
* Redis;
* object storage;
* external APIs.

---

# KUBERNETES DISRUPTION CONTROLS

Implement where appropriate:

* PodDisruptionBudgets;
* topology spread constraints;
* anti-affinity;
* rolling-update settings;
* termination grace periods;
* readiness gates where useful.

Ensure planned maintenance does not unnecessarily remove all replicas of a critical stateless service.

---

# NODE / FAILURE-DOMAIN AWARENESS

Where infrastructure supports it, distribute critical replicas across failure domains.

Consider:

* availability zones;
* node pools;
* workload classes;
* storage locality.

Do not claim multi-zone resilience if all workloads still depend on a single failure domain.

---

# STATEFUL SERVICE RELIABILITY

Define production reliability for:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* search.

For each, document:

* replication;
* failover;
* persistence;
* recovery;
* backup;
* monitoring;
* replacement/rebuild.

Do not apply stateless workload patterns blindly to stateful systems.

---

# POSTGRESQL HIGH AVAILABILITY

Implement or configure the repository-side infrastructure needed for PostgreSQL availability.

Where provider capabilities permit, support:

* automated failover;
* replicas;
* health checks;
* connection management;
* maintenance;
* backup retention;
* point-in-time recovery;
* encryption;
* monitoring.

Do not claim a production failover cluster exists unless it was provisioned and verified.

---

# POSTGRESQL CONNECTION CONTROL

Coordinate:

* API replica count;
* worker replica count;
* media worker behavior;
* connection pool sizes;
* migration jobs.

Prevent connection storms during:

* deployment;
* autoscaling;
* failover;
* recovery.

Where appropriate, support connection pooling infrastructure or managed-provider pooling.

---

# POSTGRESQL BACKUP

Implement robust backup strategy.

Support:

* automated backups;
* point-in-time recovery where available;
* retention;
* encryption;
* backup monitoring;
* failure alerting;
* off-instance/independent storage.

Replication alone is not a backup strategy.

---

# POSTGRESQL RESTORE AUTOMATION

Create repository-side procedures or automation for:

* selecting a backup;
* restoring into isolated recovery infrastructure;
* validating schema;
* validating critical tables;
* checking application connectivity;
* recording restore duration and outcome.

Do not perform destructive restores against production as part of routine CI.

---

# RESTORE DRILLS

Create a repeatable non-production restore drill.

The drill must verify:

* backup exists;
* restore succeeds;
* database is internally consistent;
* required extensions/configuration exist;
* application connectivity works;
* critical queries succeed.

Do not report successful disaster recovery based solely on backup creation.

---

# REDIS RESILIENCE

Configure Redis appropriately for its actual uses.

Where justified, support:

* replication;
* automated failover;
* persistence for state that requires it;
* memory limits;
* eviction policies;
* monitoring;
* client connection limits.

Separate durable requirements from cache/ephemeral requirements.

A Redis outage must not destroy authoritative PostgreSQL state.

---

# REDIS RECOVERY

Document and test expected behavior after:

* primary restart;
* failover;
* data loss;
* cache flush;
* stale cache;
* temporary connectivity loss.

Validate that application components degrade correctly according to their purpose.

Do not treat recovery from cache loss as equivalent to database recovery.

---

# KAFKA / REDPANDA RESILIENCE

Implement infrastructure for durable event streaming.

Address:

* replication factor;
* partition distribution;
* broker failure;
* retention;
* disk usage;
* producer acknowledgment;
* consumer lag;
* restart behavior;
* access control;
* encryption.

Configure topic-level retention appropriate to event class.

---

# EVENT BROKER FAILURE HANDLING

Validate infrastructure behavior when:

* a broker restarts;
* a consumer restarts;
* a partition becomes unavailable;
* lag increases;
* disk utilization grows;
* a consumer group falls behind.

Do not silently discard critical events.

Do not let backlog recovery overwhelm downstream databases.

---

# SEARCH RESILIENCE

Configure search infrastructure for:

* replication;
* shard/index lifecycle;
* snapshot/backup;
* health monitoring;
* disk thresholds;
* failed-node behavior;
* rolling upgrades.

Search remains a derived system.

Ensure it can be rebuilt from authoritative data.

---

# SEARCH RECOVERY

Create operational procedures for:

* snapshot restore;
* full index rebuild;
* partial reindex;
* alias switching;
* failed indexing recovery.

Do not make the application depend on a single unrecoverable search index.

---

# OBJECT STORAGE RECOVERY

Ensure object-storage architecture supports:

* durability;
* lifecycle;
* encryption;
* access control;
* versioning where appropriate;
* deletion;
* temporary-object cleanup;
* recovery procedures.

For critical media assets, define the recovery implications of:

* accidental deletion;
* corrupted processing output;
* orphaned objects;
* lifecycle-policy mistakes.

---

# MEDIA WORKER ISOLATION

Media processing is a high-risk workload.

Implement infrastructure controls for:

* CPU limits;
* memory limits;
* ephemeral storage limits;
* process execution limits;
* concurrency limits;
* restricted service accounts;
* restricted network access;
* temporary workspace isolation;
* node-pool separation where justified.

Do not allow a malformed media file to consume unrestricted cluster resources.

---

# MEDIA WORKER AUTOSCALING

Scale media workers using meaningful signals such as:

* queue depth;
* oldest-job age;
* processing latency.

Respect:

* CPU;
* memory;
* temporary disk capacity;
* object-storage throughput.

Do not scale to a level that causes storage, database, or network saturation.

---

# CDN OPERATIONS

Configure operational controls for:

* cache behavior;
* origin protection;
* signed access;
* cache invalidation;
* error handling;
* traffic visibility;
* rate controls.

Where supported, protect origins so ordinary clients cannot bypass the intended CDN/access architecture.

---

# CDN ORIGIN SECURITY

Ensure object storage/media origin is not broadly exposed when the architecture intends CDN-only controlled delivery.

Use:

* origin access controls;
* signed requests;
* private buckets;
* controlled origins.

Do not depend on obscurity of bucket URLs.

---

# TRAFFIC MANAGEMENT

Implement edge-level controls where appropriate for:

* request rate limits;
* connection limits;
* payload limits;
* abusive traffic;
* bot protection;
* DDoS mitigation integration.

Do not treat infrastructure edge controls as a replacement for application authorization.

---

# WAF POLICY

Define WAF protections appropriate to:

* API;
* web application;
* administrative endpoints.

Use managed/core protections where practical.

Avoid overly broad rules that break legitimate video/API traffic without testing.

---

# ADMINISTRATIVE NETWORK SECURITY

Administrative infrastructure must use a stronger access boundary than ordinary public application traffic.

Where applicable provide:

* private endpoints;
* VPN/identity-aware access;
* restricted ingress;
* administrative namespaces;
* separate IAM roles;
* audit logging.

Do not expose privileged operational endpoints directly to the public internet.

---

# ZERO-TRUST SERVICE ACCESS

Where practical, service-to-service access should require:

* authenticated workload identity;
* explicit network policy;
* least privilege;
* encrypted transport;
* auditable access.

Do not rely solely on network location as proof of trust.

---

# SECRET ROTATION

Implement operational mechanisms for rotating:

* database credentials;
* Redis credentials;
* event-broker credentials;
* provider credentials;
* signing material;
* TLS certificates.

Rotation must be compatible with:

* rolling deployments;
* connection recycling;
* application reload.

Do not require simultaneous manual restarts of the entire platform where avoidable.

---

# CERTIFICATE MANAGEMENT

Automate certificate lifecycle where infrastructure supports it.

Support:

* issuance;
* renewal;
* deployment;
* expiration monitoring;
* failure alerts.

Do not commit private keys.

Do not claim certificate renewal has been operationally tested unless it was actually tested.

---

# SUPPLY-CHAIN SECURITY

Strengthen artifact security through:

* SBOM generation;
* image scanning;
* dependency scanning;
* provenance;
* signed images where supported;
* controlled registries;
* admission policies where practical.

Do not allow unsigned/untrusted images into production if the selected policy requires signature verification.

---

# ADMISSION / POLICY CONTROLS

Where Kubernetes policy tooling exists, enforce policies for:

* privileged containers;
* root execution;
* host networking;
* host filesystem access;
* dangerous capabilities;
* missing resource limits;
* unapproved images;
* unsafe namespaces.

Policies must be tested against legitimate workloads.

---

# POLICY-AS-CODE

Where practical, implement automated infrastructure policies covering:

* security;
* network exposure;
* secrets;
* resource limits;
* encryption;
* environment separation;
* storage exposure.

Do not write policies that merely create noise and are routinely bypassed.

---

# DEPLOYMENT SAFETY

Strengthen deployment pipelines with:

* immutable artifacts;
* pre-deployment validation;
* migration checks;
* health gates;
* rollout monitoring;
* automatic rollback triggers where appropriate;
* manual production approval where appropriate.

Do not deploy an artifact known to fail required checks.

---

# PROGRESSIVE DELIVERY

Where operationally justified, implement support for:

* canary releases;
* staged rollout;
* controlled traffic shifting;
* automated health checks.

Use the simplest mechanism that provides useful risk reduction.

Do not introduce progressive-delivery infrastructure solely for appearance.

---

# ROLLBACK

Define rollback for:

* application deployment;
* container version;
* configuration;
* feature flags where applicable.

Database rollback must be distinguished from application rollback.

Do not assume every database migration can safely be reversed automatically.

---

# CONFIGURATION ROLLOUT

Configuration changes must be:

* versioned;
* validated;
* environment-scoped;
* reviewable;
* reversible where practical.

Sensitive configuration must remain secret-managed.

---

# FEATURE FLAGS

Where the application architecture supports feature flags, provide operational infrastructure for:

* environment-specific values;
* gradual rollout;
* emergency disablement;
* auditability.

Do not use feature flags as a substitute for authorization.

---

# OBSERVABILITY COMPLETION

Complete production observability across:

* API;
* web;
* background workers;
* media processing;
* search;
* recommendation;
* notifications;
* moderation;
* analytics;
* PostgreSQL;
* Redis;
* event streaming;
* object storage;
* CDN;
* Kubernetes;
* ingress.

---

# GOLDEN SIGNALS

Implement monitoring for:

* latency;
* traffic;
* errors;
* saturation.

Apply these principles independently to:

* APIs;
* queues;
* event streams;
* media processing;
* databases;
* search.

---

# BUSINESS / PLATFORM SLIs

Where metrics are available, define indicators for:

* successful video publishing;
* playback authorization;
* feed availability;
* feed latency;
* search availability;
* notification delivery;
* moderation queue health;
* analytics freshness;
* media-processing success.

Do not confuse business SLIs with internal infrastructure resource metrics.

---

# SLO MONITORING

Implement:

* SLI collection;
* SLO thresholds;
* burn-rate alerts where appropriate;
* reporting;
* historical visibility.

Do not claim an SLO is achieved merely because it has been configured.

Achievement requires observed measurements over an appropriate period.

---

# ALERT QUALITY

Alerts should be:

* actionable;
* severity-classified;
* routed to appropriate operational channels;
* resistant to duplicate storms;
* linked to runbooks where practical.

Avoid alerts for every small fluctuation.

---

# INCIDENT DIAGNOSTICS

Make it possible to trace a request or operation across:

* ingress;
* API;
* database;
* Redis;
* event stream;
* background jobs;
* media workers;
* search;
* external providers.

Use:

* correlation IDs;
* trace IDs;
* event IDs;
* job IDs.

Do not include secrets in diagnostic context.

---

# LOG RETENTION

Implement bounded retention for:

* application logs;
* audit logs;
* security logs;
* infrastructure logs.

Separate:

* operational troubleshooting;
* security/audit requirements.

Do not retain high-volume logs indefinitely.

---

# METRIC CARDINALITY CONTROL

Prevent unbounded labels such as:

* user IDs;
* video IDs;
* request bodies;
* arbitrary URLs;
* raw error strings.

Use controlled dimensions.

High-cardinality data belongs in traces/logs or dedicated analytics systems where appropriate.

---

# TRACE SAMPLING

Configure tracing intelligently.

Use higher sampling for:

* errors;
* critical operations;
* rare failure paths.

Avoid collecting every high-volume successful playback/event request at full detail unless infrastructure capacity and business requirements justify it.

---

# OBSERVABILITY SECURITY

Ensure telemetry pipelines cannot expose:

* passwords;
* tokens;
* push tokens;
* private media;
* private comments;
* cryptographic secrets;
* database credentials.

Apply redaction at the appropriate collection boundary.

---

# DISASTER RECOVERY ARCHITECTURE

Define recovery tiers for:

* PostgreSQL;
* object storage;
* event streams;
* Redis;
* search;
* application containers;
* configuration;
* secrets.

Classify each system as:

* authoritative durable;
* durable and reconstructible;
* ephemeral/rebuildable.

---

# RECOVERY OBJECTIVES

Define realistic:

* RPO;
* RTO;

for critical system categories.

Do not assign identical objectives to every subsystem.

Media processing, cache state, search indexes, and analytics aggregates may have different recovery characteristics from account/video metadata.

---

# DISASTER RECOVERY RUNBOOK

Create a concrete recovery procedure covering:

1. incident declaration;
2. isolation;
3. state assessment;
4. backup selection;
5. restore;
6. service recovery;
7. validation;
8. traffic restoration;
9. derived-system rebuild;
10. post-recovery verification.

The runbook must identify dependencies and ordering.

---

# REGIONAL FAILURE

Where multi-region operation is part of the selected architecture, define recovery for:

* traffic routing;
* database availability;
* object storage;
* CDN;
* event streams;
* search;
* secrets;
* configuration.

If active-active multi-region is not currently justified, document a practical recovery model instead of implementing unnecessary complexity.

---

# BACKUP MONITORING

Alert on:

* backup failure;
* backup age;
* insufficient retention;
* restore-test failure;
* capacity issues.

A backup without monitoring is not an operationally reliable backup system.

---

# RECOVERY TESTING

Implement safe non-production recovery tests for:

* database restore;
* Redis recovery behavior;
* search reconstruction;
* event-stream rebuild where practical;
* object-storage recovery procedures.

Do not run destructive recovery drills against production without explicit authorization and safeguards.

---

# CHAOS / RESILIENCE TESTING

Create safe, repeatable failure tests for:

* API pod loss;
* worker loss;
* media-worker loss;
* Redis interruption;
* database failover;
* event-broker interruption;
* search outage;
* object-storage errors;
* notification-provider failure;
* elevated queue backlog.

Validate graceful degradation and recovery.

---

# CHAOS TEST SAFETY

Failure tests must:

* run in controlled environments;
* have clear blast-radius limits;
* avoid production unless explicitly approved;
* preserve test data;
* produce measurable outcomes;
* stop automatically when safety thresholds are reached.

---

# CAPACITY PLANNING

Create documented capacity models for:

* API replicas;
* worker replicas;
* media workers;
* PostgreSQL;
* Redis;
* event broker;
* search;
* object storage;
* CDN;
* observability stack.

Model:

* normal traffic;
* peak traffic;
* viral spikes;
* failure scenarios;
* recovery surge.

---

# CAPACITY ALERTS

Alert before systems enter unsafe saturation.

Monitor:

* CPU;
* memory;
* disk;
* network;
* database connections;
* event lag;
* queue depth;
* search storage;
* cache memory.

Do not wait for total exhaustion.

---

# LOAD TESTING INFRASTRUCTURE

Provide safe infrastructure/configuration to run representative load tests against non-production environments.

Cover:

* API;
* feed retrieval;
* authentication;
* engagement;
* event ingestion;
* search;
* media-processing queues.

Do not use production credentials or production data.

---

# PERFORMANCE BASELINES

Record reproducible baseline measurements for:

* API latency;
* feed latency;
* search latency;
* event-ingestion throughput;
* media-processing throughput;
* queue processing;
* database load.

Do not invent target numbers after the test.

Record observed values with test conditions.

---

# COST OPERATIONS

Implement cost monitoring for:

* compute;
* storage;
* database;
* Redis;
* event streaming;
* search;
* CDN;
* observability;
* media processing;
* network transfer.

Use environment/component tags or labels.

---

# COST ANOMALY CONTROLS

Where supported, configure alerts for:

* unexpected compute growth;
* storage growth;
* bandwidth spikes;
* logging-volume spikes;
* media-processing surges;
* event-stream growth.

Cost alerts must not automatically terminate critical production systems without careful safeguards.

---

# RESOURCE CLEANUP

Automate cleanup of:

* preview environments where applicable;
* stale temporary resources;
* abandoned development resources;
* obsolete container images;
* expired object artifacts;
* stale snapshots where policy permits.

Do not delete resources still required for recovery or compliance.

---

# SECURITY HARDENING

Conduct an infrastructure security review covering:

* public exposure;
* IAM;
* service accounts;
* network policies;
* container privileges;
* secrets;
* encryption;
* TLS;
* storage policies;
* CI/CD permissions;
* cluster administration;
* registry access.

Correct concrete vulnerabilities within this infrastructure scope.

---

# IAM REVIEW

Verify that:

* CI/CD has only intended permissions;
* application workloads do not have administrator access;
* media workers have only media-related permissions;
* analytics workers have only required data access;
* moderators/admins are separated from infrastructure identities where appropriate.

Do not grant broad cloud-admin rights merely to make deployment easier.

---

# AUDIT LOGGING

Ensure infrastructure-sensitive actions are auditable:

* deployments;
* IaC changes;
* secret changes;
* permission changes;
* production configuration changes;
* failover;
* recovery;
* administrative infrastructure operations.

Do not store secrets in audit records.

---

# COMPLIANCE-READY FOUNDATIONS

Where relevant, implement infrastructure foundations for:

* encryption;
* least privilege;
* audit trails;
* retention;
* environment separation;
* access reviews;
* backup;
* recovery evidence.

Do not claim formal compliance certification.

---

# INFRASTRUCTURE TESTING

Create comprehensive tests for:

* IaC;
* policy-as-code;
* container security;
* Kubernetes configuration;
* Helm;
* Terraform;
* CI/CD;
* secret scanning;
* network policies;
* autoscaling;
* health probes;
* backup configuration;
* restore workflows;
* disaster-recovery procedures;
* observability configuration.

---

# DEPLOYMENT SMOKE TESTS

Provide automated post-deployment checks for:

* application availability;
* health/readiness;
* authentication;
* database connectivity;
* Redis connectivity;
* event streaming;
* background workers;
* media pipeline;
* search;
* notification infrastructure where accessible.

Checks must verify real endpoints/services rather than merely confirming that a pod exists.

---

# ROLLBACK TESTING

Test rollback in a controlled non-production environment.

Verify:

* previous artifact availability;
* health restoration;
* connection stability;
* migration compatibility;
* configuration compatibility.

Do not claim rollback works merely because a previous image exists.

---

# MIGRATION SAFETY

Infrastructure deployment tooling must distinguish:

* additive schema migration;
* backfill;
* cleanup;
* destructive changes.

Where possible enforce ordering that protects rolling deployments.

Do not automatically destroy production data as part of a normal deployment.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* advanced workload scaling;
* queue/event-aware autoscaling;
* Kubernetes disruption controls;
* topology/failure-domain distribution;
* stateful-service resilience;
* PostgreSQL high availability configuration;
* PostgreSQL backup and restore automation;
* restore drills;
* Redis resilience;
* Kafka/Redpanda resilience;
* search resilience;
* object-storage recovery controls;
* media-worker isolation;
* media-worker scaling;
* CDN operational controls;
* origin security;
* WAF/edge controls;
* administrative network isolation;
* zero-trust service-access foundations;
* secret rotation mechanisms;
* certificate lifecycle automation;
* supply-chain hardening;
* admission/policy controls;
* policy-as-code;
* deployment safety;
* progressive delivery foundations;
* rollback;
* configuration rollout;
* feature-flag infrastructure where applicable;
* complete observability;
* SLI/SLO monitoring;
* alert quality;
* incident diagnostics;
* log retention;
* metric-cardinality controls;
* trace sampling;
* telemetry security;
* disaster-recovery architecture;
* RPO/RTO definitions;
* recovery runbooks;
* regional-failure planning where applicable;
* backup monitoring;
* recovery testing;
* resilience/chaos-testing foundations;
* capacity planning;
* load-testing infrastructure;
* performance baselines;
* cost monitoring;
* cost anomaly controls;
* resource cleanup;
* infrastructure security hardening;
* IAM review;
* auditability;
* compliance-ready foundations;
* infrastructure tests;
* deployment smoke tests;
* rollback testing;
* migration-safety controls;
* documentation.

This prompt does **not** implement:

* application business logic;
* backend APIs;
* web UI;
* mobile UI;
* recommendation algorithms;
* search application logic;
* moderation application workflows;
* notification application behavior;
* creator analytics application logic;
* live cloud account creation;
* production credential fabrication;
* production data manipulation without explicit access and authorization.

---

# APPLICATION COMPATIBILITY

The infrastructure must support and remain compatible with:

* backend API;
* web frontend;
* mobile clients;
* video/media pipeline;
* feed/recommendation;
* search;
* notifications;
* moderation;
* analytics;
* PostgreSQL;
* Redis;
* event streaming;
* background jobs;
* CDN;
* object storage;
* QA.

Preserve canonical:

* service names;
* ports;
* environment variables;
* health endpoints;
* connection strings;
* secret references;
* event-broker settings;
* storage conventions.

Do not silently rename infrastructure contracts.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* Kubernetes cluster;
* cloud provider;
* managed PostgreSQL;
* managed Redis;
* Kafka/Redpanda;
* search cluster;
* object storage;
* CDN;
* DNS;
* certificates;
* CI/CD provider.

When access is unavailable:

* validate repository-side infrastructure;
* run local/test infrastructure;
* validate syntax, policy, and configuration;
* execute non-production resilience tests where possible;
* report provider-level limitations accurately.

Do not fabricate:

* Terraform applies;
* Kubernetes deployments;
* DNS records;
* certificates;
* database failovers;
* backup restores against external infrastructure;
* CDN behavior;
* cloud IAM changes.

---

# SECURITY REQUIREMENTS

Infrastructure must enforce:

* least privilege;
* private internal services;
* secure secret handling;
* encrypted transport;
* secure container execution;
* workload identity where available;
* environment isolation;
* administrative access controls;
* artifact integrity;
* auditability;
* backup protection.

Search the repository for:

* secrets;
* credentials;
* private keys;
* accidental production endpoints.

Remove accidental secrets within the current infrastructure scope and report any unresolved exposure.

---

# RELIABILITY REQUIREMENTS

Infrastructure must support:

* graceful deployment;
* graceful shutdown;
* failure isolation;
* autoscaling;
* redundancy where justified;
* backup;
* restore;
* rollback;
* observability;
* degradation;
* disaster recovery;
* recovery testing.

Do not create unnecessary distributed complexity.

---

# OBSERVABILITY REQUIREMENTS

Infrastructure must expose enough telemetry to diagnose:

* high latency;
* API errors;
* queue backlog;
* event lag;
* media-processing failures;
* database saturation;
* Redis pressure;
* search failures;
* storage problems;
* CDN/origin errors;
* deployment failures;
* security events.

Telemetry must remain privacy-conscious.

---

# VALIDATION

After implementation:

1. Run infrastructure formatting.
2. Run IaC validation.
3. Run IaC policy/security checks.
4. Validate Kubernetes manifests.
5. Validate Helm packages where used.
6. Build production containers.
7. Run container vulnerability scanning.
8. Run SBOM/provenance generation where configured.
9. Run secret scanning.
10. Validate network policies.
11. Validate admission/policy controls.
12. Validate autoscaling configuration.
13. Validate health probes.
14. Validate CI/CD workflows.
15. Validate backup configuration.
16. Run safe non-production restore tests where infrastructure is available.
17. Run observability configuration validation.
18. Validate dashboards and alert rules.
19. Run deployment smoke tests where a deployable environment exists.
20. Run controlled rollback tests where infrastructure exists.
21. Run safe resilience tests where infrastructure exists.
22. Run load/performance tests where infrastructure exists.
23. Inspect cost-monitoring configuration.
24. Inspect final diff.
25. Search for secrets.
26. Verify no external resource is claimed as provisioned without verification.
27. Verify no application business logic outside this infrastructure scope was changed.

Report unavailable external dependencies explicitly.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* workload-scaling changes;
* autoscaling changes;
* Kubernetes disruption controls;
* failure-domain changes;
* PostgreSQL HA changes;
* backup configuration;
* restore automation;
* restore drills;
* Redis resilience changes;
* Kafka/Redpanda resilience;
* search resilience;
* object-storage recovery;
* media-worker isolation;
* CDN/origin controls;
* WAF/edge changes;
* administrative network security;
* zero-trust/service-identity changes;
* secret rotation;
* certificate management;
* supply-chain controls;
* admission/policy controls;
* deployment safety;
* progressive-delivery changes;
* rollback changes;
* configuration rollout;
* feature-flag infrastructure where applicable;
* observability changes;
* SLI/SLO configuration;
* alerting;
* incident diagnostics;
* logging/metrics/tracing controls;
* disaster recovery;
* RPO/RTO definitions;
* recovery runbooks;
* resilience testing;
* capacity planning;
* load-testing infrastructure;
* performance baselines;
* cost controls;
* security hardening;
* IAM review;
* audit controls;
* infrastructure tests;
* deployment smoke tests;
* rollback validation;
* migration-safety controls;
* documentation changes;
* validation performed;
* unavailable external resources;
* known limitations;
* unresolved issues.

Do not claim any external provisioning, failover, restore, or deployment result unless it was actually verified.

---

# DEFINITION OF DONE

This advanced infrastructure/operations milestone is complete only when:

* the repository was inspected;
* production workloads have appropriate runtime topology;
* workload scaling is defined;
* queue/event-aware autoscaling is implemented where justified;
* disruption controls exist for critical stateless workloads;
* replicas are distributed appropriately across failure domains where supported;
* PostgreSQL production reliability is defined;
* PostgreSQL backups are configured;
* point-in-time recovery is supported where available;
* restore automation exists;
* restore drills are documented and executable;
* Redis resilience is defined;
* Redis failure behavior is tested where practical;
* Kafka/Redpanda resilience is defined;
* event-retention policies are explicit;
* search resilience is configured;
* search recovery/rebuild procedures exist;
* object-storage recovery is defined;
* media workers have resource and network isolation;
* media-worker autoscaling is controlled;
* CDN operations are defined;
* media origins are protected appropriately;
* WAF/edge controls are configured where justified;
* administrative infrastructure has a restricted access boundary;
* service-to-service access is explicitly secured;
* secret rotation mechanisms exist;
* certificate lifecycle is managed;
* artifact/supply-chain security is strengthened;
* admission/policy controls are implemented where supported;
* policy-as-code exists where practical;
* deployment safety gates exist;
* progressive delivery is supported where justified;
* rollback is defined and tested where infrastructure exists;
* configuration rollout is controlled;
* feature-flag infrastructure exists where applicable;
* complete observability is implemented;
* golden-signal monitoring exists;
* platform/business SLIs are defined where measurable;
* SLO monitoring is configured;
* alerts are actionable;
* incident diagnostics support cross-component tracing;
* log retention is bounded;
* metric cardinality is controlled;
* trace sampling is configured;
* telemetry is security-filtered;
* disaster-recovery tiers are defined;
* RPO/RTO targets are documented;
* recovery runbooks exist;
* regional-failure behavior is defined where applicable;
* backup monitoring exists;
* recovery tests exist;
* resilience/chaos tests exist in controlled environments where practical;
* capacity models exist;
* capacity alerts exist;
* non-production load-test infrastructure exists;
* reproducible performance baselines exist where tested;
* cost monitoring exists;
* cost anomaly detection exists where supported;
* stale resource cleanup exists;
* infrastructure security review has been performed;
* IAM has been reviewed;
* infrastructure-sensitive actions are auditable;
* compliance-ready foundations exist where relevant;
* infrastructure test coverage is implemented;
* deployment smoke tests exist;
* rollback tests exist where infrastructure permits;
* migration-safety controls exist;
* documentation reflects actual infrastructure;
* no hardcoded secrets exist;
* no fabricated provider/cloud results exist;
* no unverified production resource is claimed as provisioned;
* no unrelated application business logic was implemented;
* compatibility with backend, web, mobile, media, events, queues, search, recommendations, notifications, moderation, analytics, and QA is preserved;
* unavailable external dependencies are reported accurately;
* validation failures are not hidden;
* the implementation report accurately reflects the work performed.

Implement **only the current prompt's scope**.

Do not expand this milestone into application implementation or unverified production provisioning.
