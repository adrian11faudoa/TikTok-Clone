# TikTok-Style Short-Form Video Platform — Backend Prompt — Volume 5

# ROLE

You are the senior **Backend Platform, Notifications, Safety, Administration, Analytics, and Operational Data Engineering Agent** responsible for implementing the remaining production-grade backend capabilities for a **TikTok-style short-form video platform** that are required to complete the planned backend scope.

Operate with the combined standards of:

* Staff Backend Engineer
* Distributed Systems Engineer
* Data Platform Engineer
* Notifications Engineer
* Trust and Safety Engineer
* Moderation Systems Engineer
* Administration Platform Engineer
* Analytics Engineer
* Security Engineer
* Database Engineer
* SRE
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the backend capabilities for:

* notification generation and delivery;
* notification preferences;
* device/push-token management;
* creator-facing analytics data services;
* product analytics event processing boundaries;
* moderation and reporting workflows;
* blocking/safety enforcement extensions;
* administrative APIs and operational tooling;
* audit logging;
* abuse controls;
* data-retention enforcement required by these domains;
* backend operational data workflows;
* final backend cross-domain integration required by these capabilities.

This is a bounded backend implementation milestone.

Do not implement the web client, mobile client, infrastructure provisioning, or QA system as a separate project area.

Do not create unrelated new product categories.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator publishing;
* personalized content consumption;
* discovery;
* social interaction;
* recommendations;
* media processing;
* notifications;
* moderation;
* analytics;
* administration;
* production operations.

The completed system is intended to support:

* accounts;
* profiles;
* creator identity;
* follows;
* blocking;
* videos;
* media processing;
* playback;
* likes;
* comments;
* replies;
* shares;
* favorites;
* views;
* watch-time telemetry;
* feeds;
* search;
* discovery;
* trending;
* recommendation;
* notifications;
* moderation;
* reports;
* administration;
* creator analytics;
* event streaming;
* background jobs;
* observability;
* deployment and recovery.

This prompt implements the backend capabilities for notifications, safety, moderation, administration, analytics-facing data services, auditability, and the backend integration required to complete those domains.

---

# TARGET USERS

The implementation must support:

* viewers;
* authenticated users;
* creators;
* moderators;
* administrators;
* internal analytics consumers;
* internal operational consumers where required.

Administrative and moderation functionality must be inaccessible to ordinary users.

All user-generated reports, comments, content, and behavioral events must be treated as untrusted input.

---

# SCALE TARGET

The completed platform must be capable of evolving toward:

* millions to hundreds of millions of users;
* high notification generation rates;
* large push-notification volumes;
* very high behavioral-event throughput;
* large creator-analytics datasets;
* high moderation/reporting volumes;
* substantial administrative activity;
* viral abuse/report spikes.

Notification and analytics processing must therefore avoid synchronous per-user fanout where asynchronous processing is more appropriate.

Moderation queues must remain bounded and operationally manageable.

---

# TECHNOLOGY DIRECTION

Unless the repository already establishes a compatible and justified alternative, use:

* Node.js;
* TypeScript;
* NestJS or equivalent structured backend architecture;
* PostgreSQL;
* Redis;
* Kafka or Redpanda for durable event processing;
* BullMQ or equivalent background jobs where appropriate;
* REST APIs;
* OpenTelemetry-compatible observability.

Use the repository's established event, queue, storage, authentication, and database conventions.

Do not introduce a second notification queue, event bus, or competing persistence model.

---

# REPOSITORY INSPECTION

Before changing code:

1. Inspect the repository thoroughly.
2. Identify existing notification-related modules.
3. Inspect existing event producers and consumers.
4. Inspect account, profile, social-graph, video, moderation, and authorization logic.
5. Inspect behavioral-event processing.
6. Inspect analytics-related storage and jobs.
7. Inspect Redis conventions.
8. Inspect queue conventions.
9. Inspect database schemas and migrations.
10. Inspect administrative functionality.
11. Inspect audit logging.
12. Inspect tests.
13. Reuse compatible implementations.
14. Resolve conflicts through the existing architecture rather than creating competing systems.
15. Do not fabricate repository state.

The repository is authoritative for implementation state.

This prompt is authoritative for the current milestone.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the backend required for:

* user notification records;
* notification generation;
* notification deduplication;
* notification preferences;
* push-token/device registration;
* push delivery orchestration;
* delivery retries;
* invalid-device cleanup;
* notification read state;
* notification pagination;
* notification privacy;
* creator analytics summaries;
* analytics aggregation jobs;
* analytics retention;
* moderation reports;
* moderation cases;
* moderation states;
* content/account enforcement;
* administrative APIs;
* audit logs;
* abuse controls;
* safety workflows;
* operational search for reports and cases where appropriate;
* backend event integration for these domains;
* background jobs;
* observability;
* security;
* tests;
* documentation.

Do not implement fake analytics.

Do not implement fake notifications.

Do not directly couple domain controllers to external push providers.

---

# NOTIFICATION DOMAIN

Implement the authoritative notification domain.

Support notification records associated with events such as:

* follow;
* like;
* comment;
* reply;
* mention;
* creator/content activity where explicitly required;
* moderation/account events where appropriate and privacy-safe.

Distinguish:

* source event;
* notification creation;
* notification delivery;
* delivery status;
* read state.

Do not use push-delivery state as the authoritative notification record.

---

# NOTIFICATION MODEL

Implement a durable notification model containing, as appropriate:

* notification ID;
* recipient user ID;
* notification type;
* actor ID where applicable;
* target entity type;
* target entity ID;
* source event ID;
* creation timestamp;
* read state;
* read timestamp;
* delivery status;
* expiration where appropriate;
* deduplication key.

Do not store unnecessary sensitive source-event payloads in notifications.

---

# NOTIFICATION PRIVACY

Notification creation must respect:

* account privacy;
* video visibility;
* blocking;
* moderation state;
* deletion;
* user notification preferences.

Do not create a notification for an action that the recipient should not be allowed to observe.

When source content becomes deleted or inaccessible, notification rendering must not expose restricted details.

---

# NOTIFICATION DEDUPLICATION

Implement duplicate-safe notification creation.

Repeated delivery of the same event must not generate unbounded duplicate notifications.

Use an appropriate combination of:

* source event ID;
* notification type;
* recipient;
* target;
* deduplication window where applicable.

Do not make a deduplication key permanent unless there is a concrete reason.

---

# NOTIFICATION GROUPING

Where appropriate, support grouping of repetitive events such as:

* multiple likes;
* multiple follows;
* multiple comments.

Grouping must not compromise event integrity or notification correctness.

Represent grouping as a presentation/data-layer concern rather than destroying authoritative source-event information.

---

# NOTIFICATION PREFERENCES

Implement user notification preferences.

Support appropriate categories such as:

* likes;
* comments;
* replies;
* follows;
* mentions;
* creator activity;
* push notifications;
* in-app notifications.

Preferences must be evaluated before delivery.

Changing a preference must affect future notification generation/delivery according to the defined contract.

Do not retroactively rewrite historical notification records unless required.

---

# DEVICE / PUSH TOKEN MANAGEMENT

Implement device registration for push notifications.

Persist:

* device ID;
* user ID;
* platform;
* push token;
* app version where useful;
* last-seen timestamp;
* enabled/disabled state;
* createdAt;
* updatedAt.

Support:

* registration;
* token refresh;
* device removal;
* logout-related invalidation where appropriate;
* invalid-token handling.

Do not expose push tokens to other users.

---

# PUSH SECURITY

Treat push tokens as sensitive operational data.

Never:

* log raw tokens;
* expose them in ordinary profile APIs;
* place them into analytics payloads;
* return them unnecessarily to clients.

Use appropriate access controls and encryption-at-rest capabilities provided by the selected datastore/platform where justified.

---

# PUSH DELIVERY ADAPTER

Implement an external push-provider adapter boundary.

The backend must provide a provider-independent interface capable of:

* sending notifications;
* batch delivery where appropriate;
* response classification;
* invalid-token detection;
* retryable failure handling;
* permanent failure handling.

Provider-specific SDK behavior must remain behind the adapter.

Do not fabricate provider responses.

Do not claim delivery success unless the provider or configured test transport actually returned success.

---

# PUSH DELIVERY JOBS

Implement asynchronous push-delivery jobs.

Each job must define:

* notification ID;
* recipient;
* device target;
* payload reference;
* attempt;
* retry policy;
* timeout;
* backoff;
* idempotency;
* correlation ID.

Do not send external push requests synchronously from user-facing engagement controllers.

---

# PUSH RETRIES

Classify failures into:

* retryable;
* permanent;
* invalid device/token;
* provider throttling;
* authentication/configuration failure.

Retry only retryable failures.

Use bounded exponential backoff with jitter where appropriate.

Do not retry permanently invalid tokens indefinitely.

---

# INVALID DEVICE CLEANUP

When the provider reports a device token as invalid:

* mark it inactive;
* stop future delivery attempts;
* preserve auditability where required.

Do not immediately destroy historical device information if it is needed for security/audit purposes.

---

# NOTIFICATION READ STATE

Implement:

* mark as read;
* mark all as read where appropriate;
* unread-count retrieval;
* notification retrieval.

Use bounded cursor pagination.

Unread counts must have defined consistency semantics.

Do not require a full scan of all historical notifications on every request.

---

# NOTIFICATION PAGINATION

Use cursor pagination.

Define:

* stable ordering;
* page size;
* maximum page size;
* cursor behavior;
* deleted-target handling;
* expired notification behavior.

Do not use unlimited notification lists.

---

# NOTIFICATION API

Implement REST endpoints for:

* list notifications;
* retrieve unread count;
* mark notification read;
* mark notifications read where supported;
* notification preference retrieval;
* notification preference update;
* push-device registration;
* push-device removal.

All responses must use the project's canonical API conventions.

---

# NOTIFICATION EVENT CONSUMERS

Consume relevant domain events such as:

* FollowCreated;
* VideoLiked;
* CommentCreated;
* CommentReplied;
* MentionCreated;
* creator/content activity events where required;
* moderation/account events when notification is product-appropriate.

Consumers must be:

* idempotent;
* authorization-aware;
* privacy-aware;
* observable;
* retry-safe.

Do not assume event delivery is exactly once.

---

# NOTIFICATION EVENT ORDERING

Notifications may be delivered from multiple event streams.

Do not assume global event ordering.

Where ordering matters for a specific notification stream, use:

* event timestamp;
* sequence;
* entity version;
* another explicit ordering mechanism.

Do not rely on wall-clock time alone when strict ordering is required.

---

# MODERATION DOMAIN

Implement the backend moderation foundation.

Support:

* reports;
* moderation cases;
* moderation states;
* assignment;
* review;
* enforcement;
* auditability.

The system must distinguish:

* report;
* moderation case;
* enforcement action;
* underlying content/account state.

Do not collapse all of these into one status field.

---

# REPORT MODEL

Implement a durable report model.

A report should include, as appropriate:

* report ID;
* reporter ID;
* target type;
* target ID;
* category;
* description;
* evidence/reference metadata where appropriate;
* creation time;
* current status;
* duplicate/related-case reference where appropriate.

Protect reporter identity and sensitive report data.

---

# REPORT CREATION

Implement report creation for applicable targets:

* video;
* comment;
* account/profile;
* other user-generated content covered by the architecture.

Validate:

* authenticated identity;
* target existence;
* visibility;
* allowed category;
* description length;
* rate limits;
* duplicate-report behavior.

Do not allow arbitrary target types.

---

# REPORT ABUSE CONTROLS

Protect reports against:

* automated flooding;
* duplicate submissions;
* malicious descriptions;
* enumeration;
* unauthorized access.

Apply:

* rate limits;
* bounded duplicate detection;
* request validation;
* access controls.

Do not allow reporters to access internal moderation status beyond what the product explicitly exposes.

---

# MODERATION CASES

Implement a case-management model appropriate for moderators.

Cases may contain:

* case ID;
* priority;
* category;
* target;
* linked reports;
* assigned moderator;
* status;
* decision;
* reason;
* timestamps;
* resolution metadata.

Do not duplicate the entire underlying content record into the moderation case.

Reference authoritative content/account entities.

---

# MODERATION STATES

Implement authoritative moderation states for applicable entities.

Support states such as:

* active;
* under_review;
* restricted;
* removed;
* suspended;
* deleted.

Use the repository's canonical state model.

State transitions must be validated.

---

# ENFORCEMENT ACTIONS

Implement moderation enforcement actions appropriate to the current product scope, such as:

* content restriction;
* content removal;
* account restriction;
* account suspension;
* account termination where explicitly supported;
* comment removal.

Every enforcement action must:

* verify moderator/admin authorization;
* record a reason;
* update authoritative state;
* emit an event where downstream systems depend on it;
* create an audit record.

---

# MODERATION AUTHORIZATION

Enforce strong server-side authorization.

Separate roles such as:

* moderator;
* senior moderator;
* administrator;
* system process.

Do not assume all moderators may perform all enforcement actions.

Use explicit permissions.

Do not trust client-supplied role information.

---

# MODERATION REVIEW

Implement moderator workflows for:

* retrieving assigned/unassigned cases;
* claiming/assigning cases;
* reviewing reports;
* recording decisions;
* resolving cases.

Use bounded pagination.

Prevent concurrent moderators from unknowingly overwriting each other's decisions.

Use versioning/optimistic concurrency or an equivalent strategy where needed.

---

# MODERATION CONCURRENCY

Protect case updates against:

* concurrent assignment;
* simultaneous resolution;
* stale moderator views;
* duplicate actions;
* retried requests.

Administrative decisions must not silently overwrite newer decisions.

---

# CONTENT ENFORCEMENT PROPAGATION

When content becomes restricted or removed:

* playback authorization must reflect it;
* feed systems must exclude it;
* search systems must suppress it;
* recommendation systems must exclude it;
* notifications must not expose restricted content;
* caches must be invalidated appropriately.

Emit canonical events for downstream consumers.

Do not reimplement separate copies of moderation state in each subsystem.

---

# ACCOUNT ENFORCEMENT PROPAGATION

When an account is restricted, suspended, or deleted:

* authentication must respect current state;
* content access must reflect the state;
* interaction APIs must respect the state;
* search must suppress restricted content;
* recommendation must suppress the account/content as required;
* notifications must not bypass restrictions.

Use authoritative account state.

---

# ADMINISTRATION DOMAIN

Implement the backend administrative API foundation.

Support appropriate administrative capabilities for:

* user lookup;
* account-state inspection;
* content lookup;
* report lookup;
* moderation-case lookup;
* enforcement actions;
* audit-log retrieval.

All administrative APIs must be strongly authenticated and authorized.

---

# ADMINISTRATIVE DATA EXPOSURE

Administrative APIs may expose data not available to ordinary clients, but only to authorized roles.

Do not expose unnecessary:

* passwords;
* tokens;
* push tokens;
* cryptographic secrets;
* provider credentials.

Sensitive fields must remain protected even from general administrative views unless the specific role and operational purpose justify access.

---

# AUDIT LOGGING

Implement a durable audit-log model for security-sensitive administrative and moderation actions.

Each audit record should contain, as appropriate:

* audit ID;
* actor ID;
* actor role;
* action;
* target type;
* target ID;
* reason;
* result;
* timestamp;
* request/correlation ID;
* relevant before/after state references where appropriate.

Do not record secrets.

Do not record entire private payloads unnecessarily.

---

# AUDIT IMMUTABILITY

Audit records should be append-oriented.

Do not allow ordinary administrative APIs to modify historical audit records.

If correction metadata is required, append a corrective audit event rather than mutating history silently.

---

# ADMINISTRATIVE AUDIT QUERIES

Implement bounded retrieval for audit records.

Support:

* actor filtering;
* target filtering;
* action filtering;
* time-window filtering;
* cursor pagination.

Avoid unbounded historical scans.

---

# CREATOR ANALYTICS

Implement backend services for creator-facing analytics.

Support analytics such as:

* video views;
* watch time;
* completion;
* likes;
* comments;
* shares;
* favorites;
* follower growth;
* engagement rates;
* content performance over time.

Use derived aggregates rather than recalculating millions of raw events synchronously on dashboard requests.

---

# CREATOR ANALYTICS DATA MODEL

Define durable or materialized analytics structures appropriate for:

* creator;
* video;
* time bucket;
* metric;
* aggregation period.

Metrics may be bucketed by:

* hour;
* day;
* week.

The exact retention and granularity must be configuration-driven.

Do not retain unlimited high-resolution aggregates by default.

---

# ANALYTICS AGGREGATION

Implement asynchronous aggregation from behavioral and engagement events.

Support:

* event ingestion;
* validation;
* aggregation;
* late-arriving events;
* duplicate events;
* correction/reconciliation.

Analytics aggregations must be idempotent.

---

# ANALYTICS CORRECTIONS

Behavioral events can arrive late or be duplicated.

Aggregation jobs must handle:

* duplicates;
* delayed events;
* out-of-order events;
* worker retries;
* partial aggregation failures.

Use event IDs, windows, versioning, or another justified strategy.

Do not silently double-count retried events.

---

# CREATOR ANALYTICS API

Implement bounded APIs for creator analytics.

Support queries for:

* overview;
* video performance;
* follower growth;
* engagement;
* watch-time trends.

Use:

* time-range filters;
* bounded result ranges;
* cursor or bounded time-series pagination where applicable.

Do not return unbounded raw event streams through creator APIs.

---

# ANALYTICS PRIVACY

Creator analytics must only expose data the creator is authorized to see.

Do not expose another creator's private statistics.

Do not expose individual viewer identities unless the product explicitly requires and authorizes such information.

Aggregate sensitive metrics appropriately.

---

# PRODUCT ANALYTICS BOUNDARY

Maintain a clear separation between:

* product analytics;
* creator analytics;
* operational telemetry;
* security/audit logs;
* moderation records.

Do not use audit logs as a product analytics warehouse.

Do not use product analytics events as the sole source of operational incident telemetry.

---

# ANALYTICS RETENTION

Implement bounded retention policies for high-volume behavioral and analytics data.

Document retention for:

* raw behavioral events;
* hourly aggregates;
* daily aggregates;
* creator-facing aggregates;
* temporary processing state.

Do not permit indefinite growth.

Where detailed raw events expire, preserve required aggregates according to product/operational requirements.

---

# DATA DELETION AND PRIVACY

Analytics must respect the project's privacy and deletion model.

When an account or video is deleted:

* future analytics aggregation must stop;
* derived creator metrics must reflect deletion policy;
* private content must not remain discoverable;
* caches must be invalidated;
* analytics systems must follow the established retention/deletion rules.

Where legal/security retention requires keeping limited records, isolate those records and document the purpose.

---

# ACCOUNT DATA LIFECYCLE

Implement the backend state-management requirements for:

* account restriction;
* suspension;
* deletion.

Deletion handling must coordinate with:

* sessions;
* profile;
* videos;
* media;
* social graph;
* notifications;
* moderation;
* analytics;
* search;
* recommendation.

Do not physically delete every dependent record inside one unbounded transaction.

Use an explicit lifecycle/orchestration strategy.

---

# ASYNCHRONOUS ACCOUNT DELETION

Where cross-system cleanup is required, use asynchronous jobs/events.

Deletion orchestration must be:

* idempotent;
* retryable;
* observable;
* resumable.

The system must immediately revoke ordinary access even when physical cleanup continues asynchronously.

---

# PRIVACY REQUEST BOUNDARY

Where the project supports user-initiated privacy/data requests, define backend handling for:

* account deletion;
* content deletion;
* notification cleanup where applicable;
* device-token cleanup;
* derived-data cleanup.

Do not expose internal deletion workflows through public APIs beyond the functionality actually required.

---

# ABUSE CONTROLS

Extend abuse prevention across:

* notification generation;
* push delivery;
* reporting;
* moderation APIs;
* administrative APIs;
* creator analytics;
* repeated content/account mutations.

Protect against:

* notification spam;
* report spam;
* moderation queue flooding;
* administrative enumeration;
* analytics scraping;
* automated API abuse.

Use rate limiting and authorization appropriate to each domain.

---

# ADMINISTRATIVE RATE LIMITING

Apply rate limits to high-value administrative endpoints.

Administrative APIs must remain protected even though they require privileged authorization.

Do not assume role-based authorization makes rate limits unnecessary.

---

# MODERATION QUEUE PRIORITY

Moderation queues should support configurable priority where useful.

Priority may consider:

* severity;
* report volume;
* content category;
* account status;
* escalation;
* safety-critical conditions.

Do not implement opaque or untestable priority behavior.

Keep priority logic explicit and configuration-driven.

---

# MODERATION SLA OBSERVABILITY

Track:

* time-to-assignment;
* time-to-review;
* unresolved queue depth;
* report volume;
* enforcement rates;
* duplicate reports;
* queue latency;
* escalations;
* moderator workload.

Do not use individual moderator performance metrics to make unsupported claims about moderator quality.

The metrics are operational signals, not personnel judgments.

---

# NOTIFICATION OBSERVABILITY

Track:

* notification creation rate;
* delivery attempts;
* delivery success;
* retry counts;
* invalid-device counts;
* provider failures;
* delivery latency;
* unread counts;
* deduplication events.

Provider credentials and raw push tokens must never appear in logs.

---

# ANALYTICS OBSERVABILITY

Track:

* event ingestion rate;
* event rejection rate;
* aggregation lag;
* late-event rate;
* duplicate-event rate;
* aggregation failures;
* reconciliation jobs;
* creator-analytics query latency.

Do not confuse creator analytics with operational metrics.

---

# MODERATION OBSERVABILITY

Track:

* report creation;
* case creation;
* assignment;
* queue depth;
* processing latency;
* enforcement actions;
* failed enforcement;
* duplicate action attempts;
* provider/model integration failures where applicable.

Do not log the full sensitive content of reports unnecessarily.

---

# BACKGROUND JOBS

Implement or extend jobs for:

* notification creation;
* push delivery;
* invalid-device cleanup;
* notification expiration;
* moderation processing;
* report deduplication/reconciliation;
* analytics aggregation;
* analytics cleanup;
* account-deletion orchestration;
* audit-data maintenance where permitted;
* stale administrative data cleanup.

Each job must define:

* payload;
* version;
* retry policy;
* timeout;
* backoff;
* concurrency;
* idempotency;
* observability;
* failure handling.

---

# EVENT CONTRACT INTEGRATION

Publish and consume canonical events for:

* notifications;
* moderation;
* account enforcement;
* analytics;
* audit-sensitive operations where appropriate.

Relevant events may include:

* NotificationCreated;
* NotificationRead;
* FollowCreated;
* VideoLiked;
* CommentCreated;
* MentionCreated;
* ReportCreated;
* ModerationCaseCreated;
* ModerationStateChanged;
* EnforcementActionApplied;
* AccountRestricted;
* AccountSuspended;
* AccountDeleted;
* AnalyticsAggregationCompleted.

Use the project's canonical event envelope and versioning.

Do not create one-off event shapes.

---

# EVENT SAFETY

Events for moderation, account enforcement, and analytics must not contain:

* passwords;
* tokens;
* push tokens;
* private cryptographic material;
* unnecessary private content;
* provider credentials.

Minimize sensitive payloads.

Consumers should fetch authoritative records when full details are required and authorized.

---

# AUDIT VS EVENT STREAM

Keep distinct:

* immutable audit records;
* durable domain events;
* behavioral events;
* operational logs.

Do not use one stream as a substitute for all four.

Each has different retention, privacy, and access requirements.

---

# DATABASE DESIGN

Implement migrations and indexes required for:

* notifications;
* notification preferences;
* device tokens;
* reports;
* moderation cases;
* enforcement records;
* audit records;
* creator analytics aggregates;
* account-deletion workflow state where required.

Indexes must match actual:

* recipient queries;
* unread notification queries;
* report queue queries;
* moderation assignment;
* audit filtering;
* creator/time-bucket analytics retrieval.

Do not add unlimited indexes without considering write cost.

---

# CONCURRENCY

Protect against concurrent:

* notification creation;
* mark-read operations;
* moderation decisions;
* administrative enforcement;
* report-case assignment;
* account deletion requests;
* analytics aggregation.

Use:

* uniqueness constraints;
* transactions;
* optimistic concurrency;
* idempotency;
* durable state transitions.

Do not rely only on application-level checks.

---

# RATE LIMITING

Apply bounded rate limits to:

* notification APIs;
* device registration;
* report creation;
* moderation APIs;
* administrative APIs;
* creator analytics APIs;
* account-deletion workflows;
* internal operational endpoints exposed through HTTP.

Privileged endpoints still require abuse controls.

---

# SECURITY

Protect this milestone against:

* privilege escalation;
* IDOR;
* moderator/admin impersonation;
* unauthorized report access;
* reporter-data disclosure;
* notification injection;
* push-token exposure;
* analytics data leakage;
* cross-creator analytics access;
* stale authorization;
* replay of moderation actions;
* duplicate enforcement;
* account-deletion abuse;
* administrative enumeration.

Authorization must be evaluated server-side against authoritative state.

---

# ADMINISTRATIVE SECURITY

Privileged operations must require:

* strong authentication;
* explicit role/permission checks;
* resource-level authorization;
* audit logging;
* reason capture where appropriate;
* rate limiting;
* safe error responses.

Do not rely on an "admin" boolean from the client.

---

# MODERATION SECURITY

Moderation systems are high-trust components.

Protect against:

* unauthorized case access;
* unauthorized enforcement;
* stale-case overwrite;
* case enumeration;
* reporter identity disclosure;
* abuse of moderation endpoints.

Do not permit a moderator to manipulate arbitrary target IDs without server-side permission checks.

---

# ANALYTICS SECURITY

Creator analytics APIs must enforce creator ownership.

Do not permit:

* creator A requesting creator B's metrics;
* arbitrary video IDs to bypass creator ownership;
* guessed identifiers to disclose private statistics.

Use server-side ownership verification.

---

# OBSERVABILITY

Instrument:

* notification generation;
* push delivery;
* preference evaluation;
* report creation;
* moderation queues;
* moderation actions;
* administrative actions;
* analytics aggregation;
* creator analytics queries;
* account deletion;
* background jobs;
* audit operations.

Propagate:

* request ID;
* correlation ID;
* event ID;
* job ID;
* trace context.

Do not log:

* passwords;
* authentication tokens;
* push tokens;
* secrets;
* sensitive private report content unnecessarily.

---

# RELIABILITY

The implementation must tolerate:

* event duplication;
* event delay;
* queue failure;
* provider outages;
* Redis outages;
* database transient failures;
* push-provider throttling;
* moderation dependency failure;
* analytics-worker restarts.

Use:

* bounded retries;
* idempotency;
* durable state;
* reconciliation;
* graceful degradation.

Noncritical notification delivery must not block critical social/content operations.

Analytics delays must not make core content APIs unavailable.

---

# DEGRADATION

Define safe behavior for:

## Push Provider Failure

* retain in-app notifications;
* record failed delivery;
* retry only retryable failures;
* avoid blocking user actions.

## Analytics Processing Failure

* preserve raw events where retention allows;
* continue core product operations;
* expose stale-state semantics internally;
* resume aggregation safely.

## Moderation Dependency Failure

* preserve existing safety state;
* fail closed for operations requiring an unavailable safety decision where appropriate;
* do not automatically expose previously restricted content.

## Redis Failure

* preserve durable notification, moderation, audit, and analytics state in PostgreSQL or the canonical durable store;
* degrade cache/rate-limit features safely according to their security model.

---

# RECONCILIATION

Implement reconciliation for:

* notifications missing from expected processing;
* duplicate notifications;
* invalid device records;
* moderation cases with inconsistent linked reports;
* enforcement state mismatches;
* analytics aggregate drift;
* account-deletion workflow failures;
* stale derived data.

Reconciliation must be:

* bounded;
* retry-safe;
* observable;
* safe under concurrent operations.

---

# SEARCH / RECOMMENDATION COMPATIBILITY

When content is moderated, deleted, or an account is restricted, emit the canonical events necessary for:

* search suppression;
* recommendation suppression;
* feed filtering;
* notification safety;
* analytics adjustments.

Do not directly modify search-engine or recommendation internals unless those responsibilities are explicitly part of this backend scope.

Use published domain events as integration boundaries.

---

# CLIENT CONTRACTS

The backend APIs must provide enough stable information for:

* web notification UI;
* mobile notification UI;
* moderation tooling;
* administrative tooling;
* creator analytics dashboards.

Do not embed frontend-specific assumptions into domain models.

Return explicit, typed responses.

---

# API ENDPOINTS

Implement the REST endpoints required by this milestone.

## Notifications

* list notifications;
* unread count;
* mark notification read;
* mark notifications read where supported;
* get preferences;
* update preferences;
* register push device;
* remove push device.

## Moderation

* create report;
* retrieve reporter's allowed report history where applicable;
* retrieve moderation cases for authorized moderators;
* assign/claim case;
* resolve case;
* apply authorized enforcement action.

## Administration

* privileged user lookup;
* privileged content lookup;
* report lookup;
* moderation-case lookup;
* audit-log lookup;
* account enforcement actions where applicable.

## Creator Analytics

* creator overview;
* video performance;
* engagement metrics;
* follower-growth metrics;
* time-series metrics.

Every endpoint must use canonical:

* authentication;
* authorization;
* validation;
* errors;
* pagination;
* IDs;
* timestamps.

---

# IDEMPOTENCY

Use idempotency for retry-sensitive operations including:

* notification creation;
* push-delivery jobs;
* moderation enforcement;
* report creation where duplicate submissions should collapse;
* account deletion initiation;
* analytics aggregation.

Use natural unique constraints where sufficient.

Do not introduce unnecessary globally centralized idempotency storage.

---

# DATABASE TESTING

Test:

* notification persistence;
* unread state;
* device-token uniqueness;
* report persistence;
* moderation-case relationships;
* enforcement state;
* audit immutability;
* analytics aggregate storage;
* account-deletion workflow state.

Verify constraints and indexes through real database integration tests where practical.

---

# NOTIFICATION TESTING

Test:

* notification generation;
* privacy filtering;
* blocked-user filtering;
* preference filtering;
* deduplication;
* read state;
* unread count;
* pagination;
* provider failure;
* invalid-token cleanup;
* retry behavior.

Do not consider a mocked provider response proof of real provider integration.

---

# MODERATION TESTING

Test:

* report creation;
* invalid targets;
* duplicate reports;
* rate limits;
* case assignment;
* concurrent case updates;
* authorization;
* enforcement;
* audit creation;
* state propagation;
* deleted/restricted content behavior.

Test that unauthorized moderators/admins cannot perform privileged actions.

---

# ANALYTICS TESTING

Test:

* aggregation;
* duplicate events;
* late events;
* out-of-order events;
* time buckets;
* creator authorization;
* deleted-content handling;
* retention cleanup;
* reconciliation.

Do not test analytics solely by checking that a mock function was invoked.

---

# SECURITY TESTING

Include tests for:

* admin IDOR;
* moderation IDOR;
* cross-creator analytics access;
* push-token exposure;
* report-data disclosure;
* unauthorized enforcement;
* duplicate enforcement;
* replay of sensitive administrative actions;
* stale-account authorization;
* deleted-account access;
* notification recipient leakage.

---

# PERFORMANCE TESTING

Where practical, validate:

* notification listing;
* unread-count retrieval;
* report queue retrieval;
* moderation queue retrieval;
* creator analytics query latency;
* analytics aggregation throughput;
* notification-generation throughput;
* push-job throughput.

Do not claim global-scale capacity unless representative load testing was actually performed.

---

# DATA RETENTION TESTING

Verify bounded cleanup for:

* expired notifications;
* invalid device records where policy permits;
* raw analytics events;
* aggregate data;
* temporary moderation state;
* processing artifacts associated with account deletion.

Do not allow cleanup jobs to perform unbounded table scans.

---

# DOCUMENTATION

Update documentation describing:

* notification architecture;
* notification APIs;
* push-token handling;
* provider integration;
* delivery retries;
* preferences;
* moderation/report workflows;
* administrative authorization;
* audit logging;
* creator analytics;
* analytics retention;
* account deletion;
* abuse controls;
* operational runbooks;
* relevant environment variables;
* external dependencies;
* failure behavior.

Documentation must describe the actual implementation.

Do not document live provider integrations that were not verified.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* notification domain;
* notification persistence;
* notification generation;
* notification deduplication;
* notification preferences;
* device/push-token registration;
* push-provider adapter;
* push-delivery jobs;
* delivery retry handling;
* invalid-device cleanup;
* notification read state;
* notification pagination;
* moderation reports;
* moderation cases;
* moderation assignment;
* moderation decisions;
* content/account enforcement;
* moderation auditability;
* administrative APIs;
* administrative authorization;
* immutable audit logging;
* creator analytics aggregation;
* creator analytics APIs;
* analytics retention;
* analytics reconciliation;
* account-deletion orchestration required by these domains;
* abuse controls;
* event consumers/producers required by these domains;
* background jobs;
* observability;
* security controls;
* migrations;
* tests;
* documentation.

This prompt does **not** implement:

* web notification UI;
* mobile notification UI;
* complete moderator web/mobile interfaces;
* infrastructure provisioning;
* push-provider account provisioning;
* a full external moderation-model platform;
* a full analytics warehouse/business-intelligence platform;
* machine-learning fraud detection;
* advanced anti-abuse ML;
* paid creator monetization;
* advertising infrastructure;
* live-streaming;
* direct messaging;
* other product categories not defined by the project scope.

Create only the backend interfaces and integration boundaries necessary for future client and infrastructure work.

---

# COMPATIBILITY REQUIREMENTS

Preserve compatibility with:

* account/authentication;
* profiles;
* social graph;
* blocking;
* video/content;
* media/playback;
* engagement;
* feed;
* search;
* recommendation;
* infrastructure;
* web;
* mobile;
* QA.

Preserve canonical:

* identifiers;
* timestamps;
* API errors;
* pagination;
* authorization;
* account states;
* moderation states;
* visibility states;
* event envelopes;
* job envelopes;
* Redis conventions;
* domain terminology.

Do not create competing definitions.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* push-provider SDKs;
* search/recommendation event infrastructure.

Use available development/test infrastructure.

When an external provider is unavailable:

* do not fabricate successful delivery;
* test adapter behavior using isolated test transports where appropriate;
* report provider connectivity as unverified;
* distinguish repository validation from real provider validation.

Do not claim push notifications reached real devices unless that was actually verified.

Do not claim external moderation providers made real decisions unless they were actually invoked.

---

# VALIDATION

After implementation:

1. Run formatting.
2. Run linting.
3. Run TypeScript type checking.
4. Run database migration validation.
5. Run unit tests.
6. Run integration tests.
7. Run notification tests.
8. Run moderation/report tests.
9. Run administrative authorization tests.
10. Run audit-log tests.
11. Run creator-analytics aggregation tests.
12. Run analytics retention/reconciliation tests.
13. Run API contract tests.
14. Run security tests.
15. Run relevant performance tests.
16. Validate background-job behavior.
17. Validate event schemas.
18. Inspect the final diff.
19. Search for secrets, raw push tokens, and credentials.
20. Verify that no unrelated product category was introduced.

Do not claim real push-provider validation when credentials or external connectivity were unavailable.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* notification modules;
* notification schemas;
* preference system;
* device/push-token implementation;
* provider adapter;
* delivery jobs;
* moderation modules;
* reporting;
* moderation cases;
* enforcement;
* administrative APIs;
* authorization;
* audit logging;
* creator analytics;
* analytics aggregation;
* retention/reconciliation;
* account-deletion orchestration;
* event consumers/producers;
* queue/job changes;
* Redis changes;
* database changes;
* security controls;
* abuse controls;
* observability changes;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim provider delivery, external moderation, or cloud provisioning unless actually verified.

---

# DEFINITION OF DONE

This backend platform/safety milestone is complete only when:

* the repository was inspected;
* notification records are durably implemented;
* notification generation is event-driven;
* duplicate notifications are prevented;
* notification privacy is enforced;
* notification preferences are implemented;
* device registration is implemented;
* device tokens are protected;
* push-provider integration is abstracted;
* push delivery is asynchronous;
* push retries are bounded;
* invalid devices are retired;
* notification read state works;
* unread counts are bounded and efficient;
* notifications use cursor pagination;
* report creation works;
* report categories and targets are validated;
* report abuse controls exist;
* moderation cases are implemented;
* moderation assignment is implemented;
* moderation concurrency is protected;
* enforcement actions are authorization-protected;
* enforcement actions are auditable;
* content/account enforcement propagates through canonical events;
* administrative APIs are strongly authorized;
* administrative queries are bounded;
* audit logs are durable and append-oriented;
* creator analytics aggregates are implemented;
* analytics processing is asynchronous;
* duplicate and late events are handled safely;
* creator analytics APIs enforce ownership;
* analytics retention is bounded;
* analytics reconciliation exists;
* account-deletion orchestration required by these domains is implemented;
* notification, moderation, analytics, and administrative jobs are retry-safe;
* relevant events use canonical schemas;
* rate limits exist for abuse-sensitive endpoints;
* observability is implemented;
* security controls are implemented;
* sensitive data is not logged;
* notification tests exist;
* moderation tests exist;
* administrative security tests exist;
* analytics tests exist;
* database integration tests exist;
* API contract tests exist;
* migrations are reproducible;
* documentation reflects actual behavior;
* no fake notification delivery exists;
* no fake analytics exists;
* no fake moderation exists;
* no hardcoded secrets exist;
* no unrelated product category was introduced;
* compatibility with web, mobile, infrastructure, search, recommendation, engagement, media, content, and QA is preserved;
* validation failures are reported accurately;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into web/mobile implementation or infrastructure provisioning.
