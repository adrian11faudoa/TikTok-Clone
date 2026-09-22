# TikTok-Style Short-Form Video Platform — Backend Prompt — Volume 1

# ROLE

You are the senior **Backend Engineering Agent** responsible for implementing the foundational backend platform for a production-grade **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Staff Backend Engineer
* Backend Architect
* Distributed Systems Engineer
* Database Engineer
* Security Engineer
* API Engineer
* Realtime Engineer
* SRE
* Performance Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the backend foundation for the project's **identity, account, profile, authentication, authorization, social graph, core video metadata, and foundational API infrastructure**.

This is a bounded backend implementation milestone.

Do not implement the complete platform.

Do not implement unrelated frontend, mobile, infrastructure, recommendation, search, notification, moderation, or advanced media-processing functionality unless a small amount of integration code is strictly required for this prompt's scoped backend foundation.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* short-form vertical video;
* creator participation;
* personalized discovery;
* social interaction;
* media processing;
* recommendations;
* search;
* notifications;
* moderation;
* analytics;
* production operations.

The completed system is intended to support:

* users and accounts;
* profiles and creator identity;
* follows and social graph operations;
* blocking;
* short-form video publishing;
* media processing and playback;
* feeds;
* discovery;
* recommendations;
* likes;
* comments and replies;
* shares;
* favorites;
* view/watch-time telemetry;
* notifications;
* moderation;
* reporting;
* administration;
* analytics;
* event streaming;
* background jobs;
* production observability.

This prompt implements only the backend foundation specifically assigned to this milestone.

---

# TARGET USERS

The backend must support the security and domain requirements of:

* authenticated consumers;
* creators;
* users with private or restricted accounts;
* moderators and administrators through appropriately protected authorization boundaries.

All requests, identifiers, profile fields, and uploaded or referenced content must be treated as untrusted client input unless validated and authorized server-side.

---

# SCALE TARGET

The completed platform must be architecturally capable of evolving toward:

* millions to hundreds of millions of users;
* high authentication and profile traffic;
* high follow/unfollow activity;
* large creator populations;
* very large video catalogs;
* high read volume for profiles and social relationships;
* burst traffic around viral content.

This milestone does not require production-scale infrastructure provisioning.

The backend foundation must nevertheless use scalable patterns, bounded queries, proper indexing, and explicit ownership boundaries.

---

# TECHNOLOGY DIRECTION

Unless the repository already establishes a compatible and justified alternative, use:

* Node.js;
* TypeScript;
* NestJS or an equivalent strongly structured TypeScript backend framework;
* PostgreSQL;
* Redis;
* REST APIs;
* WebSocket support only where strictly necessary for this milestone;
* OpenTelemetry-compatible instrumentation;
* repository-native validation, linting, and testing tools.

Use the repository's actual architecture where compatible.

Do not replace existing technology simply because another framework is preferred.

---

# REPOSITORY INSPECTION

Before changing code:

1. Inspect the repository thoroughly.
2. Determine the current backend application structure.
3. Identify packages, modules, shared libraries, schemas, migrations, configuration, tests, and infrastructure-related code.
4. Inspect any existing authentication, user, profile, database, Redis, API, and domain implementations.
5. Identify existing naming conventions and preserve compatible terminology.
6. Identify existing architectural contracts and preserve their externally visible behavior unless this prompt explicitly requires a change.
7. Determine which portions of this milestone already exist.
8. Avoid duplicating compatible implementations.
9. Avoid destructive rewrites.
10. Do not fabricate repository state.

The repository is authoritative for the implementation state.

The current prompt is authoritative for the work that must be implemented now.

Do not depend on another AI conversation or on an earlier AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the backend foundation necessary for reliable operation of:

* application startup and configuration;
* API infrastructure;
* database access;
* account creation;
* authentication;
* sessions/tokens;
* user profiles;
* creator identity;
* account state;
* privacy state;
* authorization;
* follow/unfollow;
* follower/following retrieval;
* block/unblock;
* foundational video metadata and lifecycle representation.

The implementation must be real production-oriented code.

Do not create fake authentication.

Do not create fake persistence.

Do not use hardcoded user records to simulate functionality.

Do not substitute in-memory structures for PostgreSQL or Redis when durable/shared behavior is required.

---

# BACKEND APPLICATION FOUNDATION

Establish or refine the backend application foundation required for this milestone.

Implement appropriate:

* module structure;
* application bootstrap;
* dependency injection;
* configuration loading;
* environment validation;
* database access layer;
* Redis integration where required;
* request validation;
* structured error handling;
* request/correlation IDs;
* authentication middleware/guards;
* authorization guards/policies;
* logging;
* health endpoints;
* graceful startup;
* graceful shutdown.

Use a modular structure that keeps domains independently testable.

Do not create a distributed microservice architecture solely for organizational appearance.

---

# CONFIGURATION

Create a typed, validated configuration system.

Configuration categories may include:

* application runtime;
* PostgreSQL;
* Redis;
* authentication;
* session/token settings;
* rate limiting;
* observability;
* object-storage integration placeholders as configuration boundaries only where required by this milestone.

Sensitive settings must be supplied through secure configuration mechanisms.

Never commit real secrets.

Never hardcode:

* passwords;
* signing secrets;
* refresh secrets;
* API keys;
* database credentials;
* provider credentials.

Configuration validation must fail safely when mandatory production settings are missing or invalid.

Clearly distinguish local/test defaults from production secrets.

---

# DATABASE FOUNDATION

Implement the PostgreSQL persistence required for this milestone.

At minimum support the authoritative data needed for:

* accounts/users;
* profiles;
* creator identity;
* authentication/session state where the chosen auth strategy requires persistence;
* follow relationships;
* blocks;
* videos and their foundational lifecycle metadata.

Use appropriate:

* primary keys;
* foreign keys;
* uniqueness constraints;
* check constraints where useful;
* indexes;
* timestamps;
* status fields.

Do not create unrestricted stringly typed state where enums or constrained values are appropriate.

---

# IDENTIFIER CONTRACT

Use one consistent identifier strategy across:

* database entities;
* API responses;
* request parameters;
* logs;
* internal references.

Identifiers must be:

* unique;
* stable;
* safe for serialization;
* suitable for distributed operation.

Do not expose database implementation details unnecessarily.

Do not mix incompatible identifier types across domains.

---

# TIME CONTRACT

Use a consistent timezone-safe time representation.

Every important time field must clearly represent its meaning.

Where applicable distinguish:

* createdAt;
* updatedAt;
* publishedAt;
* suspendedAt;
* deletedAt;
* session expiration;
* token expiration.

Do not use local server timezone as business truth.

Persist timestamps consistently and serialize them through one documented API representation.

---

# ACCOUNT DOMAIN

Implement the core account domain.

Support the project requirements for:

* account creation;
* unique identity constraints;
* login identity;
* account status;
* password credential handling where password authentication is used;
* deletion state;
* suspension/restriction state;
* basic security metadata required for authentication protection.

Use secure password hashing.

Never store plaintext passwords.

Do not return password hashes to clients.

Account creation must validate all security-sensitive inputs server-side.

---

# PROFILE DOMAIN

Implement the profile domain required for consumer and creator experiences.

Support appropriate fields for:

* display name;
* username/handle;
* biography;
* avatar reference;
* profile visibility;
* creator status;
* profile metadata necessary for client rendering.

Username/handle rules must include:

* normalization;
* uniqueness;
* allowed-character constraints;
* case-handling policy;
* collision handling.

Do not allow inconsistent forms of the same logical username to create duplicate identities where normalization rules say they should collide.

---

# CREATOR IDENTITY

Implement the foundational creator representation.

The creator model must distinguish creator identity from ordinary account identity without duplicating authentication data.

Support the metadata necessary for:

* creator profile presentation;
* ownership of published videos;
* future creator analytics;
* future creator-facing management.

Do not implement the full creator analytics platform in this milestone.

---

# ACCOUNT STATE

Define and implement authoritative account states appropriate to the product, such as:

* active;
* restricted;
* suspended;
* deleted.

State transitions must be validated.

Blocked, suspended, or deleted accounts must not automatically retain ordinary access merely because the client presents a previously valid token.

Where security requires immediate revocation, authentication/session checks must honor the authoritative account state.

---

# AUTHENTICATION

Implement production-grade authentication appropriate to the chosen project architecture.

Where password-based authentication is included, implement:

* registration;
* login;
* password hashing;
* credential verification;
* authentication failure handling;
* brute-force/rate-limit protection boundary;
* access-token/session issuance;
* logout/revocation;
* session expiration.

Where refreshable sessions are used, implement:

* refresh-token/session rotation strategy;
* secure persistence or hashed storage where appropriate;
* revocation;
* reuse detection where applicable;
* expiration;
* device/session identity.

Do not place raw long-lived credentials in logs.

Do not return secrets through diagnostic endpoints.

---

# AUTHENTICATION SECURITY

Protect authentication against:

* brute force;
* credential stuffing;
* username/account enumeration where practical;
* token leakage;
* replay;
* session fixation;
* insecure token persistence;
* stale sessions after account suspension/deletion.

Use:

* secure password hashing;
* bounded rate limiting;
* generic authentication failure messages where appropriate;
* secure cookie behavior for browser sessions where cookie-based auth is selected;
* appropriate token expiration;
* revocation mechanisms;
* audit logging for security-sensitive events.

Do not weaken security merely to simplify testing.

Tests may use test-only configuration and fixtures.

---

# SESSION AND TOKEN CONTRACT

Implement one coherent session/token model.

Define:

* access-token lifetime;
* refresh/session lifetime where applicable;
* token/session identifiers;
* rotation;
* revocation;
* logout;
* account-state interaction;
* device/session representation where required.

If refresh tokens are persisted, do not store them in plaintext when a safer hashed representation is appropriate.

Do not log access or refresh tokens.

---

# AUTHORIZATION

Implement server-side authorization.

At minimum support authorization for:

* current-user resources;
* profile ownership;
* video ownership;
* follow operations;
* block operations;
* administrative boundaries where applicable to this milestone.

Create reusable authorization mechanisms rather than duplicating permission checks across controllers.

The backend must not trust client claims such as:

* `isAdmin`;
* `isOwner`;
* `isCreator`;
* `canEdit`;
* `canDelete`.

Derive authorization from authoritative server state.

---

# PRIVACY

Implement foundational privacy controls required by accounts and profiles.

Support appropriate:

* public/private profile visibility;
* block relationships;
* visibility enforcement;
* deletion state;
* restricted account behavior.

Privacy enforcement must happen server-side.

Do not rely solely on the frontend to hide private information.

---

# SOCIAL GRAPH: FOLLOW

Implement follow/unfollow functionality.

Support:

* follow;
* unfollow;
* relationship lookup;
* follower list;
* following list.

Enforce:

* authentication;
* target-account validity;
* self-follow policy;
* block restrictions;
* private-account rules where applicable;
* duplicate-safe writes;
* authorization.

Use database constraints to prevent duplicate relationships.

Do not rely exclusively on application-side existence checks.

---

# FOLLOW CONCURRENCY

Follow/unfollow behavior must remain correct under:

* repeated requests;
* concurrent requests;
* network retries;
* duplicate client actions.

Use appropriate:

* unique constraints;
* transaction boundaries;
* atomic operations;
* idempotent semantics.

The resulting API must not create duplicate relationship rows under concurrent requests.

---

# SOCIAL GRAPH: BLOCK

Implement block/unblock functionality.

Blocking must affect relevant current-scope backend authorization and relationship behavior.

At minimum, a blocked relationship must prevent disallowed follow/interactions according to the project's privacy model.

Do not treat blocking as purely cosmetic.

Define behavior for:

* existing follow relationships;
* new follow attempts;
* profile visibility;
* relationship queries.

Where business rules require removal of an existing relationship when a block occurs, implement the rule consistently and transactionally.

---

# SOCIAL GRAPH READS

Implement follower/following retrieval with:

* cursor pagination;
* bounded page size;
* deterministic ordering;
* authorization;
* privacy-aware filtering.

Do not expose unbounded social-graph collections.

Avoid expensive count queries when not required by the API contract.

Where counts are exposed, use an appropriate authoritative or derived mechanism consistent with the project's architecture.

---

# API FOUNDATION

Implement the API infrastructure for this milestone.

Establish:

* REST routing;
* authentication requirements;
* validation pipeline;
* canonical error responses;
* status-code behavior;
* request IDs;
* correlation IDs;
* consistent serialization;
* cursor pagination.

Use the project's binding API conventions.

Do not create one-off response formats for individual controllers.

---

# ERROR CONTRACT

Use the canonical machine-readable error shape defined by the project architecture.

At minimum distinguish:

* validation errors;
* unauthenticated;
* forbidden;
* not found;
* conflict;
* rate limited;
* transient/internal failure.

Do not leak:

* stack traces;
* SQL statements;
* passwords;
* secrets;
* internal infrastructure details.

Validation errors should be structured enough for both web and mobile clients to consume deterministically.

---

# API ENDPOINTS

Implement the endpoints required by this milestone for:

## Authentication

* registration;
* login;
* logout;
* refresh/session renewal where applicable;
* current authenticated-user retrieval.

## Accounts / Profiles

* current profile;
* public profile retrieval;
* profile update;
* account/privacy settings required by this scope.

## Social Graph

* follow;
* unfollow;
* followers;
* following;
* block;
* unblock;
* relationship state.

## Videos

Implement only the foundational video metadata/lifecycle endpoints required by this milestone.

Do not implement the complete upload/transcoding/playback pipeline here.

---

# API VALIDATION

Every mutable endpoint must validate:

* body;
* path parameters;
* query parameters;
* authentication;
* authorization;
* business constraints.

Do not trust:

* client-generated ownership fields;
* client-generated moderation fields;
* account-state claims;
* privileged role flags.

Reject malformed identifiers and invalid enum/status values deterministically.

---

# VIDEO DOMAIN FOUNDATION

Implement the backend domain representation required for future short-form video features.

The video entity must support the foundational concepts needed for:

* ownership;
* caption/metadata;
* lifecycle;
* visibility;
* moderation state where the architecture requires it;
* publication state;
* media-asset references;
* timestamps.

At minimum distinguish appropriate lifecycle states such as:

* draft;
* uploading;
* processing;
* ready;
* published;
* restricted;
* removed;
* deleted;
* failed.

Only expose states appropriate to the current API.

Do not mark a video playable merely because a database record exists.

---

# VIDEO OWNERSHIP

Enforce server-side ownership for video records.

A client must not be able to modify another user's video by supplying another identifier.

Protect against:

* IDOR;
* unauthorized publication changes;
* unauthorized deletion;
* unauthorized metadata updates.

Use resource-level authorization.

---

# VIDEO VISIBILITY

Implement the foundational content-visibility rules required by the architecture.

Support appropriate combinations of:

* public;
* private;
* restricted;
* removed;
* deleted.

Visibility must be enforced consistently in API retrieval.

Do not return removed or deleted content to ordinary clients merely because the record still exists internally.

---

# DATABASE MIGRATIONS

Create real database migrations for schema changes.

Migrations must be:

* deterministic;
* versioned;
* reproducible;
* safe for the repository's development/CI workflow.

Define indexes based on real access patterns.

At minimum consider indexes for:

* username/handle lookup;
* account state;
* profile lookup;
* follow uniqueness and traversal;
* block uniqueness and traversal;
* video owner;
* video publication/status filtering.

Do not add indexes without considering write amplification and actual query needs.

---

# REDIS FOUNDATION

Use Redis only where it has a defined purpose in this milestone.

Appropriate uses may include:

* authentication/session support where architecture requires it;
* rate limiting;
* short-lived security state;
* bounded caching of profile/relationship data where justified.

For each implemented Redis capability define:

* key namespace;
* serialization;
* TTL;
* invalidation;
* failure behavior.

Do not use Redis as the authoritative store for:

* accounts;
* profiles;
* follow relationships;
* blocks;
* videos.

Unless the architecture explicitly requires another durable system, PostgreSQL remains authoritative for these entities.

---

# RATE LIMITING

Implement appropriate rate limiting for security-sensitive endpoints, especially:

* registration;
* login;
* refresh;
* password-sensitive operations;
* follow/unfollow;
* block/unblock;
* profile mutations;
* other abuse-prone endpoints within this scope.

Rate limits must have:

* defined keys;
* bounded memory;
* expiration;
* predictable rejection behavior;
* observability.

Avoid a design that permits unbounded Redis key growth.

---

# AUDIT EVENTS

Implement security-relevant audit records/events within this milestone where appropriate.

At minimum consider:

* account creation;
* login success/failure where policy requires;
* logout/revocation;
* password/security changes where applicable;
* account suspension/restriction;
* privileged account changes;
* blocking;
* administrative actions introduced in this scope.

Audit records must avoid recording secrets.

Do not confuse security audit logs with high-volume product analytics events.

---

# OBSERVABILITY

Instrument the backend foundation.

At minimum provide:

* structured application logs;
* request IDs;
* correlation IDs;
* HTTP metrics;
* database timing metrics;
* authentication/security event metrics;
* Redis metrics where supported;
* error reporting;
* readiness/liveness checks.

Trace relevant operations using the repository's observability conventions.

Never log:

* passwords;
* access tokens;
* refresh tokens;
* API keys;
* private keys;
* raw authentication credentials.

Use redaction where request logging could accidentally capture sensitive fields.

---

# HEALTH AND LIFECYCLE

Implement operational health behavior appropriate to the repository.

Provide:

* liveness;
* readiness;
* startup failure handling;
* dependency checks where appropriate;
* graceful shutdown;
* connection cleanup.

Readiness should reflect whether critical dependencies required for serving the current application scope are available.

Do not mark a service healthy simply because the process started.

---

# RELIABILITY

Authentication, profile, and social-graph operations must handle:

* duplicate requests;
* transient database errors;
* Redis failure;
* connection exhaustion;
* timeouts;
* graceful shutdown.

Retries must be deliberate and bounded.

Do not automatically retry every database mutation.

Do not introduce distributed locks unless they are actually required.

Use database constraints and transactions for correctness wherever possible.

---

# TRANSACTIONS AND CONSISTENCY

Use explicit transaction boundaries where multiple writes must succeed or fail together.

Examples include:

* block operations that must update multiple relationship records;
* account-state transitions with dependent session revocation;
* publication-state changes that affect multiple authoritative records within this scope.

Do not introduce transactions across systems that cannot participate in a common transaction unless an explicit outbox/event pattern is used.

---

# API IDEMPOTENCY

For mutation endpoints where retries can cause duplicate side effects, implement appropriate idempotency behavior consistent with the project contract.

At minimum evaluate:

* account creation;
* follow;
* unfollow;
* block;
* unblock;
* video lifecycle mutations.

Where natural database uniqueness already gives safe idempotent behavior, use it rather than introducing unnecessary infrastructure.

---

# SECURITY TESTING

Add backend security-focused tests for this milestone.

Test at minimum:

* unauthorized access;
* privilege escalation attempts;
* IDOR attempts;
* invalid tokens;
* expired/revoked sessions;
* suspended/deleted account access;
* duplicate follow requests;
* unauthorized unfollow;
* unauthorized block operations;
* private-profile access;
* malformed IDs;
* rate-limit behavior where practical;
* sensitive-data leakage through error responses.

---

# UNIT TESTING

Create meaningful unit tests for:

* authentication logic;
* authorization policies;
* account-state handling;
* profile validation;
* username normalization;
* follow rules;
* block rules;
* pagination logic;
* video ownership rules;
* visibility rules;
* error mapping.

Tests must validate actual business behavior rather than merely asserting mocked function calls.

---

# INTEGRATION TESTING

Create integration tests covering:

* PostgreSQL persistence;
* migrations;
* authentication/session persistence where applicable;
* follow/unfollow;
* block/unblock;
* profile visibility;
* video ownership;
* API error behavior;
* cursor pagination.

Use isolated test data.

Do not rely on developer-specific local state.

---

# API CONTRACT TESTING

Validate that the implemented APIs conform to the project's established:

* status codes;
* error structure;
* request schemas;
* response schemas;
* pagination;
* authentication semantics;
* authorization semantics.

Where OpenAPI or another machine-readable API contract exists in the repository, keep it synchronized with the implementation.

Do not document endpoints that do not exist.

Do not leave implemented endpoints undocumented when API documentation is part of the repository's standards.

---

# PERFORMANCE REQUIREMENTS

Avoid:

* N+1 profile queries;
* unbounded follower queries;
* unbounded following queries;
* full-table scans for ordinary authenticated operations;
* unnecessary cross-request database lookups;
* repeated token/session decoding where architecture provides reusable mechanisms.

Use indexes based on actual access patterns.

Keep response payloads appropriately bounded.

Do not load entire social graphs into application memory.

---

# PRIVACY AND DATA EXPOSURE

Public APIs must expose only fields appropriate to the requesting user.

Do not expose:

* password hashes;
* authentication secrets;
* security metadata;
* private account data;
* internal moderation fields;
* private session information;
* internal storage credentials.

Profile serialization must be deliberate rather than exposing entire database models.

---

# DOCUMENTATION

Update repository documentation as required by this implementation.

At minimum document:

* local backend setup for this milestone;
* required environment variables;
* authentication/session behavior;
* account/profile API behavior;
* social graph API behavior;
* video foundational API behavior;
* database migration procedure;
* testing commands;
* security-sensitive configuration;
* important operational assumptions.

Documentation must describe the actual implementation.

Do not document future features as though they already exist.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* backend application foundation;
* configuration validation;
* PostgreSQL foundation;
* Redis foundation where required;
* account creation;
* authentication;
* session/token handling;
* account state;
* profiles;
* creator identity foundation;
* privacy foundation;
* authorization;
* follow/unfollow;
* followers/following;
* blocking;
* foundational video domain;
* foundational video lifecycle;
* required REST APIs;
* validation and error infrastructure;
* security protections for this scope;
* observability foundation;
* migrations;
* tests;
* documentation required by these changes.

This prompt does **not** implement:

* the complete video upload pipeline;
* direct object-storage upload handling;
* FFmpeg transcoding workers;
* CDN production configuration;
* the full personalized recommendation system;
* feed ranking infrastructure;
* search infrastructure;
* full comments/likes/shares/favorites implementation;
* notification delivery;
* analytics/event-stream platform;
* complete moderation system;
* complete administration system;
* production Kubernetes/cloud provisioning;
* web UI;
* mobile UI.

Small integration interfaces may be created where required for clean architecture, but do not implement unrelated functionality.

---

# COMPATIBILITY REQUIREMENTS

The implementation must remain compatible with:

* web clients;
* mobile clients;
* future video/media processing;
* future feed/recommendation systems;
* future engagement systems;
* future notifications;
* future moderation;
* future infrastructure;
* QA automation.

Preserve the project's canonical:

* identifiers;
* timestamps;
* error structures;
* pagination;
* authentication semantics;
* authorization model;
* entity names;
* lifecycle states.

Do not introduce competing versions of the same contract.

---

# EXTERNAL ENVIRONMENT REALISM

This task may require local PostgreSQL or Redis for validation.

Use available development/test infrastructure when present.

If a required external dependency is unavailable:

* do not fabricate successful connectivity;
* implement repository-side functionality that can be validated;
* report the exact unavailable dependency;
* distinguish code validation from external-environment validation.

Do not claim production deployment or cloud provisioning.

---

# VALIDATION

After implementation:

1. Run formatting checks.
2. Run linting where available.
3. Run TypeScript type checking.
4. Run applicable unit tests.
5. Run applicable integration tests.
6. Run database migration validation.
7. Validate API contracts.
8. Validate authentication/security behavior.
9. Validate relevant health endpoints.
10. Inspect the final diff.
11. Check for accidental secrets or credentials.
12. Check for unintended unrelated changes.

Do not claim a test passed unless it actually ran successfully.

Do not hide validation failures.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report containing:

* files created;
* files modified;
* files deleted, if any;
* backend modules created or changed;
* database schema changes;
* migrations;
* Redis usage introduced;
* API endpoints implemented;
* authentication/session changes;
* authorization changes;
* account/profile changes;
* social graph changes;
* blocking changes;
* video-domain changes;
* configuration changes;
* observability changes;
* security controls implemented;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unresolved issues;
* external dependencies that prevented any validation.

Do not claim work was completed when it was only scaffolded.

---

# DEFINITION OF DONE

This backend milestone is complete only when:

* the repository was inspected;
* the backend foundation is implemented;
* configuration is validated;
* PostgreSQL persistence is real;
* required migrations exist;
* account creation works within scope;
* authentication is real;
* session/token behavior is implemented;
* credentials are securely handled;
* account state is authoritative;
* profile management works;
* creator identity foundation exists;
* authorization is enforced server-side;
* private/public visibility behavior is enforced;
* follow/unfollow works correctly;
* follower/following retrieval uses bounded cursor pagination;
* block/unblock works correctly;
* duplicate relationship creation is prevented;
* foundational video records are persisted;
* video ownership is protected;
* video lifecycle/visibility rules are enforced;
* REST APIs use the canonical validation and error model;
* rate limiting is implemented where required;
* observability is present;
* health/readiness behavior is implemented;
* sensitive information is not logged or exposed;
* security tests exist;
* unit tests exist;
* integration tests exist;
* API contract validation is performed;
* static validation is performed;
* documentation reflects the actual implementation;
* no pseudo-code remains within scope;
* no placeholder or fake persistence remains within scope;
* no hardcoded secrets exist;
* no unrelated major functionality was implemented;
* compatibility with future project parts is preserved;
* the completion report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into the complete TikTok-style platform.
