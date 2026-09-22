# TikTok-Style Short-Form Video Platform — Architecture Prompt — Volume 2

# ROLE

You are the senior **Architecture Contract Engineering Agent** responsible for producing the second foundational architecture package for a production-grade **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Principal Architect
* API Architect
* Database Architect
* Distributed Systems Architect
* Event-Driven Systems Architect
* Media Systems Architect
* Security Architect
* Realtime Systems Architect
* Search / Recommendation Architect
* Cloud / SRE Architect
* QA Architect
* Technical Writer

Your responsibility in this task is to create the project's **concrete cross-part contracts, implementation-grade schemas, protocol definitions, operational boundaries, and architectural invariants** required for independently generated backend, frontend, mobile, infrastructure, and QA project parts to remain compatible.

This is an architecture and contract-definition milestone.

Do not implement the complete application.

Do not generate unrelated production functionality merely to demonstrate the contracts.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on vertical short-form video consumption, creation, publishing, discovery, personalized feeds, social interaction, creator participation, notifications, moderation, analytics, and large-scale media delivery.

The completed platform is intended to support:

* user accounts and profiles;
* creator profiles;
* follow and follower relationships;
* blocks and privacy controls;
* short-form video uploads;
* video publishing;
* captions;
* hashtags;
* mentions;
* sounds / audio references;
* media assets and video variants;
* transcoding and thumbnail generation;
* CDN-backed playback;
* personalized feeds;
* following feeds;
* discovery;
* trending;
* search;
* creator discovery;
* recommendation;
* likes;
* comments;
* replies;
* shares;
* favorites;
* views and watch-time events;
* notifications;
* creator analytics;
* reporting;
* moderation;
* administration;
* abuse prevention;
* event streaming;
* asynchronous jobs;
* observability;
* production deployment;
* recovery.

This volume establishes the **binding technical contracts** needed to implement those capabilities coherently.

The existence of the full product capability inventory does not authorize implementation of the complete product during this task.

---

# TARGET USERS

The architecture contracts must support:

* viewers;
* authenticated users;
* creators;
* moderators;
* administrators;
* internal operational and analytics consumers where applicable.

All client-originated data must be considered untrusted until validated and authorized server-side.

---

# SCALE TARGET

The completed system must be architecturally capable of evolving toward:

* millions to hundreds of millions of users;
* high concurrent feed consumption;
* very high video playback volume;
* large-scale media storage;
* high engagement write rates;
* viral traffic bursts;
* high notification throughput;
* large search indexes;
* large event streams;
* geographically distributed traffic.

Contracts must remain efficient enough for high-volume request, event, and media paths.

Do not introduce unnecessarily expensive payloads or unbounded response semantics.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible alternative that should be preserved, the contracts must align with:

* Next.js / React / TypeScript for web;
* React Native / Expo / TypeScript for mobile where applicable;
* Node.js / TypeScript / NestJS or equivalent structured backend architecture;
* PostgreSQL;
* Redis;
* Kafka or Redpanda where durable event streaming is required;
* BullMQ or equivalent background job processing where appropriate;
* S3-compatible object storage;
* FFmpeg or equivalent media tooling;
* CDN-backed media delivery;
* REST APIs;
* WebSocket or equivalent realtime communication where required;
* OpenTelemetry-compatible observability.

Do not create contracts that require a technology not justified by the project's architecture.

---

# REPOSITORY INSPECTION

Before creating or modifying any artifact:

1. Inspect the repository.
2. Locate the architecture package produced or maintained by the repository.
3. Inspect existing schemas, API definitions, configuration specifications, database definitions, event contracts, and domain models.
4. Reuse established compatible terminology.
5. Identify contradictions between existing artifacts.
6. Resolve contradictions explicitly rather than silently creating competing definitions.
7. Preserve compatible implementation choices.
8. Do not fabricate missing repository state.

The repository is authoritative for what actually exists.

This prompt is authoritative for the contract artifacts and architecture details that must be established now.

Do not depend on previous AI conversations.

---

# ARCHITECTURE OBJECTIVE

Create concrete contracts that later implementation teams can consume directly.

The resulting package must make it possible for independently executed project-part prompts to determine:

* exactly how identifiers are represented;
* how timestamps are serialized;
* how APIs authenticate and authorize;
* what API requests and responses look like;
* how errors are represented;
* how pagination works;
* how domain entities are represented;
* how media assets are represented;
* how events are represented;
* how jobs are represented;
* how realtime messages are represented;
* how configuration is named;
* how compatibility is preserved;
* how privacy and moderation states propagate;
* how deployment and runtime expectations are represented.

Do not leave these as vague recommendations.

---

# IDENTIFIER AND TIME CONTRACT

Create a binding project-wide identifier and time contract.

Define:

* identifier strategy;
* identifier serialization;
* UUID/ULID or equivalent decision;
* client/server ownership of IDs;
* identifier validation;
* public exposure rules;
* timestamp representation;
* timezone semantics;
* precision;
* canonical serialization;
* ordering behavior where timestamps are used for pagination or event processing.

The contract must be consistent across:

* PostgreSQL;
* REST APIs;
* WebSockets;
* events;
* queues;
* logs;
* analytics records;
* object metadata.

Define the difference between:

* entity creation time;
* last modification time;
* event occurrence time;
* ingestion time;
* processing time.

Do not use one timestamp field to represent multiple unrelated concepts.

---

# API CONTRACT

Create a binding REST API contract covering the common conventions used across the platform.

Define:

* API base structure;
* versioning strategy;
* resource naming;
* HTTP method semantics;
* authentication behavior;
* authorization behavior;
* common headers;
* correlation/request identifiers;
* content types;
* request validation;
* response envelopes where appropriate;
* empty responses;
* status-code conventions;
* error responses;
* pagination;
* sorting;
* filtering;
* idempotency;
* conditional requests where useful;
* deprecation rules.

The contract must remain practical for both web and mobile clients.

---

# API ERROR CONTRACT

Define a single canonical machine-readable error structure.

The contract must specify fields such as:

* error code;
* human-safe message;
* request/correlation identifier;
* validation details where applicable;
* retryability where useful;
* metadata only when safe.

Define rules for at least:

* invalid input;
* unauthenticated access;
* forbidden access;
* not found;
* conflict;
* rate limit;
* dependency failure;
* transient service failure;
* unsupported operation;
* idempotency conflict.

Do not expose stack traces or internal implementation details.

Ensure errors can be logged and correlated safely.

---

# PAGINATION CONTRACT

Create a binding pagination strategy.

Use cursor pagination for high-volume collections where appropriate.

Define:

* cursor encoding;
* opaque vs structured cursors;
* cursor stability;
* sort order;
* page-size limits;
* default page sizes;
* maximum page sizes;
* forward pagination;
* reverse pagination where required;
* end-of-results semantics;
* behavior after underlying data changes;
* invalid/expired cursor behavior.

Apply explicit pagination rules to:

* feeds;
* comments;
* followers;
* following;
* likes;
* notifications;
* search;
* creator/content discovery;
* moderation queues;
* administrative lists.

Do not permit unbounded production collection endpoints.

---

# IDEMPOTENCY CONTRACT

Define where idempotency is required.

At minimum consider:

* video publication;
* like/unlike state changes where appropriate;
* follow/unfollow operations;
* comment creation where retry duplication is possible;
* share creation;
* favorite/save;
* notification creation;
* administrative actions;
* payment-like operations if ever introduced;
* external-provider requests;
* background jobs.

For each applicable operation define:

* idempotency key;
* ownership;
* retention;
* duplicate behavior;
* conflict behavior;
* replay behavior;
* failure handling.

Do not implement idempotency using an unbounded or permanently retained store.

---

# AUTHENTICATION AND SESSION CONTRACT

Create a binding authentication/session contract.

Define:

* account identity;
* authentication methods supported by the current product direction;
* access-token format;
* refresh-token/session behavior where used;
* expiration;
* rotation;
* revocation;
* device/session identity;
* logout;
* password credential handling where applicable;
* account recovery boundary;
* brute-force protection;
* rate limits;
* session invalidation.

Define what data may be stored in client secure storage.

Define what information must never be trusted from the client.

Do not put authorization decisions inside access-token claims if those claims can become stale in ways that violate security requirements.

---

# AUTHORIZATION CONTRACT

Create a binding authorization model.

Define:

* roles;
* permissions;
* resource ownership;
* administrative roles;
* moderation roles;
* creator privileges;
* account-level controls;
* content-level controls;
* block relationships;
* privacy-aware access.

Document server-side authorization rules for:

* account resources;
* profile resources;
* videos;
* media assets;
* comments;
* notifications;
* moderation records;
* administrative operations.

Explicitly address IDOR protection.

A client must never gain authority merely because it knows an object identifier.

---

# ACCOUNT AND PROFILE CONTRACT

Define the externally relevant contract for:

* User;
* Account;
* Profile;
* Creator status.

Document:

* identity fields;
* display fields;
* profile visibility;
* account state;
* creator-specific metadata;
* deletion state;
* suspension state;
* moderation state;
* privacy controls.

Distinguish:

* authentication identity;
* user-facing profile;
* moderation/account state.

Do not expose internal security or moderation metadata to ordinary clients.

---

# SOCIAL GRAPH CONTRACT

Create binding contracts for:

* follow;
* unfollow;
* follower retrieval;
* following retrieval;
* block;
* unblock;
* privacy-aware graph access.

Define:

* request/response semantics;
* authorization;
* idempotency;
* conflict behavior;
* visibility rules;
* event emission;
* cache invalidation;
* eventual-consistency expectations.

Blocking must affect all relevant content-discovery and interaction paths.

---

# VIDEO DOMAIN CONTRACT

Create a binding contract for the core Video entity.

Define:

* video identifier;
* owner/creator;
* lifecycle state;
* publication state;
* visibility;
* caption;
* hashtag references;
* mentions;
* sound/audio reference;
* thumbnail reference;
* media asset references;
* moderation state;
* timestamps;
* deletion state;
* engagement summary fields that are safe to expose.

Clearly distinguish:

* draft/uploading;
* processing;
* ready;
* published;
* restricted;
* removed;
* deleted;
* failed.

The lifecycle must prevent clients from assuming media is playable before required processing and safety checks have completed.

---

# MEDIA ASSET CONTRACT

Create a binding media model for:

* source upload;
* MediaAsset;
* VideoVariant;
* thumbnail;
* preview asset;
* playback representation.

Define:

* asset ID;
* owner;
* parent video;
* asset type;
* processing state;
* media metadata;
* dimensions;
* duration;
* codec/container metadata where required;
* storage location abstraction;
* access policy;
* checksum where appropriate;
* lifecycle timestamps;
* deletion behavior.

Do not expose internal object-storage credentials or sensitive storage implementation details to clients.

---

# MEDIA UPLOAD CONTRACT

Define the secure upload lifecycle.

Document:

1. client requests upload authorization;
2. backend validates ownership and policy;
3. backend creates upload intent;
4. client transfers media to authorized storage;
5. backend receives/verifies completion;
6. processing begins asynchronously;
7. validation and safety processing occur;
8. variants are generated;
9. publication becomes eligible;
10. playback assets become available.

Define:

* allowed media types;
* size limits;
* duration limits;
* metadata validation;
* upload expiry;
* cancellation;
* retry;
* duplicate uploads;
* failed processing;
* cleanup.

Treat all uploaded media as untrusted.

---

# VIDEO PLAYBACK CONTRACT

Define the client-facing playback model.

Document:

* playable-state rules;
* media URL acquisition;
* signed access;
* URL expiration;
* CDN behavior;
* variant selection;
* manifest behavior where applicable;
* unavailable-media handling;
* removed/restricted content behavior;
* playback telemetry boundaries.

Playback authorization must be evaluated consistently with:

* account privacy;
* video visibility;
* block relationships;
* moderation state;
* deletion state.

---

# ENGAGEMENT CONTRACT

Create binding contracts for:

* like;
* unlike;
* comment;
* reply;
* share;
* favorite/save.

Define:

* endpoint semantics;
* authorization;
* duplicate behavior;
* idempotency;
* response semantics;
* event emission;
* counter semantics;
* concurrency expectations.

Distinguish authoritative interaction records from aggregated counters.

Do not make counters the authoritative representation of whether a user has performed an action.

---

# VIEW AND WATCH-TIME EVENT CONTRACT

Define a high-volume behavioral event contract for:

* impression;
* playback start;
* watch progress;
* completion;
* skip;
* replay;
* dwell/watch-time;
* negative feedback where applicable.

For each event define:

* event identity;
* event type;
* schema version;
* video/content ID;
* viewer ID when available;
* session/device context where safe;
* position/duration fields where applicable;
* client timestamp;
* server ingestion timestamp;
* correlation ID;
* privacy constraints.

Define deduplication and sampling considerations.

Do not allow clients to directly rewrite authoritative analytics.

---

# FEED CONTRACT

Create a binding client-facing feed contract.

Define:

* feed type;
* item representation;
* continuation cursor;
* ranking metadata exposed to clients;
* content visibility;
* creator/profile summary;
* media playback metadata;
* engagement summary;
* reason codes only where useful and safe;
* empty-state behavior;
* fallback behavior.

Do not expose proprietary internal ranking features unnecessarily.

Define how clients handle:

* deleted videos;
* moderated videos;
* unavailable media;
* blocked creators;
* duplicate content;
* stale cached feed items.

---

# RECOMMENDATION CONTRACT

Define internal contracts between:

* behavioral event ingestion;
* feature/aggregation processing;
* candidate generation;
* ranking;
* safety filtering;
* feed assembly.

Define conceptual objects such as:

* RecommendationCandidate;
* ranking feature set;
* policy decision;
* recommendation result.

Do not require the first implementation to use machine learning.

Define a contract that permits progression from deterministic/rule-based ranking to more advanced ranking models.

Safety and privacy filtering must be able to override ranking.

---

# HASHTAG AND MENTION CONTRACT

Define contracts for:

* hashtag extraction;
* hashtag references;
* mention references;
* normalization;
* canonical representation;
* search/indexing;
* moderation.

Define behavior for:

* invalid references;
* renamed or unavailable accounts;
* deleted content;
* case normalization;
* duplicate hashtags.

---

# SOUND / AUDIO CONTRACT

Define the logical model for platform audio references.

Document:

* sound identity;
* creator/ownership metadata;
* source/reference model;
* video association;
* playback metadata;
* visibility;
* moderation status;
* deletion implications.

Do not assume unrestricted redistribution of copyrighted audio.

The architecture must leave room for rights-management and moderation policies.

---

# COMMENT CONTRACT

Create binding contracts for:

* comment creation;
* comment retrieval;
* reply retrieval;
* deletion;
* reporting;
* moderation;
* visibility filtering.

Define:

* pagination;
* nesting limits;
* authorization;
* deleted-state handling;
* blocked-user behavior;
* moderation-state behavior;
* rate limiting.

Do not create unbounded recursive comment structures.

---

# NOTIFICATION CONTRACT

Define a canonical notification model.

Support applicable channels:

* in-app;
* push.

Define:

* notification ID;
* type;
* actor;
* target entity;
* read state;
* creation time;
* routing;
* preferences;
* privacy constraints;
* deduplication key;
* expiry where appropriate.

Define notification creation from domain events.

Prevent duplicate notifications caused by repeated event delivery.

---

# EVENT ENVELOPE CONTRACT

Create a project-wide event envelope.

Every durable event should define, where applicable:

* event ID;
* event type;
* schema version;
* aggregate/entity ID;
* producer;
* occurred-at;
* published-at where useful;
* correlation ID;
* trace ID/context;
* partitioning key;
* payload.

Define naming conventions.

Define versioning conventions.

Define compatibility requirements.

Define which payload fields are prohibited because they contain secrets or excessive private content.

---

# EVENT DELIVERY CONTRACT

Define delivery assumptions for Kafka/Redpanda or equivalent event infrastructure.

Assume at-least-once delivery unless a stronger guarantee is explicitly demonstrated.

Define:

* consumer groups;
* partitioning strategy;
* ordering expectations;
* retries;
* duplicate handling;
* dead-letter behavior;
* replay;
* retention;
* schema compatibility.

Consumers must be idempotent where business behavior can otherwise duplicate.

---

# TRANSACTIONAL OUTBOX CONTRACT

Where a relational database mutation must reliably produce an event, define the architectural use of a transactional outbox.

Document:

* transaction boundary;
* outbox record;
* event serialization;
* publishing worker;
* publish state;
* retry;
* duplicate event handling;
* cleanup/retention.

Do not require distributed two-phase commits where an outbox is sufficient.

---

# QUEUE / JOB CONTRACT

Create a canonical background-job envelope.

Define:

* job ID;
* job type;
* schema version;
* payload;
* priority;
* attempt;
* maximum attempts;
* timeout;
* backoff;
* idempotency key;
* correlation ID;
* creation time;
* scheduled time where applicable.

Define job families for applicable work such as:

* media processing;
* thumbnail generation;
* moderation processing;
* search indexing;
* notifications;
* cleanup;
* analytics processing;
* feed materialization.

Define retry and dead-letter requirements.

---

# REDIS CONTRACT

Create project-wide Redis conventions.

Define:

* key naming;
* namespace strategy;
* serialization;
* TTL requirements;
* ownership;
* invalidation;
* stale-data handling;
* failure behavior;
* memory constraints;
* lock requirements where applicable.

Explicitly document Redis uses that are:

* cache;
* ephemeral state;
* coordination;
* rate limiting;
* session-related;
* derived acceleration.

Identify authoritative data that must remain in PostgreSQL or another durable system.

---

# DATABASE CONTRACT FOUNDATION

Create a concrete relational contract for the foundational domain model.

At minimum specify the core tables/entities and relationships required for:

* accounts/users;
* profiles;
* videos;
* media assets;
* video variants;
* hashtags;
* mentions;
* sounds;
* follows;
* blocks;
* likes;
* comments;
* favorites;
* shares;
* moderation/report records where appropriate;
* notifications.

For each important table specify:

* primary key;
* important foreign keys;
* uniqueness constraints;
* critical indexes;
* lifecycle/status fields;
* high-volume access patterns.

Do not attempt to specify every future analytics warehouse table.

Avoid duplicated ownership.

---

# DATABASE CONCURRENCY CONTRACT

Define expected concurrency behavior for:

* like/unlike;
* follow/unfollow;
* favorites;
* comment operations;
* publication-state changes;
* moderation changes;
* notification deduplication;
* counter updates.

Define where the system requires:

* unique constraints;
* transactions;
* optimistic locking;
* pessimistic locking;
* atomic updates.

Do not depend on application-level checks alone when the database can enforce integrity directly.

---

# COUNTER CONTRACT

Define how derived counters are represented.

For important counters such as:

* likes;
* comments;
* shares;
* favorites;
* views;

document:

* authoritative source;
* update path;
* eventual consistency tolerance;
* reconciliation strategy;
* cache behavior;
* overflow/scaling considerations.

A displayed counter must not silently become the authoritative record of an individual user's action.

---

# SEARCH INDEX CONTRACT

Define the binding relationship among authoritative content and search indexes.

For each searchable resource, define:

* source of truth;
* index document identity;
* indexed fields;
* visibility fields;
* moderation state;
* deletion state;
* update events;
* deletion propagation;
* eventual consistency expectations.

Search must not expose:

* deleted content;
* private content to unauthorized users;
* blocked entities;
* moderation-restricted entities

merely because an index is stale.

---

# MODERATION STATE CONTRACT

Define a canonical moderation-state model applicable to:

* accounts;
* videos;
* comments;
* reports.

Define states such as appropriate:

* active;
* under_review;
* restricted;
* removed;
* suspended;
* deleted.

For each state define:

* public visibility;
* playback behavior;
* search visibility;
* feed visibility;
* recommendation eligibility;
* interaction availability;
* notification behavior.

Do not permit different subsystems to interpret the same moderation state differently.

---

# REPORT CONTRACT

Define contracts for:

* report creation;
* report categories;
* target references;
* reporter identity;
* status;
* assignment;
* review;
* resolution;
* auditability.

Reports must be protected against:

* unauthorized access;
* enumeration;
* spam;
* duplicate abuse;
* disclosure of reporter-sensitive data where applicable.

---

# ADMINISTRATIVE ACTION CONTRACT

Define a canonical structure for privileged administrative actions.

Document:

* administrator identity;
* role;
* target entity;
* action;
* reason;
* timestamp;
* correlation ID;
* outcome;
* audit record.

Every security-sensitive administrative action must be auditable.

---

# CONFIGURATION CONTRACT

Create canonical configuration naming conventions covering:

* application runtime;
* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* object storage;
* CDN;
* media processing;
* authentication;
* notification providers;
* search;
* observability;
* feature flags;
* rate limits.

For every sensitive configuration category, identify it as secret material.

Never include actual secret values.

Define required-vs-optional configuration behavior.

---

# SECURITY CONTRACTS

Create concrete security requirements for:

* API authentication;
* server-side authorization;
* object access;
* media uploads;
* media-processing workers;
* administrative APIs;
* WebSockets;
* events;
* queues;
* search;
* notification systems.

Explicitly document protection against:

* IDOR;
* privilege escalation;
* malicious uploads;
* injection;
* SSRF;
* command injection;
* XSS/CSRF where applicable;
* replay;
* credential abuse;
* rate-limit bypass;
* secret leakage.

---

# MEDIA SECURITY CONTRACT

Define security controls for media processing.

At minimum address:

* file-size validation;
* content-type verification;
* extension normalization;
* malicious-file handling;
* decompression/resource exhaustion concerns;
* FFmpeg sandboxing/isolation requirements;
* processing timeouts;
* worker resource limits;
* temporary-file cleanup;
* access authorization;
* signed URLs;
* object lifecycle;
* deletion;
* quarantine/review state where applicable.

Do not allow arbitrary user-controlled media metadata to become shell arguments or command execution inputs.

---

# REALTIME CONTRACT

Create a concrete WebSocket/realtime protocol for applicable realtime interactions.

Define:

* endpoint;
* connection authentication;
* handshake;
* protocol/version;
* message envelope;
* message ID;
* event type;
* event version;
* subscription semantics;
* authorization;
* server-to-client events;
* client acknowledgements where required;
* heartbeat;
* reconnect behavior;
* duplicate handling;
* ordering;
* backpressure;
* disconnect behavior.

The realtime protocol must never replace durable state synchronization.

Clients must be able to resynchronize through authoritative APIs after reconnect.

---

# CLIENT SYNCHRONIZATION CONTRACT

Define client recovery/synchronization rules for:

* stale feeds;
* engagement state;
* notifications;
* profile changes;
* moderation changes;
* deleted content;
* reconnecting realtime sessions.

Define which state is:

* authoritative server state;
* cached client state;
* optimistic client state;
* ephemeral client state.

Define conflict-resolution expectations.

---

# PRIVACY AND DELETION CONTRACT

Create a project-wide deletion and privacy propagation contract.

When an account or video is deleted, define effects across:

* PostgreSQL;
* Redis;
* object storage;
* CDN;
* search indexes;
* event-derived stores;
* notification state;
* recommendation candidates;
* analytics datasets where applicable;
* background jobs;
* caches.

Distinguish:

* immediate access revocation;
* eventual derived-data cleanup;
* retention required for audit/security purposes.

Do not promise that every historical event disappears instantly if retention or audit requirements legally/operationally require otherwise.

---

# DATA RETENTION CONTRACT

Define retention categories for:

* application records;
* audit records;
* raw behavioral events;
* analytics data;
* logs;
* traces;
* media;
* moderation records;
* dead-letter messages;
* temporary processing artifacts.

Every high-volume store must have a bounded lifecycle.

Do not allow indefinite growth by default.

---

# OBSERVABILITY CONTRACT

Define canonical fields for:

* structured logs;
* traces;
* metrics;
* correlation IDs;
* request IDs;
* job IDs;
* event IDs.

Define sensitive fields that must never be logged.

Establish naming conventions for:

* API metrics;
* database metrics;
* queue metrics;
* event lag;
* media-processing latency;
* CDN/media failures;
* feed latency;
* recommendation latency;
* notification delivery;
* moderation processing.

---

# SLO / SLI FOUNDATION

Define initial service-level indicators and target classes for the completed platform.

At minimum consider:

* API availability;
* API latency;
* feed-read latency;
* video playback startup latency;
* media-processing success rate;
* event-processing lag;
* queue latency;
* search availability;
* notification delivery;
* recommendation availability.

Do not claim measured production values.

These are architectural target definitions to guide later implementation and operations.

---

# FAILURE AND DEGRADATION CONTRACT

Create a concrete degradation matrix.

At minimum cover:

* PostgreSQL failure;
* Redis failure;
* Kafka/Redpanda failure;
* BullMQ/job-system failure;
* object-storage failure;
* CDN failure;
* media-worker failure;
* search failure;
* recommendation failure;
* notification-provider failure;
* moderation-provider failure.

For each failure specify:

* affected paths;
* allowed degradation;
* retry behavior;
* fallback behavior;
* data-loss risk;
* consistency effect;
* recovery expectations;
* observability.

Critical paths must degrade safely rather than failing indiscriminately.

---

# DEPLOYMENT COMPATIBILITY CONTRACT

Define compatibility expectations for rolling deployment.

Address:

* backward-compatible APIs;
* database migration ordering;
* additive schema changes;
* event-version compatibility;
* consumer upgrades;
* queue payload evolution;
* client/server compatibility;
* rollback behavior.

Do not require synchronized deployment of all consumers when contract compatibility can avoid it.

---

# DISASTER RECOVERY CONTRACT

Define architectural expectations for:

* PostgreSQL backups;
* object-storage durability;
* event retention/replay;
* search reconstruction;
* cache loss;
* queue recovery;
* regional outage.

Establish target categories for:

* RPO;
* RTO;
* restore verification;
* rebuildability of derived systems.

Distinguish durable source-of-truth systems from reconstructible derived systems.

---

# EXTERNAL INTEGRATION CONTRACT

Define adapter boundaries for external:

* object storage;
* CDN;
* push notifications;
* moderation;
* search;
* analytics;
* identity providers where applicable;
* other services introduced later.

For each integration boundary define:

* input contract;
* output contract;
* timeout;
* retry;
* idempotency;
* error mapping;
* credential boundary;
* observability.

Do not fabricate provider-specific capabilities or credentials.

---

# CONTRACT ARTIFACTS

Create a portable artifact set containing, at minimum, the concrete contract work established by this volume.

Organize artifacts into clear repository-relative paths, for example:

* identifiers and time;
* API conventions;
* error contract;
* pagination;
* idempotency;
* authentication/session;
* authorization;
* account/profile;
* social graph;
* video;
* media;
* playback;
* engagement;
* view/watch events;
* feed;
* recommendation;
* comments;
* notifications;
* event envelope;
* queue/job envelope;
* Redis conventions;
* database contracts;
* search;
* moderation;
* reporting;
* administration;
* configuration;
* realtime;
* synchronization;
* privacy/deletion;
* retention;
* observability;
* SLO/SLI;
* failure/degradation;
* deployment compatibility;
* disaster recovery;
* external integrations.

Use stable filenames and consistent terminology.

Where machine-readable schemas materially improve implementation correctness, create them in an appropriate durable schema format.

---

# CONTRACT REGISTER UPDATE

Create or update a contract register that identifies for every important contract:

* canonical artifact;
* domain owner;
* consumers;
* protocol;
* version;
* compatibility rule;
* source-of-truth status;
* lifecycle;
* security sensitivity;
* expected implementation consumers.

The register must make cross-part dependencies discoverable without requiring access to a previous AI conversation.

---

# ARCHITECTURAL CONSISTENCY REVIEW

Perform a complete consistency review across the architecture package available in the repository.

Check for:

* entity-name conflicts;
* ID mismatches;
* timestamp mismatches;
* API naming conflicts;
* inconsistent error formats;
* inconsistent pagination;
* conflicting authorization rules;
* inconsistent moderation states;
* inconsistent media lifecycle states;
* conflicting event names;
* incompatible queue payload concepts;
* contradictory ownership;
* duplicated authoritative state;
* incompatible deletion behavior;
* inconsistent configuration names.

Resolve contradictions explicitly.

Do not silently create parallel competing standards.

---

# IMPLEMENTATION BOUNDARY

This prompt is responsible for the project's **binding architecture contracts and implementation-grade protocol definitions**.

The current task includes:

* project-wide identifiers and time conventions;
* API conventions;
* error contract;
* pagination;
* idempotency;
* authentication/session;
* authorization;
* account/profile contracts;
* social graph contracts;
* video contracts;
* media and playback contracts;
* engagement contracts;
* behavioral event contracts;
* feed contracts;
* recommendation contracts;
* comments;
* notifications;
* event envelope;
* event-delivery semantics;
* transactional outbox;
* queue/job contracts;
* Redis conventions;
* database contract foundation;
* concurrency rules;
* counter rules;
* search contracts;
* moderation states;
* reporting;
* administrative actions;
* configuration conventions;
* security contracts;
* media security;
* realtime protocol;
* client synchronization;
* privacy/deletion;
* retention;
* observability;
* SLO/SLI foundation;
* failure/degradation behavior;
* deployment compatibility;
* disaster recovery expectations;
* external integration boundaries;
* contract register.

The current task does **not** authorize:

* complete application implementation;
* complete backend services;
* complete web UI;
* complete mobile UI;
* production cloud provisioning;
* full machine-learning model training;
* production-scale search deployment;
* complete media worker implementation;
* complete QA automation;
* live third-party account provisioning.

Do not convert contract definitions into an excuse to implement unrelated product functionality.

---

# SECURITY AND PRIVACY REQUIREMENTS

All contracts must enforce:

* server-authoritative authorization;
* least privilege;
* safe data exposure;
* secure secret boundaries;
* explicit object access;
* safe media handling;
* privacy-aware propagation;
* auditable privileged operations.

Never place:

* passwords;
* access tokens;
* refresh tokens;
* private keys;
* API keys;
* provider secrets

inside repository artifacts.

---

# TESTING AND VALIDATION

This is an architecture-contract milestone.

Validate the generated artifacts themselves.

Perform, as applicable:

* schema validation;
* OpenAPI validation;
* machine-readable contract validation;
* JSON Schema validation;
* Mermaid/diagram validation;
* internal-reference validation;
* duplicate contract detection;
* naming consistency checks;
* status/state consistency checks;
* event-version consistency checks;
* queue-schema consistency checks;
* configuration consistency checks;
* repository type/build validation for executable schema/configuration artifacts.

Where contracts are represented as code-generated types or schemas, validate them using the repository's available tooling.

Do not claim runtime behavior is tested when the corresponding implementation does not yet exist.

---

# DOCUMENTATION REQUIREMENTS

The artifact package must explain:

* the contract itself;
* who owns it;
* who consumes it;
* what the authoritative source is;
* versioning rules;
* compatibility requirements;
* security sensitivity;
* migration expectations.

Documentation must remain portable and usable by separately operating engineering teams.

Do not require another AI conversation to interpret an artifact.

---

# IMPLEMENTATION REPORT

After completing the architecture-contract milestone, provide a concise completion report identifying:

* files created;
* files modified;
* files deleted, if any;
* contract families established;
* machine-readable schemas created;
* API decisions;
* authentication/session decisions;
* authorization decisions;
* database contract decisions;
* media contract decisions;
* feed/recommendation contract decisions;
* event and queue contract decisions;
* realtime decisions;
* search/moderation decisions;
* privacy/deletion decisions;
* observability/SLO decisions;
* deployment/recovery decisions;
* consistency issues found;
* consistency issues resolved;
* validation performed;
* remaining assumptions;
* unresolved issues.

Do not claim an artifact exists unless it actually exists in the repository.

Do not claim operational validation unless it was actually performed.

---

# DEFINITION OF DONE

This architecture-contract milestone is complete only when:

* the repository has been inspected;
* project-wide identifier and time rules are explicit;
* API conventions are explicit;
* API errors are explicit;
* pagination is explicit;
* idempotency is explicit;
* authentication/session behavior is explicit;
* authorization is explicit;
* account/profile contracts are explicit;
* social graph contracts are explicit;
* video lifecycle is explicit;
* media asset contracts are explicit;
* upload and playback contracts are explicit;
* engagement contracts are explicit;
* behavioral event contracts are explicit;
* feed contracts are explicit;
* recommendation boundaries are explicit;
* comment contracts are explicit;
* notification contracts are explicit;
* event envelopes are explicit;
* event-delivery semantics are explicit;
* outbox behavior is explicit;
* background-job contracts are explicit;
* Redis conventions are explicit;
* core relational contracts are explicit;
* concurrency rules are explicit;
* counter semantics are explicit;
* search contracts are explicit;
* moderation-state semantics are explicit;
* reporting contracts are explicit;
* administrative-action contracts are explicit;
* configuration conventions are explicit;
* media-security requirements are explicit;
* realtime protocol is explicit;
* client synchronization rules are explicit;
* deletion and privacy propagation are explicit;
* retention expectations are explicit;
* observability conventions are explicit;
* SLO/SLI foundations are explicit;
* failure/degradation behavior is explicit;
* deployment compatibility is explicit;
* disaster recovery expectations are explicit;
* external integration boundaries are explicit;
* the contract register is complete;
* machine-readable artifacts validate where applicable;
* terminology is consistent across the architecture package;
* no hidden dependency on another AI conversation exists;
* no fake implementation is represented as completed;
* no external resource is claimed to exist without verification;
* the artifacts are portable enough for independent backend, frontend, mobile, infrastructure, and QA implementation;
* the completion report accurately represents the work performed.

Implement **only the current prompt's scope**.

Do not expand this milestone into full application implementation.
