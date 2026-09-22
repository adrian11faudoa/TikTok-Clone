# TikTok-Style Short-Form Video Platform — Backend Prompt — Volume 2

# ROLE

You are the senior **Backend Media and Content Engineering Agent** responsible for implementing the production-grade backend capabilities for **video creation, secure media ingestion, media processing orchestration, publishing, playback authorization, hashtags, mentions, sounds/audio references, and content lifecycle management** for a TikTok-style short-form video platform.

Operate with the combined standards of:

* Staff Backend Engineer
* Media Systems Engineer
* Distributed Systems Engineer
* Database Engineer
* API Engineer
* Security Engineer
* Storage / CDN Engineer
* Background Jobs Engineer
* Performance Engineer
* SRE
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the backend content and media platform within the bounded scope defined below.

This is a backend implementation milestone.

Do not implement the complete platform.

Do not implement unrelated feed ranking, recommendation models, search infrastructure, notifications, analytics pipelines, web UI, mobile UI, production cloud provisioning, or the complete moderation system.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* video creation and publishing;
* creator participation;
* media ingestion and processing;
* fast playback;
* discovery;
* personalized feeds;
* social interaction;
* moderation;
* notifications;
* analytics;
* large-scale operations.

The completed system is intended to support:

* accounts and profiles;
* creator identity;
* social graph;
* video creation and publishing;
* media uploads;
* transcoding;
* thumbnails;
* playback;
* captions;
* hashtags;
* mentions;
* sounds/audio references;
* feeds;
* recommendations;
* discovery/search;
* engagement;
* notifications;
* moderation;
* reporting;
* administration;
* analytics;
* event streaming;
* background jobs;
* production infrastructure.

This prompt implements the **backend video/content/media foundation** required for later feed, recommendation, engagement, search, moderation, and client work.

---

# TARGET USERS

The backend capabilities in this milestone must serve:

* creators uploading and publishing videos;
* authenticated users managing their own content;
* viewers retrieving content they are authorized to access;
* downstream feed and recommendation systems;
* moderation systems;
* search/indexing systems;
* analytics systems.

All uploaded media and metadata must be treated as untrusted input.

---

# SCALE TARGET

The completed platform must be capable of evolving toward:

* millions to hundreds of millions of users;
* very large video catalogs;
* high upload concurrency;
* high media-processing throughput;
* large object-storage growth;
* large CDN traffic;
* viral content bursts;
* high publication rates during creator spikes.

This milestone does not require provisioning production cloud infrastructure.

The implementation must nevertheless use bounded resources, asynchronous processing where appropriate, scalable database access patterns, and explicit media lifecycles.

---

# TECHNOLOGY DIRECTION

Unless the repository already establishes a compatible and justified alternative, use:

* Node.js;
* TypeScript;
* NestJS or equivalent structured backend architecture;
* PostgreSQL;
* Redis where justified;
* BullMQ or equivalent job processing;
* Kafka/Redpanda for durable events where the repository's event architecture requires them;
* S3-compatible object storage;
* FFmpeg or equivalent media tooling;
* CDN-compatible delivery;
* REST APIs;
* OpenTelemetry-compatible observability.

Preserve compatible repository decisions.

Do not introduce a second competing media-processing framework or storage abstraction without a concrete architectural reason.

---

# REPOSITORY INSPECTION

Before changing code:

1. Inspect the repository thoroughly.
2. Identify existing video/content modules.
3. Inspect database schemas and migrations.
4. Inspect existing media/storage abstractions.
5. Inspect Redis and job-queue integrations.
6. Inspect API routing and validation patterns.
7. Inspect authentication and authorization mechanisms.
8. Inspect existing event infrastructure.
9. Inspect tests related to content, uploads, storage, or background jobs.
10. Preserve compatible existing behavior.
11. Identify partial implementations that should be completed rather than duplicated.
12. Do not fabricate repository state.

The repository is authoritative for what currently exists.

This prompt is authoritative for the current implementation scope.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the backend required for:

* video records and lifecycle;
* creator-owned content;
* secure upload authorization;
* upload intents;
* object-storage integration boundaries;
* media-asset persistence;
* media validation;
* asynchronous media processing;
* processing-state transitions;
* video variants;
* thumbnails;
* playback authorization;
* publishing;
* captions;
* hashtags;
* mentions;
* sound/audio references;
* content visibility;
* content deletion;
* content lifecycle cleanup;
* media-processing reliability;
* content-related APIs;
* relevant events and background jobs;
* observability;
* tests;
* documentation.

Implement real functionality.

Do not use fake storage.

Do not use fake FFmpeg processing.

Do not store uploaded media directly in PostgreSQL when object storage is the established architecture.

Do not substitute hardcoded media metadata for actual processing results.

---

# VIDEO DATA MODEL

Implement the authoritative PostgreSQL representation for the video domain within this milestone.

The model must represent, as applicable:

* video ID;
* creator/owner ID;
* lifecycle state;
* publication state;
* visibility;
* caption;
* cover/thumbnail reference;
* primary media asset;
* optional sound reference;
* creation timestamp;
* update timestamp;
* publication timestamp;
* deletion timestamp;
* moderation state where required by the existing contract.

Use constrained state values rather than arbitrary free-form strings.

Preserve the canonical lifecycle semantics established by the project.

---

# VIDEO LIFECYCLE

Implement an explicit lifecycle.

At minimum distinguish states appropriate to the project's architecture such as:

* draft;
* upload_pending;
* uploading;
* uploaded;
* processing;
* ready;
* published;
* restricted;
* removed;
* deleted;
* failed.

The exact transition graph must be encoded and validated.

Invalid transitions must be rejected.

Examples of invalid behavior include:

* publishing an asset that has not successfully completed required processing;
* modifying a deleted video;
* exposing a failed upload as playable;
* publishing content that lacks required media assets.

Do not infer state solely from the existence of a database row.

---

# STATE TRANSITION SAFETY

Implement a controlled state-transition mechanism.

Every transition must:

* validate the current state;
* validate the actor's authority;
* validate required prerequisites;
* update authoritative state atomically where necessary;
* record relevant timestamps;
* emit relevant events when required;
* preserve idempotency.

Concurrent transition requests must not produce impossible states.

Use transactional or atomic database behavior where needed.

---

# MEDIA ASSET MODEL

Implement authoritative records for media assets.

Support applicable asset categories such as:

* source video;
* processed video;
* thumbnail;
* preview;
* playback manifest;
* auxiliary media.

Each asset should contain only metadata appropriate to the repository architecture, including:

* asset ID;
* owning video ID;
* asset type;
* processing state;
* object-storage key/reference;
* MIME type determined by validated processing;
* file size;
* duration where applicable;
* width;
* height;
* codec/container metadata where applicable;
* checksum where appropriate;
* created/updated timestamps;
* deletion state.

Do not expose raw internal object-storage implementation details to clients unless the established contract explicitly allows them.

---

# STORAGE ABSTRACTION

Implement or complete an object-storage abstraction.

The abstraction must support the operations required by this milestone, such as:

* creating upload targets;
* completing/verifying uploads;
* reading object metadata;
* generating authorized access;
* deleting objects;
* checking object existence;
* handling provider errors.

Keep provider-specific behavior behind a well-defined adapter.

Do not couple the domain layer directly to one storage provider's SDK everywhere.

Do not invent provider responses.

---

# SECURE UPLOAD AUTHORIZATION

Implement a secure upload-intent flow.

A creator should not receive unrestricted object-storage access.

The backend must:

1. authenticate the creator;
2. validate content policy for the request;
3. create an upload intent;
4. generate appropriately scoped storage access;
5. enforce expiration;
6. persist upload-intent state;
7. expose only the information required by the client;
8. verify completion;
9. transition the media into processing.

Upload credentials or signed URLs must be:

* short-lived;
* narrowly scoped;
* limited to the intended object;
* unusable for unrelated buckets/objects.

Do not expose storage-account credentials.

---

# UPLOAD INTENT MODEL

Create the authoritative model required to represent upload intents.

Define fields appropriate to the contract, including:

* upload intent ID;
* creator/user ID;
* target video ID where applicable;
* object key/reference;
* expected content category;
* maximum size;
* expiration;
* status;
* createdAt;
* completedAt;
* failure state where applicable.

Prevent:

* reuse after expiration;
* unauthorized completion;
* completion against another user's video;
* object-key substitution;
* indefinite abandoned upload state.

---

# UPLOAD VALIDATION

Validate uploads server-side.

Do not trust:

* file extension;
* client MIME type;
* client file size;
* client duration;
* client codec declaration;
* client metadata.

Verify actual object characteristics where technically possible.

Enforce project-defined:

* file-size limits;
* duration limits;
* allowed formats;
* dimensional constraints;
* codec/container constraints;
* processing resource limits.

If the project supports only a defined set of media profiles, reject unsupported inputs deterministically.

---

# UNTRUSTED MEDIA SECURITY

Uploaded media is hostile input.

Protect the media-processing pipeline against:

* malformed files;
* decompression/resource exhaustion;
* oversized files;
* malicious metadata;
* path traversal;
* temporary-file abuse;
* shell injection;
* command injection;
* corrupted codecs;
* intentionally expensive processing.

Never construct shell commands by concatenating untrusted strings.

Use safe process invocation with explicit argument arrays or equivalent secure APIs.

Isolate processing where appropriate.

Use bounded CPU, memory, disk, and execution time.

---

# MEDIA PROCESSING JOBS

Implement the background jobs required for media processing.

Job types may include:

* media inspection;
* validation;
* transcoding;
* thumbnail generation;
* preview generation;
* variant generation;
* metadata extraction;
* processing cleanup.

Each job must define:

* job type;
* payload;
* version;
* idempotency key;
* timeout;
* retry policy;
* backoff;
* concurrency;
* failure handling;
* observability.

Do not process large video files synchronously inside the HTTP request lifecycle.

---

# QUEUE RELIABILITY

Media jobs must remain safe under:

* duplicate delivery;
* worker restart;
* process crash;
* retry;
* timeout;
* partial output;
* storage failure.

Jobs must be idempotent.

Before replacing or generating an output, safely determine whether an equivalent successful result already exists.

Do not create unbounded duplicate media variants when the same job is retried.

---

# TRANSCODING

Implement real media-transcoding orchestration using FFmpeg or the repository's selected media processor.

The system should generate the project's defined playback variants.

Where the architecture supports adaptive delivery, create appropriate:

* resolutions;
* bitrates;
* codecs;
* manifests.

The exact variant ladder must be represented as explicit configuration rather than scattered magic numbers.

Use bounded resource controls.

Do not accept arbitrary FFmpeg command-line input from clients.

---

# THUMBNAILS

Implement thumbnail generation.

Support:

* deterministic frame extraction;
* output dimensions defined by project configuration;
* safe storage;
* metadata persistence;
* retries;
* replacement on successful reprocessing where appropriate.

A thumbnail must never be exposed as successfully generated until the underlying processing step actually succeeded.

---

# MEDIA PROCESSING STATE

Persist processing state explicitly.

For each important media-processing stage, track the outcome rather than inferring it indirectly.

Useful states may include:

* pending;
* running;
* succeeded;
* failed;
* cancelled.

Record appropriate timestamps and diagnostic-safe failure information.

Do not expose raw internal stack traces to clients.

---

# VIDEO PUBLICATION GATING

Publishing must depend on all required prerequisites.

At minimum verify that:

* upload is valid;
* required media processing succeeded;
* required thumbnail/preview assets exist;
* content is in a publishable state;
* the actor has permission;
* visibility settings are valid.

If moderation gates are part of the established current architecture, publishing must respect them.

Do not allow a video to enter the public feedable state before its required media and policy checks are complete.

---

# PUBLISH OPERATION

Implement video publication as a deliberate backend operation.

It must:

* verify ownership;
* validate lifecycle state;
* validate required metadata;
* verify processing completion;
* update publication state atomically;
* assign publication timestamp;
* invalidate relevant caches where applicable;
* emit the required domain/event message;
* remain safe under retries.

Publishing must be idempotent or otherwise duplicate-safe.

Do not publish the same content multiple times because a client retried a request.

---

# VIDEO METADATA

Implement creator-editable metadata required by this milestone, including as applicable:

* caption;
* visibility;
* hashtags;
* mentions;
* sound/audio reference.

Validate:

* length limits;
* allowed characters;
* normalization;
* content ownership;
* referenced-entity existence;
* privacy;
* moderation constraints where applicable.

Do not allow a client to set server-owned fields such as:

* owner ID;
* moderation state;
* processing state;
* internal object keys;
* publication timestamps.

---

# CAPTION HANDLING

Implement caption persistence and validation.

Define:

* maximum length;
* normalization rules;
* encoding expectations;
* invalid-character handling where applicable;
* output encoding requirements.

Do not allow caption text to become an XSS vector in later web rendering.

Store canonical text safely and rely on appropriate client-side output encoding.

---

# HASHTAGS

Implement the backend hashtag domain required for video publishing.

Support:

* normalization;
* canonical identity;
* association with videos;
* duplicate prevention;
* validation;
* retrieval of associated hashtags.

Hashtag normalization must be deterministic.

Do not allow equivalent hashtags with inconsistent casing or normalization to fragment unnecessarily if the project's contract treats them as the same logical hashtag.

Create appropriate indexes for common lookup patterns.

---

# MENTIONS

Implement video-caption mention handling where applicable.

Support:

* normalized username/handle resolution;
* referenced user identity;
* invalid/deleted account handling;
* duplicate prevention;
* privacy-aware behavior;
* event emission where required.

Do not permit references to private or deleted accounts to bypass their privacy state.

Mention parsing must not trust arbitrary user identifiers supplied by the client.

Resolve mentions against authoritative account/profile state.

---

# SOUND / AUDIO REFERENCE

Implement the foundational backend representation for sound/audio references used by videos.

Support, as applicable:

* sound ID;
* name/title;
* creator/source metadata;
* source ownership/reference;
* visibility;
* moderation state;
* deletion state.

Do not implement a full music-rights management platform in this milestone.

However, the model and API must be capable of representing that a sound may become unavailable, restricted, or removed.

Videos must not continue exposing unavailable audio merely because they contain a stale reference.

---

# VIDEO VISIBILITY

Implement the video visibility model.

Support the project's applicable states such as:

* public;
* private;
* restricted;
* removed;
* deleted.

Visibility must be enforced server-side in every current-scope video retrieval API.

The backend must evaluate visibility together with:

* account state;
* ownership;
* block relationships;
* moderation state;
* deletion state.

---

# VIDEO RETRIEVAL

Implement bounded video retrieval endpoints required by this milestone.

Support:

* authenticated owner retrieval;
* public/authorized video retrieval;
* video metadata retrieval;
* playback-information retrieval where appropriate;
* creator-owned management retrieval.

Do not implement feed ranking or recommendation logic in this prompt.

Video retrieval must not expose:

* private metadata;
* storage credentials;
* internal moderation information;
* internal processing diagnostics.

---

# PLAYBACK AUTHORIZATION

Implement backend authorization for playback access.

Depending on the architecture, provide either:

* a short-lived signed media URL;
* a playback token;
* a controlled media-access response;
* another explicitly authorized mechanism.

Before granting playback access, evaluate:

* video existence;
* video lifecycle;
* publication/visibility;
* requester authorization;
* account state;
* block/privacy restrictions;
* moderation restrictions.

Playback access must expire appropriately.

Do not expose permanent public storage URLs for private or controlled content.

---

# CDN INTEGRATION BOUNDARY

Create the backend integration boundary needed for CDN-backed media delivery.

The backend must remain responsible for authorization while the CDN handles efficient content delivery.

The implementation must support:

* authorized asset references;
* cache-aware delivery;
* expiration;
* content invalidation requirements;
* restricted/deleted asset revocation strategy.

Do not assume CDN infrastructure has been provisioned.

Repository code may define configuration and integration behavior, but it must not claim live CDN provisioning without verification.

---

# MEDIA DELETION

Implement media deletion for content within this scope.

Deletion must consider:

* authoritative video state;
* media-asset records;
* source object;
* processed variants;
* thumbnails;
* previews;
* playback manifests;
* background jobs;
* Redis caches where relevant.

Separate immediate access revocation from eventual physical cleanup.

Once a video is deleted or removed, ordinary playback APIs must stop granting access even if object cleanup has not yet completed.

---

# ABANDONED UPLOAD CLEANUP

Implement cleanup for expired or abandoned upload intents.

Cleanup must:

* identify expired intents;
* revoke/disable access where applicable;
* safely delete temporary objects;
* prevent races with active processing;
* remain idempotent;
* emit useful operational metrics.

Do not scan unlimited historical rows in one job.

Use bounded batches.

---

# PROCESSING CLEANUP

Media workers must clean temporary processing artifacts safely.

Protect against:

* orphaned files;
* repeated retry accumulation;
* disk exhaustion;
* incomplete output;
* failed jobs leaving persistent temporary state.

Use deterministic temporary paths that cannot escape the intended processing workspace.

---

# DATABASE DESIGN

Implement required schema changes with real migrations.

Create appropriate indexes for:

* videos by creator;
* videos by publication state;
* videos by visibility;
* videos by lifecycle;
* asset lookup by video;
* upload-intent lookup;
* hashtag lookup;
* video-hashtag association;
* mention lookup where applicable;
* sound lookup;
* publication ordering where required.

Do not add unbounded JSON blobs for fields that require relational integrity unless there is a justified reason.

Use foreign keys and uniqueness constraints where appropriate.

---

# DATA CONSISTENCY

Use transactions where multiple state changes must remain atomic.

Examples include:

* publication-state changes;
* upload-intent completion;
* asset-to-video ownership association;
* deletion-state transitions;
* metadata updates requiring multiple relational writes.

Do not use distributed transactions across PostgreSQL and object storage.

Use explicit state machines, reconciliation, and retryable workflows instead.

---

# OBJECT STORAGE CONSISTENCY

Object storage and PostgreSQL are separate systems.

Design explicitly for partial failure.

Examples:

* database row created but object upload fails;
* object uploaded but completion callback fails;
* processing succeeds but database update fails;
* database says deleted but object cleanup is delayed.

The implementation must make these cases recoverable.

Use durable state, retries, reconciliation jobs, or equivalent mechanisms.

Do not assume cross-system atomicity.

---

# EVENT PUBLICATION

Emit events needed by downstream systems.

Relevant events may include:

* VideoCreated;
* VideoUploadAuthorized;
* VideoUploadCompleted;
* VideoProcessingStarted;
* VideoProcessingCompleted;
* VideoProcessingFailed;
* VideoPublished;
* VideoVisibilityChanged;
* VideoUpdated;
* VideoDeleted;
* HashtagAssociated;
* MentionCreated.

Use the project's canonical event envelope.

Events must include:

* event ID;
* type;
* version;
* entity/aggregate ID;
* producer;
* occurred-at;
* correlation ID where applicable;
* payload.

Do not place secrets or unnecessary private data into events.

---

# TRANSACTIONAL OUTBOX

Where a database transaction must reliably result in a downstream event, use the established transactional-outbox architecture.

At minimum ensure:

* the domain mutation and outbox record are persisted atomically;
* the publisher retries safely;
* duplicate publication is tolerated by consumers;
* failed publication is observable;
* old outbox records are eventually cleaned according to retention policy.

Do not claim exactly-once event processing.

---

# CACHE INVALIDATION

Invalidate or refresh relevant caches when:

* video visibility changes;
* publication state changes;
* metadata changes;
* deletion occurs;
* moderation restrictions take effect within current scope.

Avoid broad cache flushing.

Use targeted keys based on the project's Redis conventions.

Do not allow stale private/deleted content to remain accessible through cached responses.

---

# RATE LIMITING AND ABUSE CONTROLS

Apply bounded rate limits to:

* upload-intent creation;
* video creation;
* metadata mutation;
* publish requests;
* repeated processing requests where exposed;
* other abuse-prone endpoints within this scope.

Prevent attackers from using media processing as a resource-exhaustion vector.

Enforce:

* file-size limits;
* upload frequency limits;
* processing concurrency limits;
* creator quotas where defined;
* bounded retries.

---

# SECURITY

Protect this milestone against:

* IDOR;
* unauthorized upload completion;
* storage-key substitution;
* arbitrary object access;
* malicious media;
* command injection;
* SSRF through media metadata or provider URLs;
* path traversal;
* resource exhaustion;
* privilege escalation;
* private-content exposure;
* stale-access after deletion;
* replayed upload authorization;
* forged processing callbacks where callbacks exist.

All authorization must be server-side.

---

# MEDIA PROCESSOR ISOLATION

Media processing must be isolated from the primary API execution path.

Where supported by the repository/environment:

* use dedicated worker processes;
* restrict filesystem access;
* restrict network access where unnecessary;
* use resource limits;
* enforce execution timeouts;
* remove temporary files;
* reject unsafe inputs before expensive processing.

Do not run untrusted FFmpeg operations with unnecessary application privileges.

---

# OBSERVABILITY

Instrument the media/content backend for:

* upload-intent creation;
* upload completion;
* media validation;
* processing queue latency;
* processing duration;
* processing success/failure;
* transcoding failures;
* thumbnail generation;
* object-storage operations;
* publication latency;
* playback authorization;
* deletion/cleanup;
* retry counts;
* orphaned upload counts.

Use structured logs and metrics.

Propagate:

* request ID;
* correlation ID;
* job ID;
* event ID;
* trace context.

Never log:

* storage credentials;
* signed URLs in full where they contain sensitive authorization material;
* authentication tokens;
* private media contents;
* secrets.

Redact sensitive storage references where necessary.

---

# RELIABILITY

Handle failure of:

* PostgreSQL;
* Redis where used;
* object storage;
* media processing workers;
* background queues;
* CDN integration;
* event publishing.

Use:

* bounded retries;
* exponential backoff;
* idempotency;
* reconciliation;
* timeouts;
* durable state.

Do not retry CPU-heavy media work indefinitely.

Do not leave content permanently stuck in a transient processing state without a recoverable failure path.

---

# RECONCILIATION

Implement reconciliation logic where object storage and database state can diverge.

Examples include:

* DB says asset exists but object is missing;
* object exists without active DB ownership;
* processing output exists but DB state is stale;
* abandoned upload remains after expiry;
* deleted video retains media objects.

Reconciliation must be:

* bounded;
* idempotent;
* observable;
* safe to run repeatedly.

Do not silently delete objects when ownership is ambiguous.

---

# API ENDPOINTS

Implement the REST endpoints required by this milestone.

At minimum provide the operations necessary for:

## Video Management

* create video draft;
* retrieve owned video;
* update metadata;
* request upload authorization;
* complete upload;
* publish;
* change visibility;
* delete;
* retrieve authorized playback information.

## Metadata

* manage hashtags/associations;
* resolve mentions;
* associate supported sound/audio references where the current architecture permits creator selection.

The exact endpoint paths, request schemas, response schemas, status codes, and errors must follow the project's canonical API conventions.

Do not invent incompatible response structures.

---

# API VALIDATION

Validate:

* path parameters;
* query parameters;
* request bodies;
* identifiers;
* visibility values;
* lifecycle operations;
* caption length;
* hashtag format;
* mention references;
* sound references;
* upload constraints.

Never accept server-owned state fields directly from clients.

---

# IDEMPOTENCY

Implement idempotency or duplicate-safe semantics for operations where retries could otherwise cause duplicate state.

At minimum evaluate:

* upload-intent creation;
* upload completion;
* publication;
* deletion;
* visibility changes;
* media-processing job scheduling.

Use natural uniqueness constraints where they provide sufficient protection.

Do not introduce a global idempotency store unnecessarily.

---

# BACKGROUND JOB TESTING

Test:

* successful processing;
* invalid files;
* unsupported media;
* duplicate processing;
* retry behavior;
* timeout handling;
* partial output;
* object-storage failure;
* worker restart;
* duplicate job delivery;
* cleanup behavior.

Tests must validate real processing behavior where the environment supports it.

When FFmpeg is available, exercise representative real media fixtures rather than testing only mocks.

When an external storage provider is unavailable, use an appropriate isolated test storage implementation without pretending that production connectivity was tested.

---

# DATABASE TESTING

Test:

* video lifecycle transitions;
* ownership constraints;
* publication gating;
* upload-intent uniqueness;
* media-asset relationships;
* deletion state;
* hashtag associations;
* mention associations;
* sound references;
* concurrent state changes.

Use isolated test databases or transactional test fixtures appropriate to the repository.

---

# API TESTING

Test:

* unauthorized video access;
* unauthorized mutation;
* valid upload-intent creation;
* invalid upload requests;
* expired upload intents;
* invalid completion;
* valid publication;
* publication before processing;
* visibility enforcement;
* playback authorization;
* deletion behavior;
* stale/deleted access;
* malformed metadata;
* hashtag and mention validation.

Verify canonical:

* status codes;
* error structure;
* response shapes;
* authentication behavior;
* authorization behavior.

---

# SECURITY TESTING

Include explicit tests for:

* IDOR on video IDs;
* IDOR on upload intents;
* object-key substitution;
* playback access after deletion;
* playback access to private videos;
* unauthorized publication;
* malicious path values;
* unsafe media command arguments;
* upload-size bypass;
* duration-limit bypass;
* invalid MIME declarations;
* replay of expired upload authorization;
* rate-limit bypass attempts.

---

# PERFORMANCE REQUIREMENTS

Do not:

* synchronously transcode videos inside HTTP handlers;
* load entire media files into process memory unnecessarily;
* perform unbounded video queries;
* scan all historical upload intents for every cleanup operation;
* use unlimited worker concurrency.

Use:

* streaming/object-store transfers;
* bounded worker concurrency;
* batched cleanup;
* indexed queries;
* appropriate background processing.

Do not optimize through unsafe shortcuts.

---

# DOCUMENTATION

Update repository documentation to describe the actual implementation.

Document:

* video lifecycle;
* upload flow;
* media-processing pipeline;
* storage configuration;
* upload constraints;
* processing configuration;
* API endpoints;
* playback authorization;
* deletion behavior;
* background jobs;
* queue configuration;
* environment variables;
* required local media-processing dependencies;
* testing procedures;
* operational troubleshooting.

Document external dependencies accurately.

Do not claim that a real S3 bucket, CDN, cloud deployment, or production media-processing fleet exists unless it was actually verified.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* video persistence;
* video lifecycle/state machine;
* creator-owned video management;
* upload-intent persistence;
* secure upload authorization;
* object-storage integration abstraction;
* upload completion verification;
* media-asset persistence;
* media validation;
* media-processing orchestration;
* FFmpeg-based processing where the repository/environment supports it;
* video variants;
* thumbnails;
* playback authorization;
* publication gating;
* video metadata;
* captions;
* hashtags;
* mentions;
* sound/audio references;
* visibility controls;
* video deletion;
* media cleanup;
* abandoned-upload cleanup;
* processing reconciliation;
* content-related events;
* relevant background jobs;
* rate limits;
* observability;
* security controls;
* migrations;
* automated tests;
* implementation documentation.

This prompt does **not** implement:

* personalized feed generation;
* recommendation ranking;
* machine-learning pipelines;
* search/index infrastructure;
* likes;
* comments;
* replies;
* shares;
* favorites;
* notifications;
* creator analytics;
* full moderation workflows;
* complete administration tooling;
* web UI;
* mobile UI;
* production cloud provisioning;
* CDN infrastructure deployment;
* global disaster-recovery infrastructure.

Create only the interfaces or integration boundaries required for these future systems to consume the implemented content/media domain.

---

# COMPATIBILITY REQUIREMENTS

Preserve compatibility with:

* the account/authentication backend;
* social-graph visibility rules;
* future feed systems;
* future recommendation systems;
* future engagement systems;
* future search indexing;
* future moderation;
* future notifications;
* future analytics;
* web clients;
* mobile clients;
* infrastructure automation;
* QA automation.

Preserve the project's canonical:

* identifiers;
* timestamps;
* API errors;
* pagination;
* authorization model;
* video lifecycle;
* visibility states;
* event envelopes;
* queue/job conventions;
* Redis naming.

Do not create competing definitions.

---

# EXTERNAL ENVIRONMENT REALISM

This task may require:

* PostgreSQL;
* Redis;
* object storage;
* FFmpeg;
* local filesystem workspace.

Use available local/test infrastructure where possible.

If an external service is unavailable:

* do not fabricate successful operation;
* test repository-side behavior through appropriate isolated mechanisms;
* clearly report unavailable dependencies;
* distinguish local/test validation from provider connectivity.

Do not claim production deployment or provider provisioning.

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
8. Run media-processing tests.
9. Run queue/job tests.
10. Run security-focused tests.
11. Validate any machine-readable API/schema artifacts.
12. Validate representative real media processing where supported.
13. Inspect final generated media metadata.
14. Inspect the final diff.
15. Search for secrets and credentials.
16. Check for unintended unrelated changes.

Do not claim successful media processing if the required processing tool was unavailable.

Do not claim successful object-storage integration if the configured provider was not accessible.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* video modules implemented;
* database schema changes;
* migrations;
* upload-intent implementation;
* storage abstraction;
* media-processing workers;
* FFmpeg integration;
* video variants;
* thumbnail generation;
* playback authorization;
* publication/lifecycle changes;
* hashtag changes;
* mention changes;
* sound/audio changes;
* event changes;
* queue/job changes;
* Redis changes;
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

Do not claim external infrastructure was provisioned unless it was actually verified.

---

# DEFINITION OF DONE

This backend media/content milestone is complete only when:

* the repository was inspected;
* the video data model is implemented;
* the video lifecycle is explicit and enforced;
* invalid lifecycle transitions are rejected;
* creator ownership is enforced;
* upload intents are persisted;
* upload authorization is secure and time-bounded;
* object-storage access is scoped appropriately;
* uploads are validated server-side;
* media is treated as untrusted input;
* media-processing jobs are implemented;
* processing is asynchronous;
* processing jobs are idempotent;
* retry and failure behavior is defined and implemented;
* FFmpeg integration is real where available;
* processing resource usage is bounded;
* video variants are generated according to explicit configuration;
* thumbnails are generated and persisted;
* publication is gated on successful required processing;
* publication is retry-safe;
* captions are validated and persisted;
* hashtags are normalized and associated correctly;
* mentions resolve against authoritative users;
* sound/audio references are modeled and validated;
* visibility rules are enforced server-side;
* playback access is authorized;
* deleted/restricted content cannot continue receiving ordinary playback authorization;
* media cleanup exists;
* abandoned uploads can be reconciled and cleaned;
* object-storage/database divergence has a recovery path;
* relevant events are emitted through the canonical event architecture;
* relevant background jobs follow the canonical job contract;
* appropriate rate limits are enforced;
* observability is implemented;
* sensitive media/storage credentials are not logged;
* security tests exist;
* database tests exist;
* API tests exist;
* media-processing tests exist;
* queue/retry tests exist;
* migrations are reproducible;
* documentation reflects actual behavior;
* no pseudo-code remains within scope;
* no fake storage or fake media processing remains within scope;
* no hardcoded secrets exist;
* no unrelated major feature area was implemented;
* compatibility with future feed, recommendation, search, engagement, moderation, notification, client, and infrastructure work is preserved;
* validation failures are accurately reported;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into the complete TikTok-style platform.
