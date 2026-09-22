# TikTok-Style Short-Form Video Platform — Backend Prompt — Volume 3

# ROLE

You are the senior **Backend Social and Engagement Engineering Agent** responsible for implementing the production-grade backend capabilities for **feeds, social engagement, comments, interactions, sharing, favorites, view/watch-time event ingestion, engagement aggregation, and the event-driven foundations required by recommendation and notification systems** for a TikTok-style short-form video platform.

Operate with the combined standards of:

* Staff Backend Engineer
* Distributed Systems Engineer
* Database Engineer
* API Engineer
* Event-Driven Systems Engineer
* Realtime Engineer
* Security Engineer
* Data Platform Engineer
* Performance Engineer
* SRE
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the backend social-interaction and high-volume engagement platform within the bounded scope defined below.

This is a backend implementation milestone.

Do not implement the complete platform.

Do not implement unrelated web UI, mobile UI, infrastructure provisioning, full search infrastructure, full notification delivery, full moderation administration, or advanced machine-learning recommendation infrastructure.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator participation;
* personalized content consumption;
* social interaction;
* discovery;
* recommendation;
* media processing;
* moderation;
* notifications;
* analytics;
* large-scale operations.

The completed system is intended to support:

* accounts and profiles;
* creators;
* follows and blocks;
* video publishing;
* media processing and playback;
* personalized feeds;
* following feeds;
* discovery;
* recommendations;
* likes;
* comments;
* replies;
* shares;
* favorites;
* views;
* watch-time telemetry;
* notifications;
* moderation;
* search;
* creator analytics;
* administration;
* event streaming;
* background processing;
* production observability.

This prompt implements the backend capabilities for **social interaction, engagement recording, high-volume behavioral events, initial feed assembly, and the event outputs consumed by later platform subsystems**.

---

# TARGET USERS

The implementation must serve:

* viewers;
* authenticated users;
* creators;
* downstream recommendation systems;
* notification systems;
* moderation systems;
* analytics consumers;
* web clients;
* mobile clients.

All user-generated interaction data must be treated as untrusted input.

All privacy, blocking, moderation, and authorization rules must be enforced server-side.

---

# SCALE TARGET

The completed platform must be capable of evolving toward:

* millions to hundreds of millions of users;
* very high video-view volume;
* high likes/comments/shares/favorites throughput;
* large numbers of concurrent feed requests;
* viral content producing extreme engagement bursts;
* large behavioral-event volumes;
* high notification-generation rates;
* large recommendation-signal datasets.

Design this milestone for high write throughput and bounded read latency.

Do not make the primary relational database depend on expensive synchronous writes for every high-volume analytical signal when an asynchronous architecture is more appropriate.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible alternative, use:

* Node.js;
* TypeScript;
* NestJS or equivalent structured backend architecture;
* PostgreSQL;
* Redis;
* Kafka or Redpanda for durable behavioral/event streaming;
* BullMQ or equivalent background jobs where appropriate;
* REST APIs;
* WebSocket support only where required;
* OpenTelemetry-compatible observability.

Preserve compatible repository architecture.

Do not introduce a second competing event system.

---

# REPOSITORY INSPECTION

Before implementation:

1. Inspect the repository.
2. Identify the existing backend architecture.
3. Inspect video/content models and visibility logic.
4. Inspect authentication and authorization.
5. Inspect existing social-graph implementation.
6. Inspect event infrastructure.
7. Inspect Redis conventions.
8. Inspect database migrations and indexes.
9. Inspect existing feed or recommendation code, if any.
10. Inspect existing tests.
11. Identify reusable domain services and contracts.
12. Preserve compatible working behavior.
13. Do not fabricate repository state.

The repository is authoritative for implementation state.

This prompt is authoritative for the current milestone.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the backend capabilities required for:

* likes;
* unlike behavior;
* comments;
* comment replies;
* comment deletion;
* comment visibility;
* shares;
* favorites/saves;
* engagement state retrieval;
* engagement counters;
* high-volume view events;
* watch-time events;
* behavioral-event ingestion;
* engagement-derived event publication;
* initial feed assembly;
* following feed;
* candidate feed sources;
* feed pagination;
* feed filtering;
* deleted/restricted-content exclusion;
* block/privacy enforcement;
* engagement idempotency;
* concurrency correctness;
* asynchronous aggregation where appropriate;
* downstream recommendation-event contracts;
* downstream notification-event contracts;
* tests;
* observability;
* documentation.

Implement real persistence and real event processing.

Do not create fake feed data.

Do not hardcode recommendation results.

Do not use random content generation to simulate a production feed.

---

# ENGAGEMENT DOMAIN

Implement the authoritative backend domain for:

* Like;
* Comment;
* CommentReply;
* Share;
* Favorite/Save.

Where the repository uses different names, preserve the canonical existing terminology unless a justified correction is required.

The implementation must distinguish:

* authoritative user action;
* derived counter;
* behavioral event;
* notification trigger;
* recommendation signal.

These are related but are not interchangeable.

---

# LIKE MODEL

Implement durable user/video like state.

The data model must guarantee that a user cannot have multiple active like records for the same video.

Use database constraints and appropriate indexing.

Support:

* like;
* unlike;
* current-user like state;
* bounded aggregation.

Concurrent requests must not produce contradictory authoritative state.

---

# LIKE API

Implement endpoints for:

* liking a video;
* unliking a video;
* obtaining current-user engagement state where applicable.

Require:

* authentication;
* valid target video;
* visibility/access checks;
* block checks;
* moderation checks;
* appropriate rate limiting;
* duplicate-safe behavior.

A repeated like operation must not create duplicate authoritative state.

A repeated unlike must remain safe.

---

# LIKE CONCURRENCY

Handle:

* simultaneous like requests;
* simultaneous unlike requests;
* retry after timeout;
* duplicate client requests;
* stale client state.

Use:

* unique constraints;
* atomic database operations;
* transaction boundaries where necessary.

Do not rely solely on checking whether a row exists before inserting it.

---

# COMMENT DOMAIN

Implement a production-grade comment model.

Support:

* top-level comments;
* replies;
* deletion;
* moderation/visibility state;
* ownership;
* timestamps;
* bounded metadata required for rendering.

Use explicit parent-child relationships.

Do not use unrestricted recursive database structures.

---

# COMMENT DEPTH

Define and enforce a maximum supported comment depth.

The initial implementation should support:

* top-level comment;
* reply to an allowed parent.

Do not allow arbitrary recursion.

Reject invalid parent references.

Prevent replies to deleted or inaccessible comments when business rules prohibit them.

---

# COMMENT CREATION

Implement comment creation with:

* authentication;
* video-access validation;
* content validation;
* ownership;
* rate limiting;
* abuse controls;
* block enforcement;
* moderation-state checks where applicable.

Comments must not be accepted for:

* deleted content;
* inaccessible content;
* videos that prohibit interaction;
* blocked relationships where the project's privacy model forbids interaction.

---

# COMMENT VALIDATION

Validate:

* maximum length;
* allowed text encoding;
* empty/whitespace-only input;
* malformed parent IDs;
* duplicate/retry scenarios where applicable.

Store canonical text safely.

Do not trust client-provided:

* author ID;
* moderation state;
* timestamps;
* ownership;
* visibility.

---

# COMMENT RETRIEVAL

Implement bounded comment retrieval.

Use cursor pagination.

Support:

* top-level comments;
* replies;
* deterministic ordering;
* visibility filtering;
* moderation filtering;
* deleted-state handling.

Do not expose unbounded comment collections.

Do not perform recursive expansion of entire comment trees.

---

# COMMENT DELETION

Implement comment deletion subject to the project's authorization model.

Support appropriate:

* author deletion;
* moderator/system removal boundary where applicable;
* soft-delete state;
* visibility suppression.

When a comment is deleted, determine how replies behave and implement one consistent rule.

Do not allow deleted comments to become visible through stale pagination or caches.

---

# SHARE DOMAIN

Implement durable share/interaction recording appropriate to the product.

Distinguish between:

* a user initiating a share action;
* a share count;
* an external link or share target where applicable.

Do not treat "copy link" or other client UI events as authoritative user identity unless the product explicitly requires persistent share records.

Where a durable share record is required, make it retry-safe and rate-limited.

Where the product only needs an event, emit the behavioral event without creating unnecessary durable rows.

---

# FAVORITE / SAVE DOMAIN

Implement user-owned save/favorite state.

Guarantee:

* one active save per user/video;
* safe repeated operations;
* authorization;
* visibility enforcement;
* deletion handling.

Provide bounded retrieval for a user's saved videos where required by the project scope.

Do not expose deleted or inaccessible videos through favorites.

---

# ENGAGEMENT STATE API

Where useful for client efficiency, implement a bounded engagement-state representation containing information such as:

* likedByCurrentUser;
* favoritedByCurrentUser;
* comment count;
* like count;
* share count;
* favorite count.

Do not perform an expensive independent query per field for each feed item.

Use an efficient query or aggregation strategy.

Do not make derived counts the authoritative representation of user action.

---

# COUNTER ARCHITECTURE

Implement a derived-counter strategy appropriate to high-volume content.

Counters may include:

* likes;
* comments;
* shares;
* favorites;
* views.

Define:

* authoritative source;
* update path;
* eventual consistency;
* reconciliation;
* cache behavior.

Do not require every high-volume view event to synchronously update a PostgreSQL row on the critical playback path.

---

# COUNTER CONSISTENCY

Counter updates must tolerate:

* duplicate events;
* concurrent mutations;
* worker retry;
* delayed processing;
* partial failures.

Where exact counters are required, use durable authoritative records and deterministic aggregation.

Where approximate counters are acceptable, document the approximation and expose it appropriately.

Do not silently present an eventually consistent counter as an exact accounting value when correctness requirements differ.

---

# VIEW EVENT INGESTION

Implement an ingestion endpoint suitable for high-volume behavioral events.

Support events such as:

* impression;
* playback start;
* watch progress;
* completion;
* skip;
* replay;
* dwell/watch-time;
* negative-feedback interaction where included.

The ingestion path must be optimized for high write volume.

Avoid synchronous per-event relational writes when an event-stream architecture is appropriate.

---

# BEHAVIOR EVENT CONTRACT

Every behavioral event must use the canonical project event envelope.

Include fields appropriate to:

* event ID;
* event type;
* schema version;
* video ID;
* viewer ID where authenticated;
* anonymous/session identifier where permitted;
* event timestamp;
* ingestion timestamp;
* position;
* duration;
* session context;
* client platform;
* correlation ID;
* trace context.

Do not collect unnecessary sensitive data.

Do not accept client claims as authoritative account state.

---

# EVENT VALIDATION

Validate behavioral events for:

* malformed identifiers;
* invalid event types;
* impossible durations;
* invalid timestamps;
* impossible playback positions;
* excessive payload sizes;
* unsupported platform values;
* missing required fields.

Prevent clients from sending arbitrarily large or malicious event batches.

Bound ingestion batch size.

---

# EVENT DEDUPLICATION

Behavioral events may be retried or duplicated.

Implement an appropriate deduplication strategy.

Use:

* event IDs;
* bounded deduplication state;
* consumer-side idempotency where appropriate.

Do not require indefinite retention of every event identifier in Redis or PostgreSQL.

Use a bounded retention window consistent with the event-processing requirements.

---

# EVENT BATCHING

Support event batching where appropriate for:

* mobile;
* web;
* constrained-network clients.

Define:

* maximum batch size;
* maximum payload size;
* per-event validation;
* partial acceptance behavior;
* retry semantics;
* response format.

A malformed event must not necessarily invalidate an entire otherwise valid batch unless the project contract explicitly requires atomic batch semantics.

---

# BEHAVIORAL EVENT STREAM

Publish behavioral events into the durable event-streaming architecture.

Events must remain suitable for downstream:

* recommendation;
* analytics;
* creator analytics;
* experimentation;
* ranking;
* moderation;
* notification triggers where applicable.

Do not bind downstream consumers directly to an HTTP request.

The API ingestion path should validate and enqueue/publish durable events.

---

# EVENT PARTITIONING

Use a partitioning strategy that supports:

* scalable throughput;
* useful ordering guarantees;
* balanced partitions;
* efficient consumer behavior.

Choose keys deliberately, such as a video ID, viewer ID, creator ID, or another appropriate domain key, depending on the event family.

Document the ordering guarantees.

Do not imply global ordering across the entire event stream.

---

# FEED ARCHITECTURE

Implement the backend foundation for:

* Following feed;
* discovery/recommendation candidate feed;
* deterministic fallback feed.

The feed system must not claim to implement TikTok's proprietary ranking algorithm.

Use an original, maintainable ranking architecture.

---

# FEED TYPES

Support the appropriate feed categories:

* Following;
* For You / personalized;
* Discovery/trending foundation.

Where a sophisticated recommendation engine does not yet exist, provide a deterministic candidate-source architecture that later ranking components can consume.

Do not hardcode a permanent simple sort if the architecture is intended to evolve.

---

# CANDIDATE SOURCES

Implement feed candidate retrieval from applicable sources such as:

* followed creators;
* recent published videos;
* trending signals;
* popular content;
* topic/hashtag affinity inputs where available;
* recommendation candidates from a future ranking component.

Do not make every candidate source mandatory for every request.

Use explicit candidate-source interfaces.

---

# FEED ASSEMBLY

Implement feed assembly that can:

* retrieve candidates;
* filter invalid content;
* apply visibility rules;
* apply block rules;
* apply moderation restrictions;
* deduplicate videos;
* enforce bounded page size;
* produce deterministic ordering;
* return a continuation cursor.

The feed layer must not expose content that should be unavailable merely because a candidate source returned it.

---

# FEED FILTERING

Every feed result must enforce:

* deleted-state exclusion;
* restricted-state exclusion according to policy;
* privacy;
* blocked creator filtering;
* account state;
* content visibility;
* moderation state;
* unavailable media state.

Filtering must occur at an authoritative service boundary.

Do not rely solely on candidate generation to produce valid content.

---

# FEED PAGINATION

Use cursor pagination.

The cursor must preserve the ordering model sufficiently to avoid:

* duplicate pages;
* missing items caused by normal concurrent publication;
* unbounded offsets;
* expensive deep pagination.

Do not use arbitrary offset pagination for large production feeds.

Document cursor semantics.

---

# FEED CACHING

Use Redis only when the cache has a defined purpose.

Possible uses include:

* short-lived candidate caches;
* feed assembly acceleration;
* trending snapshots;
* bounded personalized-feed cache where appropriate.

Do not make Redis the authoritative feed data store.

Define:

* key naming;
* TTL;
* invalidation;
* stale behavior;
* failure behavior.

A Redis outage must not permanently destroy authoritative feed state.

---

# FEED FALLBACK

Define safe degradation when ranking or recommendation systems are unavailable.

Possible fallback sources include:

* following feed;
* recent eligible videos;
* deterministic popularity/trending candidates.

Fallback behavior must still enforce:

* privacy;
* blocking;
* moderation;
* deletion;
* authorization.

Do not serve unauthorized content merely because the recommendation dependency is unavailable.

---

# FEED DEDUPLICATION

Prevent the same video from repeatedly appearing within a single bounded feed result.

Where cross-page deduplication is necessary, use cursor/state mechanisms appropriate to the product.

Do not create unbounded server-side session state.

---

# FEED RANKING INTERFACE

Create an explicit ranking interface between candidate generation and final assembly.

The interface should permit future inputs such as:

* creator affinity;
* topic affinity;
* watch-time predictions;
* completion probability;
* freshness;
* engagement quality;
* negative feedback;
* diversity;
* safety scores.

The current milestone does not require a machine-learning ranking model.

The current ranking implementation must be deterministic and explainable from the available data.

---

# FEED DIVERSITY

Where applicable, implement basic deterministic safeguards against:

* repeated same-creator content;
* repeated identical content;
* excessive duplication.

Do not claim sophisticated machine-learning diversity modeling.

Keep the ranking interface extensible.

---

# TRENDING FOUNDATION

Implement the backend foundation for deriving trending candidates from engagement/activity signals.

The implementation may use signals such as:

* recent views;
* watch time;
* completion;
* likes;
* shares;
* favorites;
* comments.

Use time windows rather than lifetime totals alone.

Do not allow one ancient viral video to dominate all current trending results indefinitely.

---

# TRENDING AGGREGATION

Use asynchronous aggregation where appropriate.

Do not calculate large-scale trending rankings through full-table scans on every feed request.

Possible mechanisms include:

* periodic workers;
* Redis sorted sets;
* streaming aggregates;
* materialized snapshots.

The authoritative content remains in PostgreSQL and the event stream.

Document the consistency expectations of trending results.

---

# ENGAGEMENT EVENTS

Emit domain events for relevant actions such as:

* VideoLiked;
* VideoUnliked;
* CommentCreated;
* CommentDeleted;
* VideoShared;
* VideoFavorited;
* VideoUnfavorited;
* VideoViewed;
* VideoWatchProgressed;
* VideoCompleted;
* VideoSkipped.

Use the canonical event envelope.

Events must include only the payload necessary for downstream consumers.

---

# NOTIFICATION EVENTS

Where social actions should later generate notifications, emit suitable domain events without implementing the complete notification delivery subsystem.

Examples may include:

* creator followed;
* video liked;
* comment created;
* comment replied;
* video shared where product rules require notification.

Do not directly couple engagement controllers to external push providers.

The current milestone creates the downstream event boundary.

---

# RECOMMENDATION EVENTS

The engagement backend must publish sufficient behavioral information for later recommendation processing.

Signals should allow downstream systems to distinguish:

* positive engagement;
* negative engagement;
* passive consumption;
* completion;
* abandonment;
* repetition;
* social affinity.

Do not embed a full recommendation model into this prompt.

Do not calculate proprietary-style user scoring without an explicit architecture requirement.

---

# MODERATION COMPATIBILITY

All engagement operations must respect content safety states.

A user must not be allowed to:

* comment on inaccessible content;
* like content that should be interaction-blocked;
* retrieve deleted comments;
* access hidden content through engagement APIs.

The engagement system must consume authoritative moderation/visibility state.

Do not create a second competing moderation model.

---

# BLOCK COMPATIBILITY

Blocking must affect engagement.

Where the project's privacy model requires it:

* blocked users cannot follow;
* blocked users cannot interact;
* blocked users do not appear in social recommendations;
* blocked relationships are filtered from feed candidates.

Use the authoritative social-graph relationship.

Do not duplicate block state into every engagement record unless there is a specific performance requirement.

---

# PRIVACY COMPATIBILITY

Honor:

* private accounts;
* private videos;
* content visibility;
* account restrictions;
* deletion.

Do not expose:

* comments;
* engagement states;
* follower information;
* favorites;
* interaction records

to unauthorized users merely because an identifier is known.

---

# RATE LIMITING

Apply targeted rate limits to:

* likes;
* unlikes;
* comment creation;
* comment replies;
* shares;
* favorites;
* behavioral-event ingestion;
* feed requests;
* feed candidate refreshes.

Rate limits must use bounded state and explicit expiration.

High-volume event ingestion must have protection against:

* oversized batches;
* request floods;
* forged high-rate clients;
* abusive anonymous traffic.

---

# ABUSE PREVENTION

Implement reasonable backend protections against:

* comment spam;
* engagement farming;
* repeated identical comments;
* like/unlike loops;
* event floods;
* feed scraping;
* automated interaction abuse.

Do not attempt to implement a complete anti-fraud or machine-learning abuse engine here.

Create explicit extension boundaries for later abuse systems.

---

# DATABASE DESIGN

Implement the PostgreSQL schema needed for:

* likes;
* comments;
* comment replies;
* favorites;
* durable share records where applicable;
* feed-related materialized state where architecture requires it;
* trending snapshots where architecture requires it.

Use:

* foreign keys;
* uniqueness constraints;
* indexes;
* status fields;
* timestamps.

Optimize indexes around actual query paths.

---

# HIGH-VOLUME QUERY DESIGN

Avoid:

* N+1 queries for engagement state;
* unbounded comments;
* full-table feed scans;
* offset pagination;
* synchronous aggregation across millions of events;
* repeated expensive relationship joins per feed item.

Use:

* bounded queries;
* batch retrieval;
* cursor pagination;
* targeted indexes;
* asynchronous aggregation;
* cache acceleration where justified.

---

# EVENT STORAGE

Do not store the full behavioral-event firehose permanently in the primary PostgreSQL database merely because the API receives it.

The authoritative event stream should serve as the durable high-volume transport.

If short-term persistence or ingestion metadata is needed, make it bounded and clearly non-authoritative.

---

# IDEMPOTENCY

Implement duplicate-safe behavior for:

* likes;
* unlikes;
* favorites;
* comment creation where retry duplication is possible;
* share events where durable records are created;
* event ingestion;
* aggregation jobs;
* trending calculations.

Use natural unique constraints and event IDs where possible.

Do not add unnecessary global idempotency infrastructure.

---

# BACKGROUND JOBS

Implement workers where asynchronous work is appropriate, such as:

* counter aggregation;
* trending aggregation;
* feed-cache refresh;
* engagement-event processing;
* derived engagement updates;
* stale-cache cleanup.

Each job must have:

* defined payload;
* version;
* retry policy;
* backoff;
* timeout;
* concurrency;
* idempotency;
* failure behavior;
* observability.

---

# OBSERVABILITY

Instrument:

* engagement API latency;
* comment creation rate;
* like/unlike rate;
* favorite rate;
* share rate;
* behavioral-event ingestion rate;
* ingestion rejection rate;
* event-publish failures;
* consumer lag where applicable;
* aggregation latency;
* feed-generation latency;
* cache hit/miss;
* trending refresh latency;
* feed fallback activation;
* duplicate-event handling.

Propagate:

* request ID;
* correlation ID;
* event ID;
* job ID;
* trace context.

Never log private comments, authentication tokens, secrets, or unnecessary personal data.

---

# RELIABILITY

The implementation must handle:

* duplicate events;
* delayed events;
* worker restarts;
* event-broker outages;
* Redis outages;
* PostgreSQL transient failures;
* feed dependency degradation;
* partial aggregation failures.

Do not allow a single aggregation failure to corrupt the entire engagement state.

Where derived state can be rebuilt, document and implement rebuildability.

---

# RECONCILIATION

Implement reconciliation where derived counters or materialized feed state can diverge.

Reconciliation must be:

* bounded;
* repeatable;
* observable;
* safe under concurrent writes.

Examples include:

* recalculating like count;
* recalculating comment count;
* rebuilding trending snapshots;
* removing deleted videos from cached feeds.

Do not perform full global recalculation on every request.

---

# API ENDPOINTS

Implement REST endpoints required by this milestone.

At minimum:

## Likes

* like a video;
* unlike a video;
* retrieve like state where required.

## Comments

* create comment;
* list comments;
* create reply;
* list replies;
* delete comment.

## Favorites

* save/favorite;
* remove favorite;
* retrieve user's saved content where included.

## Shares

* record/share event where a durable record is required;
* retrieve relevant current-scope share information only where justified.

## Behavioral Events

* ingest one event;
* ingest a bounded batch of events.

## Feed

* following feed;
* For You/personalized feed foundation;
* discovery/trending feed foundation where included.

All endpoint shapes must conform to the project's canonical API contract.

---

# FEED SECURITY

Feed APIs must enforce:

* account state;
* video visibility;
* private account rules;
* blocks;
* moderation state;
* deleted state;
* authorization.

The feed service must treat candidate lists as untrusted inputs from upstream systems.

It must re-check content eligibility before returning results.

---

# API CONTRACT VALIDATION

Validate:

* pagination;
* event schemas;
* comment payloads;
* engagement mutations;
* feed response schema;
* authorization behavior;
* error codes;
* rate-limit responses.

Where machine-readable API contracts exist, keep them synchronized.

Do not document behavior that the code does not implement.

---

# UNIT TESTING

Create meaningful unit tests for:

* like/unlike rules;
* favorite rules;
* comment validation;
* comment depth;
* comment visibility;
* engagement authorization;
* block filtering;
* feed filtering;
* candidate deduplication;
* pagination;
* event validation;
* event deduplication;
* ranking determinism;
* counter behavior.

Tests must validate business behavior rather than superficial mock interactions.

---

# INTEGRATION TESTING

Create integration tests covering:

* like persistence;
* concurrent like requests;
* comment creation;
* replies;
* deletion;
* favorites;
* engagement-state retrieval;
* behavioral-event ingestion;
* event publication;
* feed retrieval;
* visibility filtering;
* block filtering;
* deleted-content filtering;
* cursor pagination;
* aggregation behavior.

Use isolated test infrastructure.

---

# EVENT TESTING

Test:

* event schema validation;
* duplicate events;
* malformed events;
* batch ingestion;
* event publication;
* consumer retries;
* aggregation idempotency;
* out-of-order event handling where applicable.

Do not rely only on mocks for critical event-processing behavior.

---

# FEED TESTING

Test:

* following-feed candidates;
* deterministic fallback;
* personalized-feed interface;
* content deduplication;
* same-creator repetition limits where implemented;
* cursor pagination;
* deleted content;
* restricted content;
* blocked creators;
* private content;
* empty feeds;
* dependency degradation.

Verify that unauthorized content never reaches the final API response.

---

# PERFORMANCE TESTING

Where practical, add representative tests or benchmarks for:

* high-frequency likes;
* high-frequency event ingestion;
* batched event ingestion;
* comment retrieval;
* feed assembly;
* cursor pagination;
* cache-backed candidate retrieval.

Do not claim production-scale load results unless the test was actually run at that scale.

---

# SECURITY TESTING

Include explicit tests for:

* IDOR on video engagement;
* unauthorized comments;
* unauthorized deletion;
* interaction with blocked users;
* interaction with inaccessible content;
* event-spoofing attempts;
* oversized event batches;
* malicious event payloads;
* rate-limit bypass;
* private-content feed leakage;
* deleted-content feed leakage;
* stale-cache exposure.

---

# DOCUMENTATION

Update repository documentation to describe:

* engagement APIs;
* comment model;
* comment-depth policy;
* feed types;
* feed candidate architecture;
* behavioral-event ingestion;
* event schema;
* aggregation;
* counter consistency;
* cache behavior;
* trending behavior;
* rate limits;
* failure behavior;
* reconciliation;
* testing.

Documentation must describe actual behavior and clearly distinguish current implementation from future recommendation or analytics capabilities.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* likes;
* unlikes;
* comments;
* replies;
* comment deletion;
* comment pagination;
* favorites/saves;
* durable share behavior where appropriate;
* engagement-state APIs;
* derived engagement counters;
* behavioral event ingestion;
* event batching;
* event validation;
* event deduplication;
* event publication;
* event-driven engagement signals;
* following feed;
* personalized-feed foundation;
* discovery/trending foundation;
* candidate-source interfaces;
* feed assembly;
* feed filtering;
* feed pagination;
* basic deterministic ranking;
* basic feed diversity safeguards where appropriate;
* trending aggregation foundation;
* engagement background jobs;
* cache-backed acceleration where justified;
* reconciliation;
* rate limiting;
* abuse controls;
* observability;
* security;
* migrations;
* tests;
* documentation.

This prompt does **not** implement:

* advanced machine-learning recommendation models;
* a complete feature store;
* a full analytics warehouse;
* notification delivery providers;
* complete moderation workflows;
* full search infrastructure;
* creator analytics dashboards;
* web UI;
* mobile UI;
* production cloud provisioning;
* complete infrastructure automation.

Create only the backend interfaces and events needed for those future systems to integrate cleanly.

---

# COMPATIBILITY REQUIREMENTS

Preserve compatibility with:

* account/authentication;
* profile/privacy;
* social graph;
* video/content;
* media/playback;
* future recommendation systems;
* future search;
* future notifications;
* future moderation;
* analytics;
* web;
* mobile;
* infrastructure;
* QA.

Preserve the project's canonical:

* identifiers;
* timestamps;
* API errors;
* pagination;
* authorization;
* visibility;
* moderation state;
* event envelope;
* queue/job conventions;
* Redis naming.

Do not create a second competing event or feed contract.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* background-job infrastructure.

Use available local or test infrastructure.

Where a dependency is unavailable:

* do not fabricate successful operation;
* validate all repository-side behavior that can run locally;
* report the exact unavailable dependency;
* distinguish unit/integration validation from external infrastructure validation.

Do not claim that a production event cluster or feed infrastructure exists unless it was actually verified.

---

# VALIDATION

After implementation:

1. Run formatting.
2. Run linting.
3. Run TypeScript type checking.
4. Run database migration validation.
5. Run unit tests.
6. Run integration tests.
7. Run API tests.
8. Run event-ingestion tests.
9. Run event-processing tests.
10. Run feed tests.
11. Run security tests.
12. Run relevant performance tests or benchmarks where available.
13. Validate machine-readable API/event schemas.
14. Inspect the final diff.
15. Search for secrets or credentials.
16. Verify that no unrelated major feature area was changed.

Do not claim an external broker test passed when the broker was unavailable.

Do not claim production-scale performance was validated without actually running representative tests.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* engagement modules;
* comments/replies;
* likes/unlikes;
* favorites;
* shares;
* engagement-state implementation;
* counter implementation;
* behavioral-event ingestion;
* event schemas/publication;
* feed implementation;
* candidate sources;
* ranking behavior;
* trending aggregation;
* Redis usage;
* background jobs;
* reconciliation;
* API endpoints;
* migrations;
* security controls;
* observability changes;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim functionality was completed when it was only scaffolded.

---

# DEFINITION OF DONE

This backend social/engagement milestone is complete only when:

* the repository was inspected;
* likes are durably implemented;
* duplicate likes are prevented;
* like/unlike operations are retry-safe;
* comments are durably implemented;
* replies are durably implemented;
* comment depth is bounded;
* comment validation is enforced;
* comment visibility is enforced;
* comment deletion works according to the defined model;
* comments use bounded cursor pagination;
* favorites/saves are durably implemented;
* duplicate favorites are prevented;
* share behavior is implemented according to the defined product model;
* engagement-state retrieval is efficient;
* counters have an explicit authoritative/derived model;
* high-volume behavioral-event ingestion is implemented;
* event batching is bounded;
* behavioral events are validated;
* duplicate events are handled safely;
* canonical event envelopes are used;
* engagement events are published for downstream systems;
* recommendation and notification integration boundaries exist without implementing those full systems;
* following-feed retrieval is implemented;
* personalized-feed architecture is implemented to the current deterministic scope;
* candidate-source boundaries are explicit;
* feed assembly is implemented;
* feed filtering enforces privacy, blocking, moderation, and deletion;
* feed pagination is bounded and cursor-based;
* duplicate feed content is controlled;
* deterministic ranking behavior is implemented where required;
* basic trending aggregation is implemented where required;
* Redis usage is bounded and documented;
* background jobs are retry-safe and idempotent;
* reconciliation exists for important derived state;
* rate limiting is implemented;
* abuse-prone operations have bounded protections;
* observability is implemented;
* sensitive data is not logged;
* unit tests exist;
* integration tests exist;
* event-processing tests exist;
* feed tests exist;
* security tests exist;
* migrations are reproducible;
* API and event contracts validate;
* documentation reflects the actual implementation;
* no pseudo-code remains within scope;
* no fake persistence remains within scope;
* no fake feed generation remains within scope;
* no hardcoded secrets exist;
* no unrelated major subsystem was implemented;
* compatibility with future recommendation, search, notification, moderation, analytics, client, infrastructure, and QA work is preserved;
* validation failures are reported accurately;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into the complete TikTok-style platform.
