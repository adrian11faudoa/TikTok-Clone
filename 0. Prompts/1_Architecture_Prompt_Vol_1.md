# TikTok-Style Short-Form Video Platform — Architecture Prompt — Volume 1

# ROLE

You are the senior **Architecture Engineering Agent** responsible for producing the foundational architecture package for a production-grade **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Principal Architect
* Distributed Systems Architect
* Backend Architect
* Database Architect
* Security Architect
* Media Architecture Engineer
* Realtime Systems Architect
* Data / Event Architecture Engineer
* Cloud / Infrastructure Architect
* SRE
* QA Architect
* Technical Writer

Your responsibility in this task is to create the project's **foundational, implementation-useful architecture artifacts**.

This is an architecture and contract-definition milestone.

Do not implement the complete application.

Do not generate unrelated production code merely to demonstrate the architecture.

Produce concrete artifacts that can later guide independently implemented backend, frontend, mobile, infrastructure, and QA work.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on vertical short-form video consumption, creation, publishing, discovery, personalized feeds, social interaction, creator participation, notifications, moderation, analytics, and large-scale media delivery.

The completed platform is intended to support:

* user accounts and profiles;
* creator profiles;
* follows and social graph operations;
* short-form video uploads and publishing;
* video metadata;
* captions;
* hashtags;
* mentions;
* sounds / audio references;
* thumbnails and video derivatives;
* media transcoding;
* CDN-backed video playback;
* personalized feeds;
* following feeds where applicable;
* discovery and trending;
* search;
* creator discovery;
* recommendations;
* likes;
* comments and replies;
* shares;
* saves / favorites;
* views and watch-time telemetry;
* notifications;
* creator analytics;
* reporting;
* moderation;
* blocking;
* administrative controls;
* privacy controls;
* abuse prevention;
* event streaming;
* background processing;
* production observability;
* deployment and recovery.

Only architecture relevant to the current volume is to be defined now.

The existence of the full product capability list does not authorize implementation of the entire platform during this task.

---

# TARGET USERS

The architecture must account for:

* anonymous viewers where product policy permits;
* authenticated viewers;
* creators;
* moderators;
* administrators;
* internal operational and analytics users where required.

User-generated content and interaction data must be treated as untrusted or potentially adversarial input.

---

# GLOBAL SCALE TARGET

The completed architecture must be capable of evolving toward:

* millions to hundreds of millions of registered users;
* large concurrent video playback populations;
* high feed-request rates;
* substantial concurrent uploads;
* very high media-storage growth;
* large engagement-event volumes;
* viral traffic bursts;
* high notification throughput;
* large search indexes;
* geographically distributed traffic;
* continuously growing creator and content catalogs.

These targets are architectural requirements, not a mandate to deploy production-scale infrastructure during this architecture milestone.

Architecture choices must avoid creating fundamental blockers to this target scale.

---

# TECHNOLOGY DIRECTION

Unless the repository already establishes a compatible and justified alternative, design the architecture around:

## Web

* Next.js
* React
* TypeScript

## Mobile

* React Native
* Expo where compatible with the required functionality
* TypeScript

## Backend

* TypeScript
* Node.js
* NestJS or an equivalent strongly structured TypeScript backend architecture

## Database

* PostgreSQL as the authoritative relational datastore

## Cache / Ephemeral State

* Redis

## Event Streaming

* Kafka or Redpanda where durable event streaming is justified

## Background Jobs

* BullMQ or an equivalent job-processing mechanism where Redis-backed asynchronous work is appropriate

## Object Storage

* S3-compatible object storage

## Media Processing

* FFmpeg or equivalent production tooling

## Media Delivery

* CDN-backed delivery with appropriately authorized asset access

## API

* REST by default
* WebSocket or equivalent realtime transport where required

## Observability

* OpenTelemetry-compatible tracing and telemetry
* structured logging
* metrics
* health checks
* readiness/liveness
* alerting

## Infrastructure

* containerized workloads
* infrastructure-as-code
* cloud deployment architecture appropriate to the scale and operational requirements

Do not introduce technologies simply because they are common in large systems.

Every chosen component must have a documented architectural purpose.

If the repository already contains a compatible technology choice, inspect and preserve it unless a justified architectural issue requires otherwise.

---

# REPOSITORY INSPECTION

Before creating architecture artifacts:

1. Inspect the repository thoroughly enough to determine whether an implementation already exists.
2. Identify applications, packages, services, modules, database tooling, infrastructure, configuration, tests, and documentation.
3. Identify existing technology choices.
4. Identify existing domain models and naming conventions.
5. Identify existing APIs, schemas, events, queues, storage abstractions, and authentication mechanisms.
6. Identify inconsistencies or architectural gaps relevant to this architecture milestone.
7. Preserve sound existing decisions where compatible with the project direction.
8. Do not fabricate repository contents.

The repository is the authoritative source for what actually exists.

This prompt is authoritative for the architecture work that must be produced now.

Do not assume another AI conversation, previous response, or external artifact exists unless the artifact is actually present in the repository or explicitly supplied in the current execution environment.

---

# ARCHITECTURE OBJECTIVE

Produce a concrete foundational architecture package that gives later implementation work a stable technical direction.

The architecture must answer, with implementation-useful specificity:

* what the major domains are;
* where domain ownership resides;
* how the system is decomposed;
* how clients communicate with the platform;
* where authoritative state lives;
* which responsibilities are synchronous;
* which responsibilities are asynchronous;
* how media flows through the system;
* how feeds and discovery are structured;
* how social and engagement data are represented conceptually;
* how major system boundaries communicate;
* what the core infrastructure dependencies are;
* what security boundaries exist;
* what failure boundaries exist;
* what contracts must be preserved;
* how the system can scale without unnecessary complexity.

Do not produce only conceptual prose.

The architecture package must contain actual diagrams, tables, schemas, decision records, and contract documentation where appropriate.

---

# ARCHITECTURE PRINCIPLES

The architecture must follow these principles:

* clear ownership of authoritative data;
* explicit bounded domains;
* modularity;
* contract-first integration;
* secure-by-default behavior;
* server-authoritative authorization;
* asynchronous processing for expensive workloads;
* idempotency for retryable operations;
* bounded resource consumption;
* observable critical paths;
* horizontal scalability where needed;
* deliberate consistency models;
* compatibility-aware evolution;
* operational simplicity where possible;
* explicit failure behavior;
* avoid unnecessary microservice fragmentation;
* avoid coupling clients directly to internal infrastructure;
* protect untrusted media and user-generated content;
* separate operational telemetry from product analytics;
* preserve a clean migration path toward larger scale.

---

# ARCHITECTURAL BOUNDARY MODEL

Define the proposed high-level domain/module boundaries for at least:

* Identity and Accounts
* Profiles
* Social Graph
* Video Content
* Media Assets and Processing
* Feed / Candidate Delivery
* Recommendation
* Discovery / Search
* Engagement
* Comments
* Notifications
* Moderation and Safety
* Reports
* Administration
* Analytics / Behavioral Events

For each boundary, document:

* responsibility;
* authoritative data;
* major entities;
* inbound interactions;
* outbound interactions;
* synchronous dependencies;
* asynchronous dependencies;
* security boundary;
* scalability characteristics;
* expected ownership.

Where multiple domains may reside in the same deployable application initially, distinguish **logical ownership** from **deployment boundaries**.

Do not force every domain into a separate service merely because a domain exists.

---

# SYSTEM CONTEXT

Create a system-context artifact that clearly shows:

* web clients;
* mobile clients;
* backend entry point;
* identity/authentication boundary;
* core application domains;
* PostgreSQL;
* Redis;
* event streaming;
* background-job infrastructure;
* object storage;
* media-processing workers;
* CDN;
* search subsystem where applicable;
* notification providers where applicable;
* moderation providers or moderation-processing boundary where applicable;
* analytics consumers;
* administrative interfaces;
* observability infrastructure;
* external dependencies.

Distinguish:

* trusted internal services;
* semi-trusted client applications;
* untrusted user input;
* external providers.

Document major trust boundaries.

---

# COMPONENT ARCHITECTURE

Produce a component-level architecture describing the major runtime components.

At minimum define:

* web application;
* mobile application;
* API/application boundary;
* authentication/session boundary;
* feed/read path;
* content/write path;
* media upload path;
* media-processing workers;
* engagement path;
* event-ingestion path;
* notification path;
* moderation path;
* search/indexing path;
* analytics path;
* administrative path.

For each component define:

* responsibility;
* inputs;
* outputs;
* data dependencies;
* failure modes;
* scaling characteristics;
* observability requirements.

Make clear which components are:

* synchronous request/response;
* asynchronous workers;
* event consumers;
* data stores;
* external providers.

---

# DOMAIN MODEL

Create the foundational conceptual domain model.

At minimum define the relationships among:

* User / Account
* Profile
* Creator
* Video
* MediaAsset
* VideoVariant
* Hashtag
* Mention
* Sound
* Follow
* Like
* Comment
* CommentReply
* Share
* Favorite
* ViewEvent
* Feed
* RecommendationCandidate
* Notification
* Report
* ModerationCase
* AuditEvent

For each important entity, document:

* purpose;
* ownership;
* lifecycle;
* identity requirements;
* key relationships;
* privacy considerations;
* deletion implications;
* high-volume characteristics.

Do not prematurely define every database column.

This volume establishes the authoritative conceptual model.

---

# DATA OWNERSHIP

Create a data-ownership matrix.

Explicitly identify:

* authoritative owner of each core entity;
* allowed readers;
* allowed writers;
* derived-data consumers;
* caches;
* search indexes;
* analytics consumers.

Distinguish authoritative state from:

* cache state;
* materialized state;
* search indexes;
* analytics copies;
* event streams;
* derived counters.

No downstream cache, index, or event topic may silently become the authoritative source of business truth.

---

# DATA FLOW ARCHITECTURE

Document the major end-to-end flows.

At minimum define architectural flows for:

* account creation/authentication;
* video upload authorization;
* video upload;
* media processing;
* video publication;
* video playback;
* feed retrieval;
* follow/unfollow;
* like/unlike;
* comment creation;
* content sharing;
* favorite/save;
* view/watch-time event capture;
* notification generation;
* content reporting;
* moderation-state changes;
* search indexing.

For every major flow identify:

* initiating client;
* API boundary;
* authoritative write;
* asynchronous work;
* events;
* derived data;
* cache behavior;
* eventual consistency;
* failure recovery.

Use sequence diagrams where they provide meaningful clarity.

---

# MEDIA ARCHITECTURE FOUNDATION

Define the foundational media architecture.

Document:

* upload authorization;
* direct vs proxied upload model;
* object-storage boundary;
* upload states;
* metadata ownership;
* validation;
* malware/content scanning boundary;
* transcoding;
* thumbnail generation;
* variant generation;
* processing queue;
* processing retries;
* failed-processing behavior;
* publication gating;
* CDN delivery;
* signed access;
* deletion lifecycle.

Explicitly document that uploaded files are untrusted.

Define the conceptual relationship among:

* Video entity;
* source upload;
* MediaAsset;
* processed variants;
* playback representation.

Define which system components own each step.

---

# FEED ARCHITECTURE FOUNDATION

Define the architectural model for short-form video feed delivery.

Document the separation between:

* candidate generation;
* ranking;
* policy/safety filtering;
* personalization;
* freshness;
* deduplication;
* feed assembly;
* delivery;
* caching.

Define initial candidate sources such as:

* followed creators;
* trending content;
* recent published content;
* topic/hashtag signals;
* creator/content affinity;
* recommendation candidates.

Do not claim to reproduce TikTok's proprietary ranking algorithm.

Define an original architecture that provides a path from deterministic initial ranking toward future machine-learning-based recommendation.

Document:

* latency expectations;
* cache strategy;
* freshness requirements;
* handling of unavailable/deleted/restricted content;
* pagination or continuation semantics;
* fallback behavior when recommendation systems are degraded.

---

# SOCIAL GRAPH FOUNDATION

Define the conceptual architecture for:

* follow;
* unfollow;
* follower relationships;
* following relationships;
* blocks;
* privacy-aware visibility.

Document:

* authoritative relationship ownership;
* write behavior;
* read patterns;
* high-volume query strategy;
* indexing expectations;
* propagation to feeds and recommendations.

Do not permit blocking/privacy constraints to be bypassed through recommendation, search, feed, or direct-content access paths.

---

# ENGAGEMENT FOUNDATION

Define the architectural model for:

* likes;
* comments;
* replies;
* shares;
* favorites;
* views;
* watch-time signals.

Document:

* authoritative data;
* counter strategy;
* event strategy;
* concurrency considerations;
* idempotency;
* consistency expectations;
* high-volume write handling.

Explicitly distinguish authoritative interaction records from derived aggregate counters.

---

# SEARCH AND DISCOVERY FOUNDATION

Define the logical architecture for search and discovery.

Include:

* users/creators;
* hashtags;
* videos;
* sounds/audio references where applicable.

Document:

* source of truth;
* index ownership;
* indexing events;
* deletion propagation;
* eventual consistency;
* query responsibilities;
* privacy enforcement;
* moderation filtering;
* scaling considerations.

Do not expose restricted/deleted content merely because an index has not yet synchronized.

---

# NOTIFICATION FOUNDATION

Define the architectural model for:

* in-app notifications;
* push notifications;
* notification preferences;
* notification creation;
* deduplication;
* delivery retries;
* invalid-device handling;
* rate limiting.

Document the relationship between source events and notifications.

Prevent duplicate event delivery from generating uncontrolled notification duplication.

---

# MODERATION AND SAFETY FOUNDATION

Define the foundational safety architecture.

Document:

* report ingestion;
* moderation-state model;
* automated moderation integration boundary;
* manual review boundary;
* enforcement actions;
* account restrictions;
* content visibility restrictions;
* blocking;
* appeals/review boundaries where applicable;
* auditability.

Ensure moderation state is authoritative and consistently enforced across:

* feeds;
* search;
* playback;
* profiles;
* APIs;
* notifications;
* recommendations.

---

# ADMINISTRATION FOUNDATION

Define the administrative architecture for:

* privileged users;
* moderation operators;
* operational administrators;
* account controls;
* content controls;
* report handling;
* audit logs.

Document:

* privileged authentication;
* authorization;
* separation of administrative roles;
* audit requirements;
* sensitive-data restrictions;
* administrative API boundaries.

---

# SECURITY TRUST BOUNDARIES

Create a foundational security-boundary artifact.

Identify trust boundaries between:

* client and API;
* API and internal modules/services;
* application and database;
* application and Redis;
* application and event infrastructure;
* application and object storage;
* media workers and uploaded files;
* application and external providers;
* users and administrative systems.

For each boundary document:

* authentication;
* authorization;
* validation;
* encryption;
* secret handling;
* abuse controls;
* audit requirements.

Include major threat categories such as:

* authentication bypass;
* authorization bypass;
* IDOR;
* malicious uploads;
* injection;
* XSS/CSRF where applicable;
* SSRF;
* command execution through media processing;
* credential abuse;
* replay;
* rate-limit bypass;
* WebSocket abuse;
* data exposure.

---

# PRIVACY FOUNDATION

Define the architectural privacy model for:

* account visibility;
* content visibility;
* blocking;
* sensitive metadata;
* deletion;
* retention;
* analytics;
* moderation data;
* administrative access.

Document how privacy restrictions propagate into:

* caches;
* search;
* recommendations;
* analytics;
* notifications;
* derived datasets.

---

# OBSERVABILITY ARCHITECTURE

Define the foundational observability model.

At minimum cover:

* structured logs;
* metrics;
* distributed tracing;
* correlation IDs;
* request IDs;
* health checks;
* readiness;
* liveness;
* error tracking.

Define observability boundaries around:

* API requests;
* database operations;
* Redis;
* events;
* queues;
* media processing;
* feed generation;
* recommendation processing;
* search indexing;
* notification delivery;
* external providers.

Define sensitive-data logging restrictions.

---

# RELIABILITY FOUNDATION

Document architectural handling for:

* timeouts;
* retries;
* exponential backoff;
* jitter where appropriate;
* idempotency;
* duplicate events;
* partial failures;
* dependency outages;
* backpressure;
* graceful degradation;
* graceful shutdown;
* reconciliation;
* recovery.

Identify which dependencies are:

* critical;
* important but degradable;
* noncritical.

Define fallback behavior for degraded recommendation, search, notification, analytics, and media-processing dependencies where appropriate.

---

# ARCHITECTURAL DECISION RECORDS

Create ADRs or an equivalent decision-record set for important foundational choices.

At minimum record decisions concerning:

* monolith/modular-monolith vs independently deployed services;
* PostgreSQL ownership;
* Redis usage;
* event-streaming technology;
* background job technology;
* object-storage architecture;
* media-processing approach;
* CDN/media delivery model;
* API style;
* realtime strategy;
* search architecture;
* feed architecture;
* recommendation architecture;
* observability strategy;
* authentication/session strategy.

Each decision record must include:

* context;
* decision;
* alternatives considered;
* rationale;
* consequences;
* operational implications.

Do not create ADRs merely for trivial implementation choices.

---

# ARCHITECTURE CONTRACT REGISTER

Create a register identifying the contracts that subsequent implementation work must preserve.

At minimum classify contracts for:

* identifiers;
* timestamps;
* API errors;
* API pagination;
* authentication;
* authorization;
* user/account;
* video/content;
* media;
* social graph;
* engagement;
* comments;
* feed;
* recommendations;
* notifications;
* search;
* moderation;
* events;
* queues;
* configuration;
* observability.

For each contract, record:

* contract name;
* owner;
* consumers;
* lifecycle;
* compatibility expectations;
* versioning needs;
* repository artifact location.

This register may point to detailed contracts that will be created by later architecture work, but it must clearly establish the contract inventory and ownership model now.

---

# ARTIFACT DIRECTORY AND PORTABILITY

Create a dedicated architecture documentation structure that can be transferred independently between development environments.

The architecture package must not depend on hidden conversation context.

Use clear filenames and stable terminology.

At minimum organize the artifacts around categories such as:

* overview;
* system context;
* component architecture;
* domain model;
* data ownership;
* major data flows;
* media architecture;
* feed/recommendation architecture;
* social/engagement architecture;
* search/discovery;
* moderation/security;
* observability/reliability;
* ADRs;
* contract register.

Use repository-relative paths when describing locations.

Do not rely solely on diagrams whose meaning cannot be recovered from accompanying text.

---

# DIAGRAM REQUIREMENTS

Where diagrams materially improve understanding, create them in a durable repository-friendly form such as Mermaid or another text-based diagram format supported by the project.

Diagrams must be accompanied by explanatory text.

Do not create diagrams that are visually attractive but technically ambiguous.

Use consistent names across:

* diagrams;
* tables;
* schemas;
* ADRs;
* documentation.

---

# CONFIGURATION FOUNDATION

Define the architectural categories for configuration that later implementations must standardize.

At minimum cover:

* application configuration;
* database configuration;
* Redis configuration;
* event-stream configuration;
* object-storage configuration;
* media-processing configuration;
* authentication configuration;
* notification configuration;
* observability configuration;
* feature flags where applicable.

Distinguish:

* safe configuration values;
* sensitive secrets.

Never embed real credentials.

---

# VERSIONING AND EVOLUTION

Define foundational compatibility rules for:

* REST APIs;
* events;
* queue payloads;
* database schemas;
* client contracts;
* media metadata.

Address:

* backward compatibility;
* additive changes;
* deprecation;
* migrations;
* event versioning;
* rolling deployment compatibility.

The architecture must support independently generated project parts without relying on undocumented assumptions.

---

# FAILURE MODEL

Create a failure-domain matrix covering at least:

* PostgreSQL unavailable;
* Redis unavailable;
* event broker unavailable;
* job queue unavailable;
* object storage unavailable;
* CDN degradation;
* media worker failure;
* search unavailable;
* recommendation service unavailable;
* notification-provider failure;
* moderation dependency failure;
* external-provider timeout.

For each, document:

* affected capabilities;
* expected user-visible behavior;
* fallback behavior;
* retry behavior;
* data-consistency implications;
* recovery path;
* observability expectations.

Do not assume every dependency failure should make the entire platform unavailable.

---

# SECURITY AND PRIVACY ARTIFACTS

The architecture package must contain enough security documentation to guide future implementation.

At minimum create:

* trust-boundary documentation;
* high-level threat model;
* authorization model;
* sensitive-data classification guidance;
* secret-management requirements;
* media-security requirements;
* administrative security requirements.

Do not claim security certification or formal compliance unless independently established by evidence.

---

# ARCHITECTURE QUALITY BAR

The architecture is not complete merely because documents exist.

The architecture must be sufficiently concrete that an experienced implementation team can determine:

* what components exist;
* who owns what data;
* how components communicate;
* what the important contracts are;
* how major flows operate;
* where asynchronous processing occurs;
* how failures are handled;
* how security is enforced;
* how media moves through the system;
* how feeds and recommendations are structured;
* how the system evolves;
* what later implementation teams must preserve.

Resolve contradictions within this architecture package before completion.

Do not leave two competing definitions of the same entity, service, event, or architectural boundary without explicitly documenting the reason.

---

# IMPLEMENTATION BOUNDARY

This prompt is responsible for the **foundational architecture package**.

The current task includes:

* repository architectural inspection;
* foundational system architecture;
* domain boundaries;
* component architecture;
* conceptual domain model;
* data ownership;
* foundational media architecture;
* foundational feed/recommendation architecture;
* social and engagement architecture;
* search/discovery foundation;
* notification foundation;
* moderation/security foundation;
* observability and reliability foundation;
* ADRs for major foundational choices;
* architecture contract register;
* foundational failure model;
* portable architecture documentation.

The current task does **not** authorize implementation of:

* the complete backend;
* complete REST endpoints;
* the complete web application;
* the complete mobile application;
* production cloud provisioning;
* the complete QA suite;
* the complete media-processing implementation;
* a finished machine-learning recommendation system;
* a finished search engine deployment;
* a finished notification provider integration;
* a complete administration UI.

Those responsibilities belong to their appropriate planned implementation scopes.

Architecture may include schemas, examples, interface definitions, diagrams, and configuration specifications necessary to make the architecture implementation-useful, but these artifacts must not become a substitute for later bounded implementation work.

---

# QUALITY AND COMPATIBILITY REQUIREMENTS

All architecture decisions must remain compatible with:

* backend implementation;
* web frontend implementation;
* mobile implementation;
* infrastructure implementation;
* QA implementation;
* Codex/final integration.

Do not create contracts that require hidden knowledge.

Do not rely on another AI conversation.

Do not assume a previous architecture artifact exists unless it exists in the repository.

Every important decision made during this task must be represented in the generated architecture artifacts.

---

# TESTING AND VALIDATION

This is an architecture milestone, so validation must focus on architectural correctness rather than pretending that unimplemented product functionality has been tested.

Perform, as applicable:

* documentation consistency checks;
* schema validity checks;
* diagram syntax checks;
* contract consistency checks;
* duplicate terminology checks;
* architecture cross-reference checks;
* configuration schema validation where applicable;
* repository build/type validation if architecture changes include executable configuration or schema artifacts;
* static validation of generated architecture files.

Where architecture artifacts contain machine-readable schemas or specifications, validate them with appropriate tooling.

Do not claim runtime behavior is tested when the corresponding implementation does not yet exist.

---

# DOCUMENTATION REQUIREMENTS

All architecture artifacts must:

* use consistent terminology;
* identify authoritative ownership;
* distinguish current architectural scope from future capabilities;
* document meaningful assumptions;
* document important tradeoffs;
* identify external dependencies;
* identify unresolved decisions honestly;
* remain portable across separate AI development conversations.

Write documentation for an engineering audience.

Avoid vague statements such as:

* "the system should scale";
* "use best practices";
* "the API will be secure";
* "the database will be optimized";

without accompanying concrete architectural decisions.

---

# FINAL ARCHITECTURE REVIEW

Before declaring completion, internally verify that the architecture package:

* has one coherent system model;
* has consistent terminology;
* has explicit domain ownership;
* has explicit component responsibilities;
* identifies authoritative data;
* identifies derived data;
* defines foundational data flows;
* defines media boundaries;
* defines feed boundaries;
* defines recommendation boundaries;
* defines social/engagement boundaries;
* defines search boundaries;
* defines notification boundaries;
* defines moderation boundaries;
* defines security boundaries;
* defines observability boundaries;
* defines failure behavior;
* defines major architectural decisions;
* identifies cross-part contracts;
* is portable;
* does not depend on a previous AI response;
* does not claim implementation that has not occurred;
* does not claim external infrastructure that has not been verified;
* is detailed enough to guide later implementation.

Resolve contradictions before completion.

---

# IMPLEMENTATION REPORT

After completing the architecture milestone, provide a concise completion report identifying:

* architecture files created;
* architecture files modified;
* architecture files removed, if any;
* major architectural decisions;
* domain boundaries established;
* data ownership decisions;
* media architecture decisions;
* feed/recommendation decisions;
* search/discovery decisions;
* social/engagement decisions;
* security decisions;
* privacy decisions;
* observability decisions;
* reliability decisions;
* ADRs created;
* contract-register changes;
* validation performed;
* repository checks performed;
* assumptions that remain;
* unresolved architectural issues, if any;
* integration considerations for later implementation work.

Do not report an artifact as created unless it actually exists in the repository.

Do not claim that a decision was validated operationally unless it was actually validated.

---

# DEFINITION OF DONE

This architecture milestone is complete only when:

* the repository was inspected;
* the foundational architecture artifacts were created or updated;
* the system context is documented;
* the component architecture is documented;
* domain boundaries are explicit;
* data ownership is explicit;
* major data flows are documented;
* media architecture is defined;
* feed architecture is defined;
* recommendation boundaries are defined;
* social and engagement architecture is defined;
* search/discovery architecture is defined;
* notification architecture is defined;
* moderation and safety architecture is defined;
* security trust boundaries are defined;
* privacy architecture is defined;
* observability architecture is defined;
* reliability/failure behavior is defined;
* major ADRs are documented;
* the contract register exists;
* terminology is consistent;
* artifacts are portable;
* diagrams and schemas are valid where applicable;
* architecture contradictions have been resolved;
* no hidden dependency on another AI conversation exists;
* no fake implementation is presented as completed;
* no production infrastructure is claimed to exist without verification;
* the architecture package is detailed enough to guide later implementation;
* the required validation has been performed;
* the completion report accurately describes the work performed.

Implement **only the current prompt's scope**.

Do not expand this milestone into full application implementation.
