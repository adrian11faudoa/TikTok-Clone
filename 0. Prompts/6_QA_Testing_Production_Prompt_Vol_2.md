# TikTok-Style Short-Form Video Platform — QA Prompt — Volume 2

# ROLE

You are the **Senior QA Engineering, Quality Systems, Release Validation, Performance, Security Validation, and Reliability Test Engineering team** responsible for implementing the second bounded QA workstream for a production-grade TikTok-style short-form video platform.

Operate with the standards of a funded startup / enterprise engineering organization.

You are responsible for creating and integrating the **advanced validation, release qualification, performance, resilience, security regression, cross-platform end-to-end, and operational test capabilities** required to determine whether the implemented system behaves correctly under realistic production conditions.

Do not merely describe a test strategy.

Inspect the repository and implement the actual QA capabilities, executable tests, test infrastructure, validation tooling, fixtures, datasets, reports, automation, and documentation that fall within this prompt's scope.

Do not invent functionality that does not exist.

Do not silently repair unrelated application defects.

Do not weaken assertions merely to make tests pass.

Do not convert unavailable external dependencies into false-positive mocks without explicitly documenting the substitution.

# PROJECT

Build QA validation capabilities for a **TikTok-style short-form video platform** supporting:

* account registration and authentication;
* profiles and creator identity;
* follows, followers, blocking, and social graph operations;
* short-form video creation and lifecycle management;
* secure media upload;
* media processing and transcoding;
* thumbnails and playback variants;
* CDN-backed playback;
* captions, hashtags, mentions, and sounds;
* personalized and following feeds;
* discovery and search;
* trending content;
* likes, comments, replies, shares, and favorites;
* notifications and push-delivery workflows;
* creator analytics;
* reporting, moderation, enforcement, and administrative operations;
* privacy, account controls, deletion, and retention;
* event-driven processing;
* background workers and queues;
* observability and operational diagnostics;
* web and mobile clients.

The system is expected to operate at large scale with high concurrency, high media throughput, substantial event volume, and failure conditions that must be handled predictably.

# TARGET USERS

The system must support:

* viewers;
* registered users;
* creators;
* moderators;
* administrators;
* support and operations personnel;
* automated workers and platform services.

Testing must reflect the distinct permissions, data visibility, and operational responsibilities of these roles.

# SCALE TARGET

Validate behavior relevant to a platform capable of serving:

* millions to hundreds of millions of accounts;
* large concurrent feed and playback traffic;
* high rates of likes, comments, follows, shares, notifications, and behavioral events;
* large concurrent media uploads and processing jobs;
* substantial background queue and event-stream traffic;
* geographically distributed production deployments.

Do not interpret the scale target as a requirement to create an artificial load test against unavailable production-scale infrastructure.

Instead, implement scalable test mechanisms, realistic workload models, parameterized datasets, representative concurrency profiles, and clearly documented extrapolation limits.

# TECHNOLOGY DIRECTION

Use the technologies and repository architecture actually present in the project, with expected direction including:

* Next.js / React / TypeScript for web;
* React Native / Expo / TypeScript for mobile;
* Node.js / NestJS / TypeScript for backend services;
* PostgreSQL;
* Redis;
* Kafka or Redpanda;
* BullMQ or equivalent worker infrastructure;
* S3-compatible object storage;
* FFmpeg-based media processing;
* CDN-backed media delivery;
* REST APIs;
* WebSocket or equivalent realtime mechanisms where implemented;
* OpenTelemetry;
* Prometheus / Grafana or equivalent observability;
* containerized deployment;
* Kubernetes and infrastructure-as-code where implemented.

Do not replace existing technology merely to simplify testing.

Where the repository differs from this direction, test the actual implementation rather than creating a parallel fictional stack.

# REPOSITORY INSPECTION

Before implementing anything:

* inspect the repository structure;
* identify backend services, workers, web applications, mobile applications, libraries, infrastructure, scripts, and test suites;
* identify existing unit, integration, contract, E2E, performance, security, and CI tooling;
* inspect package manifests and test configuration;
* inspect environment/configuration handling;
* inspect database migrations and seed mechanisms;
* inspect authentication and authorization behavior;
* inspect event, queue, worker, and media-processing paths;
* inspect observability integration;
* inspect existing QA documentation;
* identify supported local and CI execution paths;
* identify existing test utilities, fixtures, factories, mocks, simulators, and test datasets;
* identify already implemented quality gates;
* identify external dependencies required by meaningful end-to-end or performance validation.

Do not assume that another agent or another conversation has completed any test capability.

Treat the repository and portable project artifacts present in the working environment as the only implementation evidence available to you.

# IMPLEMENTATION OBJECTIVE

Implement the advanced QA layer required to validate the platform as an integrated system under:

* realistic user journeys;
* realistic concurrency;
* degraded dependencies;
* asynchronous processing;
* partial failures;
* retries;
* duplicate delivery;
* delayed event processing;
* stale caches;
* race conditions;
* security attacks and authorization abuse;
* large datasets;
* media-processing failures;
* deployment transitions;
* recovery operations;
* cross-platform client behavior;
* release candidates and regression cycles.

The resulting QA system must produce evidence that engineers can use to understand:

* what was tested;
* under what conditions;
* with which data and identities;
* which contracts were validated;
* which failure modes were exercised;
* what passed;
* what failed;
* what could not be executed;
* why something could not be executed;
* and what environmental assumptions affected the result.

# SCOPE BOUNDARY

This prompt covers advanced QA implementation and validation.

The scope includes:

* integrated E2E validation;
* cross-platform user journeys;
* release qualification;
* performance testing;
* load, stress, and soak testing;
* resilience and fault-injection testing;
* security regression testing;
* privacy regression testing;
* deployment and rollback validation;
* backup and restore validation;
* event and queue reliability validation;
* media pipeline reliability validation;
* test observability;
* test evidence and reporting;
* CI quality gates;
* regression orchestration;
* test environment readiness checks;
* test-data lifecycle management;
* defect reproducibility tooling;
* test documentation and operational runbooks.

The scope does not include:

* implementing new product features unrelated to testability;
* rewriting backend business logic merely to make tests easier;
* replacing the project's production architecture;
* inventing cloud resources that cannot actually be provisioned or validated;
* creating fake success paths for unavailable systems;
* building a full analytics warehouse;
* building an independent production monitoring platform outside the project's operational scope;
* implementing unrelated frontend or mobile features;
* introducing new business behavior solely for demonstration purposes;
* deleting meaningful assertions because of intermittent failures;
* declaring compliance certifications that have not actually been established.

# ADVANCED END-TO-END TEST FOUNDATION

Implement executable E2E coverage for the highest-risk complete user journeys.

Cover, where supported by the implemented product:

* registration;
* authentication;
* session establishment;
* profile creation and editing;
* follow and unfollow;
* block and unblock;
* video upload initiation;
* secure upload;
* media processing;
* publish;
* playback;
* feed retrieval;
* feed interaction;
* like and unlike;
* comment and reply;
* share;
* favorite/save;
* search;
* hashtag discovery;
* creator discovery;
* trending discovery;
* notification generation;
* notification retrieval;
* creator analytics generation;
* content reporting;
* moderation state transitions;
* administrative review;
* account deletion;
* deletion propagation;
* session invalidation;
* privacy enforcement.

Each major E2E journey must validate more than HTTP success.

Where applicable, verify:

* persisted state;
* authorization;
* visibility;
* emitted events;
* queue behavior;
* asynchronous completion;
* cache invalidation;
* notification effects;
* analytics effects;
* audit records;
* media state transitions;
* deletion propagation;
* client-visible state.

Avoid tests that pass solely because an endpoint returned a nominal success response.

# CROSS-CLIENT VALIDATION

Implement representative end-to-end coverage across the supported web and mobile applications.

Validate the same core product behaviors through the user-facing surfaces that actually implement them.

Cover:

* authentication and session lifecycle;
* feed navigation;
* playback;
* engagement;
* comments;
* profiles;
* follow relationships;
* blocking;
* search;
* notifications;
* saved content;
* content reporting;
* creator workflows where implemented;
* deep links;
* push notification transitions where supported;
* reconnect behavior;
* foreground/background transitions;
* logout and session expiration.

Validate that API and persistence behavior remain consistent across clients.

Where a client intentionally differs in behavior, encode that difference explicitly rather than treating the discrepancy as accidental.

# REALISTIC USER JOURNEY SCENARIOS

Create reusable multi-user scenarios representing:

* viewer consuming a feed;
* creator publishing content;
* creator revising metadata before publication;
* viewer interacting with creator content;
* creator receiving engagement notifications;
* user blocking another user;
* user reporting content;
* moderator reviewing a report;
* administrator applying a permitted administrative action;
* deleted user whose content and relationships require cleanup;
* users operating under different privacy settings;
* anonymous viewer interacting with public content;
* authenticated viewer accessing restricted functionality.

Scenarios must use deterministic identities and test data.

Do not use personal data or real credentials.

# RELEASE QUALIFICATION

Implement a repeatable release qualification suite that can be executed against a release candidate.

The suite must verify, at minimum:

* service startup;
* migrations;
* configuration validation;
* authentication;
* authorization;
* critical APIs;
* critical UI paths;
* core mobile paths where automated execution is supported;
* database connectivity;
* Redis connectivity where required;
* event publishing;
* worker execution;
* queue consumption;
* media-processing prerequisites;
* playback readiness;
* search readiness;
* notification behavior;
* observability availability;
* health and readiness behavior;
* graceful shutdown;
* rollback-sensitive compatibility checks.

Define explicit blocking failures for release-critical functionality.

Do not label a release as qualified if critical checks were skipped.

Where infrastructure required for a release test is unavailable, the result must state that the validation was not executed and identify the missing dependency.

# RELEASE-CANDIDATE TEST MATRIX

Create a machine-readable and human-readable matrix covering:

* feature/domain;
* test layer;
* environment;
* prerequisite;
* execution command;
* expected result;
* failure severity;
* release-blocking status;
* data requirements;
* dependency requirements;
* evidence location.

The matrix must be maintainable and tied to actual automated tests.

Do not create a static checklist that claims coverage without executable evidence.

# REGRESSION SUITE DESIGN

Organize regression coverage by risk and execution time.

Provide distinct mechanisms for:

* fast pre-commit validation;
* pull-request validation;
* broader CI validation;
* release-candidate validation;
* scheduled deep regression;
* performance validation;
* resilience validation;
* security regression;
* cross-platform validation.

Avoid forcing the entire expensive suite into every developer feedback loop.

Define reliable test selection and tagging mechanisms.

Ensure test categories are discoverable and consistently executable.

# TEST DATA ENGINEERING

Implement reusable deterministic data factories and scenario builders for advanced QA.

Support data representing:

* users;
* accounts in distinct lifecycle states;
* creators;
* private and public profiles;
* social relationships;
* blocked users;
* videos;
* media assets;
* processing states;
* visibility modes;
* engagement;
* comments and replies;
* feed candidates;
* discovery objects;
* notifications;
* reports;
* moderation cases;
* analytics events;
* deletion scenarios;
* expired sessions;
* permission variants.

Support:

* seeded deterministic datasets;
* randomized data where appropriate;
* controlled dataset size;
* cleanup;
* isolation;
* reproducibility;
* parallel execution without collisions.

Do not depend on production data.

# LARGE-DATASET VALIDATION

Create parameterized test datasets capable of validating behavior with materially larger data volumes than ordinary unit and integration fixtures.

Cover representative cases such as:

* users with large follower counts;
* videos with high engagement;
* creators with large content libraries;
* users with many notifications;
* comments with substantial reply trees;
* high-volume event histories;
* feeds containing large candidate populations;
* search indexes containing many documents;
* expired and retained data combinations.

Focus on correctness, pagination, indexing, filtering, aggregation, and latency behavior.

Document the actual dataset sizes used.

Do not claim hyperscale validation from tiny datasets.

# PERFORMANCE TESTING

Implement executable performance testing for critical paths.

At minimum, define workloads for:

* authentication;
* profile retrieval;
* feed retrieval;
* pagination;
* video metadata retrieval;
* playback authorization;
* likes;
* comments;
* follows;
* search;
* trending discovery;
* notification retrieval;
* creator analytics;
* reporting;
* moderation operations;
* high-volume event ingestion;
* queue/job processing;
* media-processing orchestration where practical.

Capture:

* latency;
* throughput;
* concurrency;
* error rate;
* saturation indicators;
* queue depth;
* database behavior;
* cache behavior;
* resource utilization where available.

Use parameterized workload profiles rather than hardcoded single measurements.

# PERFORMANCE BASELINES

Create a documented baseline mechanism.

Track at least:

* median latency;
* high-percentile latency;
* throughput;
* failure rate;
* timeout rate;
* queue delay;
* processing duration;
* resource pressure;
* startup time where relevant.

Do not invent universal performance targets.

Where engineering SLOs or thresholds exist in the repository/project artifacts, validate against them.

Where a target is not established, expose measurements without inventing a pass threshold and clearly identify the missing acceptance criterion.

# LOAD TESTING

Implement multiple workload profiles such as:

* normal sustained load;
* elevated load;
* burst traffic;
* asymmetric read-heavy traffic;
* engagement-heavy traffic;
* event-ingestion-heavy traffic;
* notification-heavy traffic;
* search-heavy traffic;
* media-processing-heavy traffic.

Validate:

* correctness under load;
* error behavior;
* rate limiting;
* queue behavior;
* retries;
* duplicate processing protection;
* database contention;
* cache degradation;
* backpressure;
* autoscaling signals where infrastructure supports them.

Do not treat a high request count alone as meaningful load validation.

# STRESS TESTING

Create controlled mechanisms for increasing load until one or more documented resource boundaries are reached.

Capture:

* first failure point;
* failure mode;
* affected dependency;
* recovery behavior;
* queue growth;
* error amplification;
* data integrity impact;
* client-visible symptoms;
* whether the system recovers automatically.

Never intentionally damage an uncontrolled external production environment.

# SOAK TESTING

Implement long-duration workloads where practical.

Use soak scenarios to detect:

* memory leaks;
* descriptor leaks;
* connection leaks;
* queue accumulation;
* stale locks;
* duplicate event amplification;
* cache instability;
* resource fragmentation;
* worker degradation;
* long-tail latency deterioration.

Document execution duration and environment characteristics.

Do not claim soak-test evidence if the run was too short to reveal meaningful long-duration behavior.

# ASYNCHRONOUS SYSTEM VALIDATION

Create tests for delayed and out-of-order asynchronous processing.

Cover:

* duplicate events;
* retries;
* delayed events;
* out-of-order events;
* worker restarts;
* queue redelivery;
* partial completion;
* dead-letter behavior;
* poison messages;
* idempotency;
* transactional outbox behavior;
* eventual consistency;
* stale reads;
* replay/reconciliation behavior.

Verify that duplicate processing does not corrupt state.

Verify that retries do not produce uncontrolled side effects.

Verify that permanent failures become visible through the documented failure mechanism.

# MEDIA PIPELINE RELIABILITY TESTING

Create realistic media test assets and validation flows covering:

* valid supported video;
* unsupported format;
* malformed file;
* truncated file;
* oversized file;
* low-duration edge cases;
* unusual dimensions;
* invalid metadata;
* corrupted media;
* processing timeout;
* worker interruption;
* storage interruption;
* retry;
* duplicate job delivery;
* partial variant failure;
* thumbnail generation failure;
* final publication gating;
* deletion during processing;
* expired upload authorization.

Validate security checks and state transitions.

Ensure failed media jobs cannot accidentally publish unusable assets.

# FEED AND RECOMMENDATION VALIDATION

Create deterministic tests for:

* feed ordering;
* pagination;
* deduplication;
* blocked-user filtering;
* visibility filtering;
* deleted-content filtering;
* authorization;
* freshness behavior;
* engagement effects;
* negative feedback;
* recommendation fallbacks;
* anonymous behavior;
* authenticated behavior;
* cache reuse;
* cache invalidation.

Where ranking uses nondeterministic or externally changing inputs, provide deterministic test fixtures and stable assertions for invariant behavior rather than overfitting to incidental order.

# SEARCH AND DISCOVERY VALIDATION

Validate:

* indexing;
* updates;
* deletion propagation;
* visibility rules;
* blocked-user filtering;
* pagination;
* search normalization;
* creator discovery;
* hashtag discovery;
* video discovery;
* sound discovery;
* trending logic;
* stale-index behavior;
* rebuild/version compatibility.

Test consistency between source-of-truth data and searchable representations.

# NOTIFICATION VALIDATION

Test:

* notification creation;
* deduplication;
* preferences;
* device targeting;
* invalid devices;
* retries;
* backoff;
* read state;
* unread counts;
* deep links;
* push-provider failures;
* duplicate delivery;
* eventual delivery;
* deletion/privacy effects.

Do not require external push-provider success when a real provider is unavailable.

Instead, distinguish:

* provider integration validation;
* application-level notification validation;
* end-to-end external delivery validation.

# MODERATION AND SAFETY REGRESSION

Create tests covering:

* report creation;
* duplicate reports;
* moderation state transitions;
* permissions;
* enforcement;
* appeals or review paths where implemented;
* audit events;
* restricted-content visibility;
* removed-content behavior;
* blocked-user effects;
* administrator authorization;
* moderator authorization;
* unauthorized administrative access;
* audit immutability or append-only expectations where implemented.

Validate that privileged actions cannot be performed by ordinary users.

# SECURITY REGRESSION TESTING

Implement automated security regression coverage for:

* authentication bypass;
* broken authorization;
* object-level authorization failures;
* privilege escalation;
* insecure direct object reference patterns;
* session fixation or reuse;
* expired-session access;
* token misuse;
* CSRF protections where relevant;
* rate-limit bypass;
* excessive input size;
* malicious payloads;
* injection attempts;
* unsafe file uploads;
* path traversal;
* SSRF-sensitive integration boundaries;
* insecure redirects;
* secret exposure;
* sensitive data leakage in API responses;
* sensitive data leakage in logs;
* unauthorized media access.

Test security controls at the actual enforcement boundary.

Do not rely only on UI hiding.

# PRIVACY REGRESSION

Validate that:

* private content is not publicly accessible;
* blocked users do not gain prohibited visibility;
* deleted accounts lose access according to policy;
* deleted content is no longer discoverable where required;
* restricted profile information is not leaked;
* analytics do not expose unauthorized data;
* administrative information is role-protected;
* logs do not contain prohibited sensitive information;
* caches do not bypass authorization;
* search indexes respect deletion and visibility;
* notification payloads do not expose unauthorized information.

# ABUSE AND RATE-LIMIT VALIDATION

Create executable abuse scenarios for:

* login attempts;
* registration;
* password or credential recovery where implemented;
* follows;
* likes;
* comments;
* shares;
* reports;
* search;
* notifications;
* media upload;
* event ingestion;
* privileged operations.

Validate that rate limiting:

* activates when expected;
* returns the documented error contract;
* does not lock out unrelated users;
* behaves predictably under concurrent requests;
* recovers according to policy;
* produces useful observability.

# CONCURRENCY AND RACE-CONDITION TESTING

Implement tests targeting competing operations such as:

* follow versus unfollow;
* like versus unlike;
* duplicate like;
* duplicate share;
* simultaneous comments;
* simultaneous edits;
* concurrent publication;
* concurrent deletion;
* moderation versus publication;
* notification creation versus preference changes;
* account deletion versus active requests;
* worker retries versus successful completion.

Validate final-state correctness and invariant preservation.

Do not merely assert that all requests returned a status code.

# DATABASE VALIDATION

Create advanced tests for:

* migration compatibility;
* rollback-sensitive changes where supported;
* transaction boundaries;
* optimistic concurrency;
* unique constraints;
* foreign-key integrity;
* soft deletion;
* cleanup jobs;
* index effectiveness where measurable;
* deadlock-sensitive operations;
* concurrent writes;
* connection exhaustion handling;
* retry behavior;
* data reconciliation.

Include tests capable of detecting duplicate or orphaned records created by race conditions.

# CACHE VALIDATION

Test:

* cache hits;
* cache misses;
* invalidation;
* expiry;
* stale data windows;
* concurrent regeneration;
* authorization-sensitive cache boundaries;
* deleted-object invalidation;
* negative caching where used;
* cache outage behavior.

Verify that stale cache data cannot violate privacy or authorization.

# EVENT AND QUEUE VALIDATION

Validate event contracts under:

* normal publication;
* duplicate delivery;
* delayed delivery;
* malformed payload;
* unknown version;
* consumer restart;
* producer retry;
* consumer retry;
* dead-letter routing;
* partition-related ordering expectations;
* replay;
* recovery.

Verify that event consumers fail safely when receiving unsupported or invalid events.

# DEPLOYMENT VALIDATION

Create automated or scripted checks for:

* application startup;
* readiness;
* liveness;
* graceful shutdown;
* schema compatibility;
* configuration compatibility;
* versioned event compatibility;
* queue-worker compatibility;
* rolling deployment behavior;
* migration sequencing;
* rollback;
* cache compatibility;
* client/API compatibility.

Where production-like infrastructure is available, exercise the deployment behavior.

Where it is not available, build validation against the closest supported environment and document the limitation.

# BACKUP AND RESTORE VALIDATION

Implement executable validation where backup infrastructure is accessible.

Cover:

* backup creation;
* backup integrity;
* restore into isolated environment;
* schema/data validation;
* application startup after restore;
* critical workflows after restore;
* event/queue consistency where relevant;
* object-storage/media restoration where supported;
* recovery documentation verification.

Do not claim disaster-recovery success without actually restoring data in a controlled environment.

# FAILURE INJECTION

Implement safe, repeatable failure scenarios for dependencies such as:

* PostgreSQL unavailable;
* Redis unavailable;
* event broker unavailable;
* queue worker unavailable;
* search unavailable;
* object storage unavailable;
* CDN/origin failure;
* notification provider failure;
* media-processing worker failure;
* network latency;
* transient network errors;
* dependency timeouts;
* malformed dependency responses.

Validate:

* bounded retries;
* backoff;
* circuit-breaking where implemented;
* graceful degradation;
* error contracts;
* no data corruption;
* recovery after restoration.

Do not create destructive fault-injection tooling capable of unintentionally affecting unrelated environments.

# RESILIENCE TESTING

Create scenarios for:

* service restart;
* worker restart;
* leader or primary failure where infrastructure permits;
* consumer restart;
* queue backlog;
* partial dependency outage;
* connection exhaustion;
* cache loss;
* search index degradation;
* object-storage interruption.

Verify recovery behavior rather than only failure detection.

# CLIENT RESILIENCE VALIDATION

For web and mobile clients, validate:

* slow network;
* intermittent network;
* complete offline transition;
* reconnect;
* request timeout;
* duplicate submission;
* app backgrounding;
* app foregrounding;
* process restart where supported;
* stale cached data;
* expired authentication;
* push/deep-link transition;
* interrupted upload.

Ensure user-visible failure behavior is explicit and does not silently lose important state.

# ACCESSIBILITY REGRESSION

Extend accessibility testing across critical web and mobile workflows.

Validate:

* keyboard access;
* focus management;
* semantic controls;
* accessible names;
* screen-reader compatibility where automation supports it;
* color-independent state communication;
* dynamic content announcements;
* reduced-motion behavior where implemented;
* touch target expectations;
* form and validation feedback.

Prioritize:

* authentication;
* feed;
* playback controls;
* comments;
* profile;
* search;
* notifications;
* creator workflows;
* reporting;
* settings.

# VISUAL REGRESSION

Where the repository already supports visual testing, implement targeted snapshots or equivalent validation for high-risk screens.

Focus on:

* responsive feed layouts;
* video player states;
* comment surfaces;
* search/discovery;
* notification center;
* creator surfaces;
* moderation surfaces where applicable;
* error/loading/empty states.

Avoid brittle snapshots that fail because of nondeterministic timestamps, generated IDs, randomized content, or remote assets.

# TEST OBSERVABILITY

Implement QA observability that makes failures diagnosable.

Capture, where appropriate:

* test run identifier;
* scenario identifier;
* environment;
* build/release identifier;
* user identity class;
* request correlation ID;
* event correlation ID;
* queue/job identifiers;
* media identifiers;
* relevant database identifiers;
* timestamps;
* dependency failures;
* logs;
* traces;
* screenshots;
* video recordings for UI failures where supported;
* performance measurements.

Do not capture secrets or unnecessary sensitive user data.

# FAILURE TRIAGE AND REPRODUCTION

Create standardized failure artifacts containing:

* test name;
* scenario;
* environment;
* exact command;
* inputs;
* dataset;
* relevant identifiers;
* expected behavior;
* actual behavior;
* logs;
* traces where available;
* screenshots/video where applicable;
* first failing assertion;
* dependency status;
* reproducibility information.

Provide tooling that allows an engineer to reproduce important failures without reconstructing undocumented state manually.

# FLAKY TEST CONTROL

Implement mechanisms to detect and manage flaky tests.

Do not hide flaky tests through indefinite retries.

For retries:

* record the original failure;
* record retry outcome;
* distinguish flaky from deterministic failures;
* report retry frequency;
* avoid masking release-blocking defects;
* track quarantined tests explicitly.

A test must not become permanently non-blocking merely because it is unstable.

# PARALLEL EXECUTION

Ensure test suites can run in parallel safely where appropriate.

Prevent collisions involving:

* users;
* database records;
* media files;
* storage objects;
* queues;
* ports;
* temp directories;
* cache keys;
* snapshots;
* event identifiers.

Use deterministic isolation mechanisms.

# TEST ENVIRONMENT VALIDATION

Create preflight checks for each supported QA environment.

Validate:

* required services;
* credentials presence without printing secrets;
* schema version;
* migrations;
* seed data;
* feature configuration;
* queues;
* brokers;
* storage;
* media tools;
* search;
* observability;
* mobile/web automation prerequisites.

Fail fast when prerequisites are missing.

Do not allow a missing dependency to produce misleading application failures.

# CI/CD INTEGRATION

Integrate the advanced QA suites into CI/CD according to execution cost and release risk.

Define:

* fast gates;
* standard CI gates;
* release gates;
* scheduled deep suites;
* performance jobs;
* security jobs;
* resilience jobs.

CI output must make it clear whether a job:

* passed;
* failed;
* was skipped;
* could not execute;
* was blocked by an unavailable dependency.

Do not configure CI to ignore failures without explicit documented justification.

# QUALITY GATES

Define automated quality gates around:

* correctness;
* security;
* contract compatibility;
* regression;
* performance;
* reliability;
* accessibility;
* deployment safety.

Do not invent numerical gates where no engineering target exists.

Where thresholds are already defined, encode them automatically.

Where thresholds are intentionally not yet specified, create a visible configuration point and document that release approval still requires human evaluation rather than pretending a threshold exists.

# CONTRACT REGRESSION

Validate the implementation against externally meaningful contracts for:

* IDs;
* timestamps;
* authentication;
* authorization;
* errors;
* pagination;
* idempotency;
* APIs;
* events;
* queues;
* realtime behavior;
* media states;
* notifications;
* search;
* moderation;
* analytics.

The test suite must detect breaking changes in:

* required fields;
* field types;
* enum values;
* error formats;
* status semantics;
* pagination behavior;
* idempotency behavior;
* event versions;
* authorization behavior.

# API COMPATIBILITY TESTING

Create executable contract regression tests covering:

* request validation;
* response structure;
* status codes;
* canonical errors;
* pagination;
* authentication;
* authorization;
* rate limiting;
* idempotency;
* backwards-compatible field evolution.

Do not validate only happy paths.

# MIGRATION SAFETY VALIDATION

Create tests for schema changes that could affect:

* running application versions;
* background workers;
* event consumers;
* administrative APIs;
* analytics;
* search indexing;
* deletion;
* reporting.

Validate migration sequencing and compatibility where the deployment architecture supports rolling updates.

# SECURITY TOOLING INTEGRATION

Integrate appropriate automated scanners already compatible with the repository, such as:

* dependency vulnerability scanning;
* secret scanning;
* static analysis;
* container scanning;
* infrastructure-as-code scanning;
* API security testing;
* dependency license checks where already required.

Do not fabricate scan results.

Document tooling that could not execute because required infrastructure or credentials were unavailable.

# TEST ARTIFACT RETENTION

Configure useful artifact retention for CI and local diagnostics.

Retain only what is operationally useful, such as:

* test reports;
* screenshots;
* videos;
* logs;
* traces;
* performance summaries;
* crash data;
* coverage reports.

Avoid retaining unnecessary sensitive test data indefinitely.

# COVERAGE ANALYSIS

Produce coverage reporting appropriate to the different layers.

Track meaningful coverage across:

* unit;
* integration;
* contract;
* API;
* worker;
* event;
* E2E;
* web;
* mobile;
* security;
* resilience.

Do not treat code coverage percentage as equivalent to quality.

Highlight untested high-risk paths even when line coverage is high.

# REGRESSION RISK REPORTING

Create a mechanism for associating major changed domains with their regression suites.

At minimum support risk mapping for:

* identity;
* authentication;
* authorization;
* media;
* playback;
* feed;
* recommendations;
* search;
* engagement;
* notifications;
* moderation;
* analytics;
* deletion/privacy;
* infrastructure-sensitive behavior.

This must help CI or engineers select the relevant validation suite for a change.

# TEST DOCUMENTATION

Produce clear QA documentation covering:

* local execution;
* CI execution;
* environment prerequisites;
* test categories;
* tags;
* data setup;
* cleanup;
* release qualification;
* performance execution;
* security regression;
* resilience testing;
* failure triage;
* artifact locations;
* known external dependencies;
* unsupported automation;
* interpretation of results.

Documentation must describe actual commands and actual repository paths.

Do not write documentation for tools that do not exist.

# NO FALSE CONFIDENCE

The QA implementation must explicitly distinguish:

* automated and verified;
* automated but environment-blocked;
* manually verified;
* not yet covered;
* dependency-limited;
* intentionally out of scope.

Never mark a feature as tested merely because a test file exists.

Never claim production-scale validation based on a development environment.

Never turn skipped tests into passes.

Never suppress a failure merely to create a green pipeline.

# REQUIRED IMPLEMENTATION ARTIFACTS

Create or update the actual repository artifacts necessary to deliver this QA scope, including as applicable:

* advanced E2E test suites;
* cross-platform test flows;
* release qualification suite;
* performance/load/stress/soak tooling;
* resilience and fault-injection tests;
* media reliability tests;
* event and queue failure tests;
* security regression suites;
* privacy regression suites;
* test data factories;
* large-data generators;
* test environment preflight tooling;
* CI workflows;
* quality-gate configuration;
* regression tagging;
* test reports;
* release test matrix;
* performance baseline documentation;
* failure triage documentation;
* test execution documentation;
* reproducibility helpers;
* test cleanup utilities.

Do not create meaningless filler files.

# TESTING PRINCIPLES

Apply all of the following:

* tests must be deterministic whenever practical;
* assertions must validate meaningful outcomes;
* tests must isolate their state;
* tests must clean up their data;
* asynchronous behavior must be tested asynchronously;
* retries must be bounded;
* time must be controllable where practical;
* IDs must be deterministic or traceable in tests;
* no hardcoded production credentials;
* no real personal data;
* no production database access for destructive tests;
* no destructive failure injection against uncontrolled environments;
* no hidden network dependencies;
* no tests that pass because the application returned a generic success;
* no fake implementations disguised as integration tests;
* no swallowed exceptions;
* no blanket test disabling;
* no arbitrary sleeps when condition-based synchronization is possible.

# HANDLING EXTERNAL DEPENDENCIES

For every dependency that cannot be fully exercised in the available environment:

* identify it;
* identify which tests depend on it;
* provide an appropriate local substitute only when such substitution preserves meaningful application behavior;
* distinguish mocked, simulated, emulated, and real integration testing;
* document what remains unverified;
* ensure CI does not falsely report external-delivery success when only an internal simulation was executed.

Examples include:

* push providers;
* CDN behavior;
* cloud object storage;
* external identity providers;
* external moderation providers;
* managed search;
* managed Kafka/Redis/PostgreSQL;
* cloud load balancers.

# TEST SECURITY

QA infrastructure itself must be secure.

Ensure:

* credentials come from approved configuration mechanisms;
* secrets are never committed;
* secrets are not printed in logs;
* test tokens are scoped;
* privileged fixtures are controlled;
* destructive tests are environment-protected;
* test environments are identifiable;
* external endpoints are allowlisted where practical;
* generated test data cannot accidentally target production.

# IMPLEMENTATION SAFETY

When implementation defects are discovered:

* fix only defects necessary to make the current QA scope executable or correct, when such fixes are clearly bounded and safe;
* do not redesign unrelated product behavior;
* document all application changes made for testability;
* keep test-specific hooks behind safe configuration boundaries;
* do not weaken production security merely to enable testing.

# OUT-OF-SCOPE AREAS

Do not perform the following as part of this prompt:

* redesign the platform architecture;
* implement unrelated backend domains;
* implement unrelated web features;
* implement unrelated mobile features;
* replace the database;
* replace event infrastructure;
* invent unsupported cloud integrations;
* build a new recommendation ML platform;
* build a new analytics warehouse;
* implement monetization;
* implement live streaming;
* implement direct messaging;
* implement advertising;
* create a surprise final integration phase;
* declare the product production-ready solely because the tests are green.

# VALIDATION REQUIREMENTS

After implementation:

* execute the relevant test suites;
* execute release qualification checks;
* execute available security scans;
* execute available performance tests at representative levels;
* execute resilience scenarios that are safe in the current environment;
* validate CI configuration;
* validate test-data setup and teardown;
* validate reports and artifacts;
* validate that failed tests actually fail when their expected condition is intentionally broken where practical;
* validate that skipped or blocked tests are clearly reported;
* inspect logs for accidental secret leakage;
* inspect generated artifacts for misleading status reporting.

Where a complete environment is unavailable, execute everything possible and explicitly report the remaining unverified scope.

# REGRESSION VALIDATION

Before completion, ensure the advanced QA implementation does not break:

* existing unit tests;
* existing integration tests;
* existing contract tests;
* existing web tests;
* existing mobile tests;
* existing infrastructure validation;
* existing development workflows.

Fix regressions caused by the QA implementation itself.

Do not silently modify unrelated tests simply to accommodate new behavior.

# DOCUMENTATION AND PORTABLE HANDOFF

Ensure the resulting QA artifacts are portable and understandable by another engineering environment.

Document:

* test architecture;
* execution commands;
* dependencies;
* environment assumptions;
* data models;
* scenario definitions;
* CI entry points;
* release gates;
* performance methodology;
* resilience methodology;
* security coverage;
* known gaps;
* evidence locations;
* limitations.

The documentation must enable another engineer or integration environment to understand and execute the QA system without relying on this conversation.

# IMPLEMENTATION REPORT

At the end, provide an implementation report that clearly states:

* repository areas inspected;
* QA capabilities implemented;
* files created;
* files modified;
* E2E scenarios implemented;
* performance workloads implemented;
* resilience scenarios implemented;
* security regression coverage implemented;
* privacy regression coverage implemented;
* release qualification checks implemented;
* CI integrations implemented;
* test-data infrastructure implemented;
* commands executed;
* test results;
* performance results where executed;
* security-scan results where executed;
* blocked or unavailable validations;
* environmental limitations;
* application fixes made solely for testability;
* known remaining QA gaps.

Do not claim successful execution for tests that were not actually run.

# DEFINITION OF DONE

This prompt is complete only when all applicable requirements below are satisfied:

* Advanced QA capabilities are implemented as executable repository artifacts.
* Critical cross-platform E2E journeys are covered.
* Release qualification is repeatable and documented.
* Performance workloads exist for critical system paths.
* Load, stress, and soak mechanisms exist where technically supported.
* Event and queue failure cases are tested.
* Media pipeline failure cases are tested.
* Security regression coverage exists.
* Privacy regression coverage exists.
* Concurrency and race-sensitive operations are exercised.
* Dependency failure behavior is tested.
* Resilience and recovery behavior are tested where the environment supports it.
* Test data is deterministic, isolated, and reusable.
* CI integrates appropriate advanced QA gates.
* Test results distinguish pass, fail, skip, and environment-blocked execution.
* Test artifacts are useful for diagnosis.
* No secrets are embedded in QA code or reports.
* No production data is required.
* No false passes are introduced.
* Existing relevant test suites remain functional.
* Documentation reflects the actual implemented system.
* Commands and validation results are reproducible.
* Portable QA handoff artifacts exist.
* The implementation report accurately describes completed and unverified work.

# FINAL SCOPE REMINDER

Implement **only the current prompt's scope**.

Do not expand this workstream into unrelated product development, architectural redesign, or an unplanned additional project phase.

Do not assume unavailable environments, credentials, providers, devices, or cloud resources.

Do not substitute claims for evidence.

Implement the advanced QA system, execute the validations that are actually possible, preserve test integrity, document limitations precisely, and finish with the required implementation report and Definition of Done.
