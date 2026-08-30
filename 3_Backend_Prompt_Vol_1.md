You are operating in Senior Engineering Team Mode.

Build the production-ready backend foundation for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The backend must follow the approved TikTok-like architecture, domain boundaries, service ownership, database architecture, video architecture, feed architecture, recommendation architecture, search architecture, security model, event architecture, queue architecture, and Project Index.

Do not redesign the architecture.

Do not generate frontend code.

Do not generate mobile code.

Do not generate infrastructure implementation code.

Do not generate Terraform.

Do not generate Kubernetes manifests.

Do not generate CI/CD workflows.

────────────────────────────────────────

MISSION

Build the production-ready backend foundation required for:

• API Gateway
• Application bootstrap
• Configuration
• Request context
• Structured logging
• Error handling
• Validation
• Authentication foundation
• Authorization foundation
• PostgreSQL
• Prisma
• Redis
• Kafka/Redpanda
• BullMQ
• WebSockets
• Socket.IO
• OpenTelemetry
• Metrics
• Health checks
• Graceful shutdown
• API contracts
• Event contracts
• Queue contracts
• Testing foundation
• Local development

This volume establishes the backend platform required by all later video-social domains.

The complete backend must eventually support:

• Users
• Profiles
• Creators
• Creator verification
• Follows
• Followers
• Blocking
• Videos
• Uploads
• Video processing
• Transcoding
• Media packaging
• Thumbnails
• Captions
• Sounds
• Hashtags
• Mentions
• Likes
• Comments
• Shares
• Saves
• Collections
• Reposts
• Feeds
• Recommendations
• Ranking
• Trending
• Search
• Messaging
• Notifications
• Moderation
• Safety
• Reporting
• Rights
• Advertising
• Analytics
• Creator analytics
• Administration
• Privacy
• Feature flags
• Dynamic configuration
• Audit
• Multi-region operation

────────────────────────────────────────

PRIMARY TECHNOLOGY STACK

Backend:

• Node.js
• NestJS
• TypeScript

Database:

• PostgreSQL
• Prisma ORM

Cache:

• Redis

Event Streaming:

• Kafka or Redpanda

Background Processing:

• BullMQ

Search:

• Elasticsearch or OpenSearch

Object Storage:

• AWS S3

CDN:

• CloudFront

Video Processing:

• FFmpeg
• Queue-driven workers

Real-Time:

• WebSockets
• Socket.IO

Notifications:

• Firebase Cloud Messaging
• Apple Push Notification Service

Observability:

• OpenTelemetry
• Prometheus
• Grafana
• Loki
• Tempo

Testing:

• Jest
• Supertest
• Integration testing tools

────────────────────────────────────────

IMPLEMENTATION RULES

Never generate pseudo-code.

Never generate placeholders.

Never generate TODO comments.

Never omit implementations.

Never say:

- "implement similarly"
- "left as an exercise"
- "for brevity"
- "remaining code omitted"

Every generated file must be complete.

Every generated file must compile.

Never regenerate unchanged files.

Only modify existing files when required.

Use strict TypeScript.

Use dependency injection.

Keep controllers thin.

Keep business logic outside controllers.

Use repositories for persistence.

Use DTOs for external contracts.

Use centralized validation.

Use centralized error handling.

Use structured logging.

Use safe timeout and retry policies.

Use idempotency where operations may be retried.

Use the established observability infrastructure.

────────────────────────────────────────

BACKEND ARCHITECTURE

Use:

• Clean Architecture
• Domain-Driven Design
• SOLID
• Repository Pattern
• Service Layer
• Dependency Injection
• Feature-first organization
• Explicit domain ownership
• CQRS where justified
• Event-driven communication where appropriate
• Transactional Outbox where appropriate
• Idempotent consumers
• Stateless services where possible
• Horizontal scalability

Do not create unnecessary microservices.

The implementation must permit future extraction of high-scale domains such as:

• Video processing
• Feed
• Recommendations
• Search
• Messaging
• Moderation
• Analytics

────────────────────────────────────────

MONOREPO BACKEND FOUNDATION

Create the backend structure required by the approved architecture.

Support:

apps/

• API Gateway

services/

Prepare service boundaries for:

• Identity
• Accounts
• Profiles
• Creators
• Creator Verification
• Social Graph
• Videos
• Upload
• Video Processing
• Transcoding
• Packaging
• Thumbnails
• Captions
• Sounds
• Hashtags
• Engagement
• Comments
• Sharing
• Collections
• Reposts
• Feed
• Feed Candidates
• Ranking
• Recommendations
• Trending
• Search
• Messaging
• Notifications
• Moderation
• Safety
• Reporting
• Rights
• Advertising
• Analytics
• Creator Analytics
• Administration
• Audit
• Feature Flags
• Configuration
• Privacy

workers/

• Video workers
• Search workers
• Feed workers
• Recommendation workers
• Moderation workers
• Notification workers
• Analytics workers
• Privacy workers

packages/

• Configuration
• Logging
• Errors
• Validation
• Database
• Redis
• Events
• Queues
• Observability
• API contracts
• Media abstractions
• Storage abstractions
• Search abstractions
• Testing utilities

────────────────────────────────────────

APPLICATION BOOTSTRAP

Implement NestJS application initialization.

Support:

• Environment loading
• Configuration
• Global validation
• Global exception handling
• Structured logging
• Request IDs
• Correlation IDs
• Trace IDs
• Secure headers
• CORS
• Request-size limits
• API versioning
• Graceful shutdown
• Health checks
• OpenAPI

Use production-safe defaults.

────────────────────────────────────────

CONFIGURATION

Implement centralized strongly typed configuration.

Support:

APPLICATION

• Environment
• Service name
• Version
• Host
• Port
• Region

POSTGRESQL

• Host
• Port
• Database
• Username
• Password
• TLS
• Connection pool

REDIS

• Host
• Port
• Username
• Password
• TLS

KAFKA / REDPANDA

• Brokers
• Client ID
• Authentication
• TLS
• Consumer groups

BULLMQ

• Redis configuration
• Retry defaults
• Queue defaults

S3

• Bucket
• Region
• Endpoint where appropriate

CLOUDFRONT

• Distribution configuration
• Public media domain

SEARCH

• Endpoint
• Credentials
• Index configuration

VIDEO

• Processing limits
• Upload limits
• Supported formats
• Maximum duration

OBSERVABILITY

• Log level
• OpenTelemetry endpoint
• Metrics configuration

NOTIFICATIONS

• FCM configuration
• APNS configuration

Never hard-code secrets.

Never access process.env throughout domain modules.

Validate all required configuration at startup.

Fail fast for invalid configuration.

────────────────────────────────────────

REQUEST CONTEXT

Implement reusable request context containing:

• Request ID
• Correlation ID
• Trace ID
• Service
• Environment
• Region
• User ID where authenticated
• Creator ID where applicable
• Device ID
• Client platform
• Client version

Propagate context to:

• Logs
• Metrics
• Traces
• Kafka events
• Background jobs
• External requests

────────────────────────────────────────

LOGGING

Implement structured JSON logging.

Support:

• Timestamp
• Service
• Environment
• Region
• Log level
• Request ID
• Correlation ID
• Trace ID
• Operation
• Duration
• Result
• Safe error information

Never log:

• Passwords
• Access tokens
• Refresh tokens
• Private messages
• Signed playback credentials
• S3 credentials
• Search credentials
• Private behavioral data unnecessarily
• Security-sensitive moderation data unnecessarily

────────────────────────────────────────

ERROR HANDLING

Implement centralized API error handling.

Define errors for:

• Validation
• Authentication
• Authorization
• Not found
• Conflict
• Rate limit
• Payload too large
• Unsupported media
• Dependency unavailable
• External-provider failure
• Upload failure
• Processing failure
• Moderation failure
• Internal error

Use a consistent error response:

• Error code
• Public-safe message
• Request ID
• Correlation ID
• Validation details where appropriate

Never expose stack traces in production responses.

────────────────────────────────────────

VALIDATION

Implement centralized validation for:

• Request bodies
• Query parameters
• Path parameters
• Headers
• Configuration
• Event payloads
• Queue payloads
• Webhook payloads
• Upload metadata

Validate:

• File size
• MIME type
• Duration
• Resolution metadata
• Content identifiers
• Pagination
• Cursor values

Reject clearly invalid input.

────────────────────────────────────────

API FOUNDATION

Implement reusable REST API infrastructure.

Support:

• API versioning
• Request validation
• Response conventions
• Error conventions
• Pagination
• Cursor pagination
• Authentication
• Authorization
• Rate limiting
• OpenAPI
• Request tracing
• Timeout handling
• Cancellation
• Idempotency

Create reusable abstractions for:

• Idempotency keys
• Resource versions
• Optimistic concurrency
• Safe retries

────────────────────────────────────────

SECURITY FOUNDATION

Implement:

• Authentication guards
• Authorization guards
• RBAC foundation
• Permission foundation
• Rate limiting foundation
• Secure headers
• CORS
• Audit hooks

Prepare for:

• Password authentication
• OAuth
• MFA
• Passkeys
• Session management
• Device authentication

Never store plaintext passwords.

────────────────────────────────────────

DATABASE FOUNDATION

Implement PostgreSQL integration using Prisma.

Support:

• Prisma client lifecycle
• Connection handling
• Health checks
• Graceful shutdown
• Transactions
• Error translation
• Query logging controls
• Migration structure

Prepare for:

• Large tables
• Partitioning
• Read replicas
• Connection pooling
• Background archival

Do not create the complete domain schema in this volume.

────────────────────────────────────────

PRISMA FOUNDATION

Define conventions for:

• Primary IDs
• Public IDs where needed
• Created timestamps
• Updated timestamps
• Soft deletion where justified
• Optimistic concurrency
• Foreign keys
• Unique constraints
• Composite indexes

Prepare ownership boundaries between domains.

Do not permit arbitrary cross-domain writes.

────────────────────────────────────────

REDIS FOUNDATION

Implement reusable Redis infrastructure.

Support:

• Connection management
• TLS
• Authentication
• Health checks
• Graceful shutdown
• Namespaced keys
• Serialization
• TTL
• Cache abstraction
• Short-lived lease abstraction
• Idempotency
• Rate limiting
• Distributed coordination

Prepare for:

• Feed cache
• Recommendation cache
• Trending
• Upload sessions
• WebSocket coordination
• Notification deduplication
• Rate limits

Redis must never be authoritative for:

• Users
• Creators
• Videos
• Rights
• Moderation
• Financial data
• Privacy records

────────────────────────────────────────

REDIS KEY CONVENTIONS

Create standardized namespaces:

• feed:
• recommendation:
• trending:
• upload:
• video:
• search:
• notification:
• messaging:
• moderation:
• rate-limit:
• websocket:
• idempotency:

Keys should include appropriate:

• Environment
• Region
• Entity scope

Define:

• TTL
• Serialization
• Ownership
• Invalidation

────────────────────────────────────────

KAFKA / REDPANDA FOUNDATION

Implement reusable event infrastructure.

Support:

• Producer lifecycle
• Consumer lifecycle
• Topic configuration
• Consumer groups
• Serialization
• Event IDs
• Event versions
• Correlation IDs
• Causation IDs where appropriate
• Retry
• Dead-letter handling
• Graceful shutdown

Define a standard event envelope:

• Event ID
• Event type
• Event version
• Aggregate type
• Aggregate ID
• Region
• Timestamp
• Correlation ID
• Causation ID where appropriate
• Producer
• Payload

Do not implement the complete domain event catalog yet.

────────────────────────────────────────

TRANSACTIONAL OUTBOX

Implement reusable outbox infrastructure.

Support:

• Outbox ID
• Event type
• Event version
• Aggregate type
• Aggregate ID
• Region
• Payload
• Status
• Retry count
• Next retry
• Published timestamp
• Error information
• Created timestamp

Ensure transactional consistency between:

• Database state change
• Durable event creation

Support recovery when Kafka publication fails.

Publishing must be retryable and idempotent.

────────────────────────────────────────

BULLMQ FOUNDATION

Implement reusable job infrastructure.

Support:

• Queue registration
• Producer
• Worker
• Job IDs
• Retry
• Exponential backoff
• Timeout
• Concurrency
• Failure handling
• Dead-letter behavior
• Graceful shutdown
• Metrics

Prepare queues for:

• Video processing
• Transcoding
• Thumbnail generation
• Captions
• Moderation
• Search indexing
• Feed refresh
• Recommendation refresh
• Trending
• Notifications
• Analytics
• Privacy

Do not implement full domain jobs yet.

────────────────────────────────────────

WEBSOCKET FOUNDATION

Implement production-ready WebSocket infrastructure.

Support:

• Connection establishment
• Authentication
• Authorization
• Heartbeats
• Reconnection
• Disconnect handling
• Connection metadata
• Region awareness
• Room/channel abstraction
• Rate limiting
• Backpressure

Prepare channels for:

• Notifications
• Messaging
• Processing status
• Creator analytics
• Moderation updates where appropriate
• Live engagement where supported

────────────────────────────────────────

SOCKET.IO FOUNDATION

Where Socket.IO is approved:

Implement:

• Gateway lifecycle
• Authentication middleware
• Connection tracking
• Room abstraction
• Event validation
• Error handling
• Heartbeats
• Rate limiting
• Graceful shutdown

Prepare horizontal scaling with Redis coordination.

────────────────────────────────────────

OBJECT STORAGE FOUNDATION

Implement reusable S3 integration.

Support:

• Bucket abstraction
• Object key generation
• Upload authorization
• Object metadata
• Head/check
• Delete
• Presigned upload URLs
• Presigned multipart operations where needed
• Secure download authorization

Never return permanent public credentials.

Do not expose raw cloud credentials to clients.

────────────────────────────────────────

MEDIA STORAGE NAMING

Create standardized object-key conventions.

Separate:

• uploads/
• processing/
• masters/
• renditions/
• manifests/
• segments/
• thumbnails/
• posters/
• previews/
• captions/
• creator-assets/
• exports/

Include:

• Region
• Content ID
• Version where appropriate

Avoid user-controlled path traversal.

────────────────────────────────────────

MEDIA SECURITY FOUNDATION

Validate:

• MIME type
• File extension
• File signature
• Size
• Upload session
• Owner
• Region

Prepare integration boundaries for malware scanning.

Do not assume client MIME type is trustworthy.

────────────────────────────────────────

UPLOAD FOUNDATION

Implement backend support for upload sessions.

Support:

• Upload initialization
• Multipart upload
• Resume
• Status
• Completion
• Cancellation
• Expiration

An upload session must include:

• Upload ID
• User ID
• Video ID
• Object key
• Expected size
• State
• Expiration
• Region

States:

• Created
• Uploading
• Completing
• Completed
• Failed
• Canceled
• Expired

Do not implement full transcoding in this volume.

────────────────────────────────────────

VIDEO METADATA FOUNDATION

Create foundational models/services for:

• Video
• Metadata
• Visibility
• Publication state

Prepare states:

• Draft
• Uploading
• Processing
• Moderation
• Published
• Restricted
• Removed
• Archived
• Deleted

Only create the minimum schema needed for the foundation.

────────────────────────────────────────

SEARCH ABSTRACTION

Create provider-neutral interfaces for:

• Index
• Upsert
• Update
• Delete
• Search
• Suggest
• Bulk indexing

Do not allow OpenSearch/Elasticsearch-specific objects to leak into domain contracts.

────────────────────────────────────────

NOTIFICATION ABSTRACTION

Create provider-neutral interfaces for:

• Push
• Email
• SMS where approved

Support:

• Provider normalization
• Timeout
• Retry classification
• Error normalization

Do not implement all notification business rules in this volume.

────────────────────────────────────────

MEDIA PROCESSING ABSTRACTION

Create interfaces for:

• Validate media
• Extract metadata
• Transcode
• Generate thumbnail
• Generate preview
• Generate captions
• Package streaming assets
• Validate output

Do not execute heavy FFmpeg work synchronously inside API requests.

────────────────────────────────────────

VIDEO PROCESSING JOB CONTRACT

Define a reusable job model containing:

• Job ID
• Video ID
• Asset ID
• Job type
• Input reference
• Output references
• Region
• Priority
• Retry count
• Created timestamp
• Deadline where applicable

Support idempotent processing.

────────────────────────────────────────

HEALTH CHECKS

Implement:

• Liveness
• Readiness
• Startup health where appropriate

Support checks for:

• PostgreSQL
• Redis
• Kafka
• BullMQ infrastructure
• S3 configuration
• Search where required

Do not make liveness fail because a third-party service is temporarily unavailable.

────────────────────────────────────────

GRACEFUL SHUTDOWN

Implement shutdown support for:

• HTTP server
• WebSocket gateways
• NestJS modules
• Prisma
• Redis
• Kafka producers
• Kafka consumers
• BullMQ workers
• S3 clients

Stop accepting new work before closing dependencies.

Handle active requests and background jobs safely.

────────────────────────────────────────

OBSERVABILITY

Implement:

• Structured logging
• Metrics
• Distributed tracing
• Correlation IDs
• Request latency
• Error metrics
• Database metrics
• Redis metrics
• Kafka metrics
• Queue metrics
• WebSocket metrics
• Upload metrics

Use:

• OpenTelemetry
• Prometheus-compatible metrics

Prepare metrics for:

• API traffic
• Upload initialization
• Upload completion
• Video processing
• Search
• Feed
• Recommendation
• Notifications
• Messaging

────────────────────────────────────────

API CONTRACT FOUNDATION

Create shared conventions for:

• Resource naming
• Request DTOs
• Response DTOs
• Errors
• Pagination
• Cursor pagination
• Idempotency
• Versioning

Prepare contracts for:

• Users
• Profiles
• Creators
• Videos
• Uploads
• Feeds
• Search
• Engagement
• Messaging
• Notifications
• Moderation

Do not implement domain business logic in contract packages.

────────────────────────────────────────

EVENT CONTRACT FOUNDATION

Create reusable conventions for:

• Event naming
• Event versioning
• Metadata
• Producer ownership
• Payload validation
• Compatibility

Prepare for future events such as:

• VideoPublished
• VideoViewed
• VideoLiked
• CommentCreated
• FollowCreated
• RecommendationServed
• SearchPerformed

Do not build the full event catalog yet.

────────────────────────────────────────

TESTING FOUNDATION

Implement:

• Jest configuration
• Unit-test utilities
• Integration-test utilities
• Database test helpers
• Redis test helpers
• Kafka test helpers
• BullMQ test helpers
• WebSocket test helpers
• API testing helpers
• Fixtures
• Factories

Support deterministic tests.

────────────────────────────────────────

LOCAL DEVELOPMENT

Provide local development infrastructure supporting:

• PostgreSQL
• Redis
• Kafka/Redpanda
• OpenSearch where useful
• S3-compatible object storage

Use Docker Compose where appropriate.

Local development must not depend on production credentials.

────────────────────────────────────────

SECURITY TEST FOUNDATION

Prepare tests for:

• Authentication
• Authorization
• IDOR
• Rate limiting
• Upload ownership
• Object-key manipulation
• WebSocket authorization
• Input validation
• Provider webhook verification boundaries

────────────────────────────────────────

DOCUMENTATION

Generate backend foundation documentation covering:

• Backend architecture
• Monorepo structure
• Configuration
• API conventions
• Error handling
• Validation
• Database conventions
• Prisma
• Redis
• Kafka/Redpanda
• Transactional outbox
• BullMQ
• WebSockets
• Socket.IO
• S3
• Search abstraction
• Media-processing abstraction
• Notification abstraction
• Observability
• Testing
• Local development
• Security foundation
• Upload foundation

────────────────────────────────────────

PROJECT INDEX

Update the backend Project Index with:

• Applications
• Services
• Workers
• Shared packages
• Configuration
• PostgreSQL
• Prisma
• Redis
• Kafka/Redpanda
• Transactional Outbox
• BullMQ
• WebSockets
• Socket.IO
• S3
• Upload subsystem
• Video foundation
• Search abstraction
• Media-processing abstraction
• Notification abstraction
• Observability
• Health checks
• Testing
• Local development
• Security
• Generated files
• Modified files
• Remaining work
• Current milestone
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

BACKEND MILESTONE 1

Monorepo backend structure, NestJS application bootstrap, configuration, request context, logging, errors, validation, security foundation, and API foundation.

BACKEND MILESTONE 2

PostgreSQL, Prisma, migrations, connection management, transaction utilities, query conventions, indexes, and database health.

BACKEND MILESTONE 3

Redis infrastructure, key namespaces, cache abstractions, TTLs, idempotency, rate limiting, and short-lived coordination.

BACKEND MILESTONE 4

Kafka/Redpanda, event envelopes, producers, consumers, schemas, retries, dead-letter infrastructure, and transactional outbox.

BACKEND MILESTONE 5

BullMQ, queues, workers, retries, backoff, timeouts, dead-letter handling, and queue observability.

BACKEND MILESTONE 6

WebSockets and Socket.IO, authentication, authorization, rooms, Redis coordination, heartbeats, reconnection, and backpressure.

BACKEND MILESTONE 7

S3 integration, upload sessions, multipart upload, object-key security, media storage abstractions, and upload lifecycle foundation.

BACKEND MILESTONE 8

Video metadata foundation, media-processing abstractions, processing-job contracts, search abstraction, and notification abstraction.

BACKEND MILESTONE 9

Observability, health checks, graceful shutdown, metrics, tracing, diagnostics, and production hardening.

BACKEND MILESTONE 10

Testing infrastructure, integration helpers, fixtures, factories, local development, security tests, documentation, and Project Index completion.

Each milestone should contain approximately 20–40 files where practical.

Every milestone must compile before proceeding.

────────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never truncate code.

Never summarize source code instead of generating it.

Never generate pseudo-code.

Never generate placeholders.

Never generate TODO implementations.

When modifying an existing file:

1. Provide the exact file path.
2. State why it must change.
3. Provide the complete updated file.

Never regenerate unchanged files.

────────────────────────────────────────

SCOPE RESTRICTION

This volume covers backend foundations:

• Application bootstrap
• Configuration
• Request context
• Logging
• Errors
• Validation
• Security foundation
• API foundation
• PostgreSQL
• Prisma
• Redis
• Kafka/Redpanda
• Transactional Outbox
• BullMQ
• WebSockets
• Socket.IO
• S3
• Upload sessions
• Video metadata foundation
• Media-processing abstraction
• Search abstraction
• Notification abstraction
• Observability
• Health checks
• Graceful shutdown
• Testing foundation
• Local development

Do not implement complete:

• Social graph
• Creators
• Follows
• Likes
• Comments
• Shares
• Collections
• Reposts
• Feed
• Recommendation
• Ranking
• Trending
• Search business logic
• Video transcoding workers
• Playback authorization
• Messaging business logic
• Notifications business logic
• Moderation
• Safety
• Rights
• Advertising
• Analytics
• Administration
• Privacy workflows
• Infrastructure
• Frontend
• Mobile

Those belong to later backend implementation volumes.

────────────────────────────────────────

QUALITY BAR

Treat this backend foundation as critical infrastructure for a globally distributed short-form video platform.

Assume:

• Hundreds of millions of users
• Millions of creators
• Millions of video uploads per day
• Massive feed traffic
• Massive video-processing workloads
• Massive CDN traffic
• Very high event throughput
• Very high WebSocket traffic
• Large search workloads
• Large recommendation workloads
• Multiple regions
• Strict privacy requirements
• Strict content-safety requirements

Prioritize:

• Correctness
• Security
• Scalability
• Reliability
• Low latency
• Media-processing isolation
• Event durability
• Idempotency
• Observability
• Testability
• Maintainability
• Future service extraction
• Production readiness
