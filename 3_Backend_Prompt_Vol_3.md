You are operating in Senior Engineering Team Mode.

Build the production-ready backend for high-scale video processing, adaptive media delivery, playback authorization, content eligibility, engagement, comments, likes, shares, saves, collections, reposts, and foundational creator-content distribution for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The backend must follow the approved TikTok-like architecture, domain boundaries, database ownership, S3 architecture, CDN architecture, media-processing architecture, video lifecycle, security model, event architecture, queue architecture, Redis architecture, and Project Index.

Do not redesign the architecture.

Do not generate frontend code.

Do not generate mobile code.

Do not generate infrastructure implementation code.

Do not generate Terraform.

Do not generate Kubernetes manifests.

Do not generate CI/CD workflows.

────────────────────────────────────────

MISSION

Implement the production-ready backend required for:

• Video processing
• Media validation
• FFmpeg orchestration
• Transcoding
• Video renditions
• Adaptive bitrate ladders
• HLS packaging
• Manifest generation
• Segment metadata
• Thumbnail generation
• Poster generation
• Preview generation
• Caption processing
• Media quality validation
• Playback authorization
• Signed media access
• CDN delivery authorization
• Content eligibility
• Content visibility enforcement
• Likes
• Unlikes
• Like counts
• Comments
• Comment replies
• Comment likes
• Comment pinning
• Shares
• Saves
• Collections
• Reposts
• Engagement aggregation
• Engagement events
• Engagement counters
• Content deletion propagation

The implementation must support:

• Hundreds of millions of users
• Millions of creators
• Millions of uploaded videos
• Massive video-processing queues
• Billions of video impressions
• Massive engagement traffic
• High concurrent playback traffic
• Multiple regions
• Global CDN delivery
• Strong privacy
• Strong authorization
• High availability
• Eventual consistency for derived counters where appropriate

────────────────────────────────────────

TECHNOLOGY STACK

Backend:

• Node.js
• NestJS
• TypeScript

Database:

• PostgreSQL
• Prisma ORM

Cache:

• Redis

Event streaming:

• Kafka or Redpanda

Background processing:

• BullMQ

Object storage:

• AWS S3

CDN:

• CloudFront

Video processing:

• FFmpeg
• Queue-driven workers
• Hardware acceleration where justified

Search:

• Existing OpenSearch/Elasticsearch abstraction

Real-time:

• WebSockets
• Socket.IO where appropriate

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

Use idempotency for all retriable operations.

Use optimistic concurrency where appropriate.

Use queue-based asynchronous processing for long-running media jobs.

Never proxy large media payloads through ordinary API endpoints.

────────────────────────────────────────

DOMAIN OWNERSHIP

Maintain explicit boundaries between:

• Video metadata
• Video assets
• Media processing
• Media packaging
• Playback authorization
• Content eligibility
• Likes
• Comments
• Shares
• Saves
• Collections
• Reposts
• Engagement aggregates

Do not combine:

• Physical media storage with video metadata
• Playback authorization with CDN implementation details
• Like relationships with aggregate counters
• Comments with moderation state
• Saves with recommendation state

────────────────────────────────────────

VIDEO PROCESSING ORCHESTRATION

Complete the media-processing lifecycle:

Uploaded
→ Validation
→ Security Scan
→ Metadata Extraction
→ Processing
→ Transcoding
→ Thumbnail
→ Preview
→ Caption
→ Packaging
→ Quality Validation
→ Moderation Ready
→ Ready

Define durable processing states.

Every stage must be:

• Idempotent
• Retryable
• Observable
• Recoverable

────────────────────────────────────────

MEDIA VALIDATION

Validate:

• File existence
• File size
• MIME signature
• Container format
• Codec
• Duration
• Resolution
• Frame rate
• Audio stream
• Video stream
• Corruption

Reject unsupported or malformed media.

Client-provided metadata must not be authoritative.

────────────────────────────────────────

MEDIA SECURITY SCAN

Create a provider abstraction for security scanning.

Support:

• Scan requested
• Scan pending
• Scan clean
• Scan rejected
• Scan failed

Do not publish media until required security controls pass.

────────────────────────────────────────

METADATA EXTRACTION

Extract:

• Duration
• Width
• Height
• Frame rate
• Video codec
• Audio codec
• Bitrate
• Sample rate
• Channels
• Container
• Rotation/orientation

Normalize values into platform-owned metadata models.

────────────────────────────────────────

TRANSCODING

Implement queue-driven transcoding.

Support configurable output profiles such as:

• Low resolution
• Standard resolution
• High resolution
• Full HD where supported

For each rendition define:

• Codec
• Resolution
• Bitrate
• Frame rate
• Keyframe interval
• Audio settings
• Processing profile version

Do not hard-code media profiles inside controllers.

────────────────────────────────────────

ADAPTIVE BITRATE LADDER

Define a configurable ladder based on:

• Resolution
• Bitrate
• Codec
• Frame rate
• Device/network considerations

Support multiple profiles where product requirements justify them.

────────────────────────────────────────

FFMPEG ORCHESTRATION

Create a provider/service abstraction around FFmpeg.

Support:

• Input validation
• Process execution
• Timeout
• Resource limits
• Exit-code handling
• Standard-output capture
• Standard-error capture
• Cleanup
• Retry classification

Never execute arbitrary user-controlled command fragments.

Construct FFmpeg arguments from validated internal configuration.

────────────────────────────────────────

PROCESS ISOLATION

Media-processing workloads must be isolated from latency-sensitive APIs.

Define:

• Worker pools
• Concurrency
• Resource classes
• CPU limits
• Memory limits
• Temporary storage
• Cleanup

Heavy jobs must not starve API workloads.

────────────────────────────────────────

PROCESSING PRIORITY

Support priority classes where justified:

• User-facing urgent
• Standard
• Bulk/reprocessing

Do not allow unbounded priority escalation by clients.

────────────────────────────────────────

THUMBNAIL GENERATION

Implement:

• Thumbnail extraction
• Multiple candidate thumbnails
• Poster frame
• Preview image
• Selection state

Validate generated images.

Store objects in S3.

Store metadata in PostgreSQL.

────────────────────────────────────────

PREVIEW GENERATION

Support short preview assets where the product requires them.

Define:

• Duration
• Resolution
• Codec
• Object reference
• Processing state

Preview generation must be asynchronous.

────────────────────────────────────────

CAPTION PROCESSING

Integrate the established caption abstraction.

Support:

• Creator captions
• Automatic transcription
• External caption providers

Process:

• Language
• Timing
• Formatting
• Validation

Do not make transcription a synchronous upload dependency.

────────────────────────────────────────

HLS PACKAGING

Implement packaging for adaptive streaming.

Generate:

• Master manifest
• Variant playlists
• Segments

Define:

• Segment naming
• Segment duration
• Rendition mapping
• Manifest version
• Content version

Store generated artifacts in S3.

────────────────────────────────────────

MEDIA VERSIONING

Every processing generation must be versioned.

Support:

• Video version
• Asset version
• Processing version
• Rendition version

Never allow an older processing job to overwrite a newer asset.

────────────────────────────────────────

MEDIA QUALITY VALIDATION

After processing validate:

• File exists
• Duration
• Resolution
• Codec
• Bitrate
• Audio stream
• Segment validity
• Manifest validity
• Expected rendition set

A video should not become ready until required renditions pass validation.

────────────────────────────────────────

MEDIA FAILURE RECOVERY

When processing fails:

• Persist failure state
• Store safe diagnostic reference
• Retry when retryable
• Dead-letter permanent failure
• Allow controlled reprocessing

Do not retry corrupted input forever.

────────────────────────────────────────

PLAYBACK AUTHORIZATION

Implement server-authoritative playback authorization.

Check:

• User authentication
• Account status
• Video existence
• Visibility
• Publication state
• Moderation state
• Rights
• Region
• Age/content restrictions
• Block state
• Creator restrictions
• Video version

Return only the minimum authorization data required by clients.

────────────────────────────────────────

PLAYBACK TOKEN

Use short-lived authorization for media access.

Support:

• Video ID
• Authorized user
• Allowed media/version
• Region where required
• Expiration
• Token ID
• Issued time

Do not generate permanent public media URLs for restricted content.

────────────────────────────────────────

CDN ACCESS

Use CloudFront-compatible signed access.

Support:

• Signed URLs/cookies or equivalent
• Short expiration
• Origin access control
• Cache-safe media identifiers

Do not expose S3 origin access publicly.

────────────────────────────────────────

PLAYBACK ELIGIBILITY

Create a reusable eligibility evaluator.

Inputs:

• User
• Video
• Visibility
• Rights
• Moderation
• Region
• Age restrictions
• Block state
• Publication

Output:

• Allowed/denied
• Reason code
• Effective media version
• Expiration metadata

Internal reason codes must not leak sensitive policy details unnecessarily.

────────────────────────────────────────

PRIVATE VIDEO ACCESS

For private videos:

• Owner authorization required
• No public search
• No public recommendation
• No anonymous playback
• No unrestricted CDN access

────────────────────────────────────────

FOLLOWERS-ONLY ACCESS

For followers-only videos:

• Confirm active follow relationship
• Respect blocks
• Respect creator restrictions
• Use fresh enough relationship state for security-sensitive playback

Do not trust cached follower state beyond acceptable staleness.

────────────────────────────────────────

CONTENT DELETION

When a video is deleted:

• Mark deleted
• Revoke playback authorization
• Remove publication
• Remove feed eligibility
• Remove recommendation eligibility
• Schedule search deletion
• Schedule CDN/object cleanup
• Publish deletion event

The deletion command must be idempotent.

────────────────────────────────────────

DELETE PROPAGATION

Propagate deletion to:

• Feed candidates
• Recommendation candidates
• Search indexes
• Trending sets
• Cached profile feeds
• Playback authorization
• CDN/object lifecycle

Derived systems may converge asynchronously but must stop serving unauthorized content as quickly as required.

────────────────────────────────────────

LIKE DOMAIN

Implement:

• Like
• Unlike
• User-like state
• Like count reference

The relationship must be unique per:

• User
• Video

────────────────────────────────────────

LIKE CONCURRENCY

Protect against:

• Double like
• Double unlike
• Concurrent toggle
• Counter mismatch

Use:

• Database uniqueness
• Idempotency
• Event-driven aggregate updates
• Reconciliation

────────────────────────────────────────

ENGAGEMENT COUNTERS

Separate:

• Authoritative relationship
• Event
• Derived count

Counters may be eventually consistent.

Support reconciliation against authoritative relationships where practical.

────────────────────────────────────────

COMMENT DOMAIN

Implement:

• Comment
• Reply
• Comment like
• Delete
• Pin
• Visibility/moderation reference

Comment states may include:

• Active
• Hidden
• Removed
• Deleted
• Moderation Pending

────────────────────────────────────────

COMMENT OWNERSHIP

Only:

• Comment author
• Video owner where permitted
• Authorized moderator

may perform the corresponding actions.

Do not allow arbitrary comment modification.

────────────────────────────────────────

COMMENT PAGINATION

Use cursor pagination.

Support:

• Top comments
• Recent comments
• Replies
• Pagination cursor
• Ranking version where necessary

Avoid offset pagination for large comment collections.

────────────────────────────────────────

COMMENT RANKING FOUNDATION

Prepare ranking inputs:

• Engagement
• Recency
• Creator relevance
• Reply activity
• Spam score
• Safety state

The final ranking model may be expanded later.

────────────────────────────────────────

COMMENT MODERATION INTEGRATION

Comments must support moderation references.

When a comment is restricted:

• It should stop appearing in ordinary comment queries.
• It should stop contributing to eligible recommendation/analytics signals where required.
• Its moderation history remains controlled.

────────────────────────────────────────

COMMENT LIKES

Implement:

• Like
• Unlike
• Count
• Duplicate protection

Do not use counters as the only authority for whether a user liked a comment.

────────────────────────────────────────

PINNED COMMENTS

Support:

• Pin
• Unpin

Validate:

• Video ownership
• Comment belongs to video
• Comment remains eligible

Only the video owner or authorized moderator may pin.

────────────────────────────────────────

SHARES

Implement:

• Internal share
• External share reference
• Share count

Do not create unrestricted access to private videos.

────────────────────────────────────────

SHARE AUTHORIZATION

When generating a share reference:

• Validate video visibility
• Validate publication
• Respect blocks and restrictions
• Use secure identifiers
• Do not expose internal object paths

────────────────────────────────────────

SAVES

Implement:

• Save video
• Unsave video
• Saved state
• Save timestamp

Unique relationship:

• User
• Video

────────────────────────────────────────

COLLECTIONS

Implement:

• Create collection
• Update collection
• Delete collection
• Add video
• Remove video
• Reorder where required
• Collection visibility

Collection states:

• Active
• Archived
• Deleted

────────────────────────────────────────

PRIVATE COLLECTIONS

Collections are private by default unless product rules explicitly allow sharing.

Do not expose:

• Collection membership
• Saved-video relationships
• Private collection contents

to unauthorized users.

────────────────────────────────────────

REPOSTS

Where supported, implement:

• Repost
• Remove repost
• Repost state
• Repost timestamp

Define how reposts affect:

• Feed
• Profile
• Notifications
• Recommendations

Do not create duplicate content assets.

────────────────────────────────────────

ENGAGEMENT EVENTS

Publish:

• VideoLiked
• VideoUnliked
• CommentCreated
• CommentDeleted
• CommentLiked
• CommentUnliked
• CommentPinned
• CommentUnpinned
• VideoShared
• VideoSaved
• VideoUnsaved
• CollectionCreated
• CollectionUpdated
• CollectionDeleted
• RepostCreated
• RepostRemoved
• VideoDeleted

Events must be:

• Versioned
• Idempotent
• Minimal
• Privacy-aware

────────────────────────────────────────

DATABASE

Implement Prisma models and migrations for:

• VideoProcessingJob
• VideoProcessingStage
• VideoProcessingAttempt
• VideoRendition
• VideoManifest
• VideoSegmentSet
• Thumbnail
• PosterAsset
• PreviewAsset
• PlaybackAuthorizationRecord where required
• Like
• VideoEngagementAggregate
• Comment
• CommentLike
• CommentModerationReference
• Share
• SavedVideo
• Collection
• CollectionItem
• Repost
• EngagementReconciliationReference

Use:

• Foreign keys
• Unique constraints
• Composite indexes
• State fields
• Version fields
• Timestamps

────────────────────────────────────────

DATABASE INDEXES

Create indexes for:

• Video + publication state
• Video + visibility
• Video + creator
• Processing status
• Processing job priority
• Like user/video
• Comment video/created
• Comment parent/created
• Collection owner
• Collection item
• Saved video user/video
• Repost user/video

Use access patterns consistent with cursor pagination.

────────────────────────────────────────

REDIS

Use Redis for:

• Processing deduplication
• Short-lived playback authorization metadata where justified
• Signed-access coordination
• Like-state cache
• Engagement counters
• Comment ranking cache
• Collection cache
• Rate limiting
• WebSocket coordination

Define:

• Key pattern
• TTL
• Ownership
• Invalidation

Redis must never be authoritative for:

• Video ownership
• Playback rights
• Like relationships
• Comment ownership
• Saves
• Collections

────────────────────────────────────────

BACKGROUND JOBS

Implement BullMQ jobs for:

• Processing orchestration
• Transcoding
• Thumbnail generation
• Preview generation
• Caption processing
• HLS packaging
• Media validation
• Failed-job retry
• Media cleanup
• CDN invalidation where required
• Engagement counter reconciliation
• Orphaned media detection
• Deleted-content cleanup

Every job supports:

• Retry
• Backoff
• Timeout
• Idempotency
• Dead-letter handling
• Metrics
• Structured logging

────────────────────────────────────────

API

Implement production-ready REST APIs.

VIDEO PROCESSING

• Get processing status
• Retry failed processing where authorized
• Get asset status

PLAYBACK

• Request playback authorization
• Get playable media metadata

LIKES

• Like video
• Unlike video
• Get like state

COMMENTS

• List comments
• Create comment
• Delete comment
• Like comment
• Unlike comment
• Reply
• Pin/unpin where authorized

SHARES

• Create share reference
• Get share metadata where appropriate

SAVES

• Save video
• Unsave video
• Get saved state

COLLECTIONS

• Create
• Update
• Delete
• List
• Add video
• Remove video
• Reorder

REPOST

• Repost
• Remove repost

Every endpoint must implement:

• Authentication
• Authorization
• Validation
• Rate limiting
• Idempotency where required
• OpenAPI
• Consistent errors
• Resource ownership

────────────────────────────────────────

PLAYBACK API

The playback authorization endpoint must not expose:

• S3 credentials
• Internal origin URLs
• Private storage keys
• Provider secrets

Return only the secure playback information required by the authorized client.

────────────────────────────────────────

SECURITY

Protect against:

• Media scraping
• Playback-token replay
• Unauthorized media access
• Object enumeration
• Upload/process manipulation
• Like spam
• Comment spam
• Share abuse
• Collection enumeration
• Private-content leakage
• Comment IDOR
• Cross-user saved-content access

Use:

• Authentication
• Authorization
• Resource ownership
• Rate limits
• Short-lived tokens
• Secure object references
• Idempotency
• Audit

────────────────────────────────────────

OBSERVABILITY

Instrument:

MEDIA

• Upload completion
• Validation
• Security scan
• Processing
• Transcoding
• Packaging
• Quality validation
• Cleanup

PLAYBACK

• Authorization requests
• Authorization latency
• Denials
• Token generation
• CDN integration errors

ENGAGEMENT

• Likes
• Comments
• Shares
• Saves
• Reposts

Track:

• Processing latency
• Queue depth
• Failure rate
• Retry rate
• Playback authorization success
• Engagement throughput
• Counter lag
• Reconciliation mismatches

Never log:

• Signed URLs/tokens
• Private content
• Private collection contents
• Sensitive user behavior unnecessarily

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Video-processing state machine
• Retry classification
• Rendition validation
• Playback eligibility
• Visibility rules
• Like rules
• Comment rules
• Share rules
• Save rules
• Collection rules
• Repost rules

MEDIA TESTS

Test:

• Valid media
• Corrupt media
• Unsupported codec
• Invalid container
• Large input
• Processing failure
• Duplicate processing
• Superseded version
• Deleted video
• Manifest validation

PLAYBACK TESTS

Test:

• Public video
• Followers-only
• Private
• Removed
• Restricted
• Region denied
• Blocked creator
• Expired authorization
• Replay attempt

ENGAGEMENT TESTS

Test:

• Like
• Unlike
• Duplicate like
• Concurrent like/unlike
• Comment creation
• Comment deletion
• Comment reply
• Comment like
• Share
• Save
• Collection modification
• Repost

CONCURRENCY TESTS

Test:

• Concurrent like
• Concurrent unlike
• Duplicate comment
• Simultaneous collection edits
• Duplicate processing
• Processing version race
• Delete/process race

SECURITY TESTS

Test:

• Playback IDOR
• Media-token replay
• Private-video access
• Collection access
• Comment IDOR
• Unauthorized pin
• Unauthorized share
• Object-key manipulation

PERFORMANCE TESTS

Test:

• Playback authorization throughput
• Like throughput
• Comment throughput
• Share throughput
• Save throughput
• Queue throughput
• Media-processing throughput

────────────────────────────────────────

DOCUMENTATION

Generate:

• Video-processing architecture
• FFmpeg architecture
• Transcoding architecture
• Rendition strategy
• HLS packaging
• Thumbnail architecture
• Preview architecture
• Caption integration
• Media quality validation
• Playback authorization
• CDN security
• Content eligibility
• Video deletion propagation
• Like architecture
• Engagement counters
• Comment architecture
• Comment ranking foundation
• Share architecture
• Save architecture
• Collection architecture
• Repost architecture
• Engagement events
• Queue catalog
• Database schema
• Redis key catalog
• Security model
• Testing strategy

────────────────────────────────────────

PROJECT INDEX

Update the backend Project Index with:

• Media-processing modules
• Processing jobs
• Renditions
• Manifests
• Segment sets
• Thumbnails
• Posters
• Previews
• Captions
• Playback authorization
• Content eligibility
• CDN integration
• Video deletion propagation
• Likes
• Engagement aggregates
• Comments
• Comment replies
• Comment likes
• Comment moderation references
• Shares
• Saves
• Collections
• Reposts
• Financially unrelated engagement events
• APIs
• Kafka topics
• BullMQ queues
• Redis keys
• S3 object patterns
• Tests
• Security
• Observability
• Generated files
• Remaining work
• Current milestone
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

BACKEND MILESTONE 21

Media validation, security scanning, metadata extraction, processing state machine, job orchestration, and processing persistence.

BACKEND MILESTONE 22

FFmpeg orchestration, transcoding profiles, worker execution, retries, timeouts, resource controls, and processing recovery.

BACKEND MILESTONE 23

Video renditions, adaptive bitrate ladders, HLS manifests, packaging, segment metadata, and quality validation.

BACKEND MILESTONE 24

Thumbnail, poster, preview, and caption-processing integration.

BACKEND MILESTONE 25

Playback eligibility, visibility checks, rights hooks, short-lived playback authorization, secure CDN access, and token lifecycle.

BACKEND MILESTONE 26

Video deletion propagation, media cleanup, orphan reconciliation, version conflicts, and CDN/object cleanup.

BACKEND MILESTONE 27

Likes, unlikes, engagement relationships, scalable counters, reconciliation, and engagement events.

BACKEND MILESTONE 28

Comments, replies, comment likes, pagination, pinning, moderation integration, rate limits, and comment events.

BACKEND MILESTONE 29

Shares, saves, collections, reposts, privacy controls, APIs, events, queues, and observability.

BACKEND MILESTONE 30

Media, playback, engagement, concurrency, security, performance, recovery, and integration testing.

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

This volume covers:

• Video processing
• Media validation
• Security scanning abstraction
• Metadata extraction
• FFmpeg orchestration
• Transcoding
• Renditions
• Adaptive bitrate
• HLS packaging
• Thumbnails
• Posters
• Previews
• Captions integration
• Media quality validation
• Playback authorization
• Content eligibility
• CDN authorization integration
• Video deletion propagation
• Likes
• Unlikes
• Engagement aggregates
• Comments
• Replies
• Comment likes
• Comment pinning
• Shares
• Saves
• Collections
• Reposts
• Related events
• Related queues
• Related workers

Do not implement complete:

• For You feed
• Following feed
• Feed ranking
• Recommendation engine
• Candidate generation
• Trending
• Search business logic
• Notifications business logic
• Messaging
• Moderation engine
• Safety platform
• Advertising
• Analytics platform
• Administration UI
• Privacy export/deletion platform
• Infrastructure
• Frontend
• Mobile

Use existing foundations and approved contracts.

────────────────────────────────────────

QUALITY BAR

Treat video processing, playback authorization, and engagement systems as mission-critical infrastructure.

Assume:

• Hundreds of millions of users
• Millions of creators
• Millions of video uploads per day
• Billions of impressions
• Very high concurrent playback
• Massive engagement traffic
• Large media-processing queues
• Global CDN delivery
• Multiple regions
• Strict privacy
• Strict authorization

Prioritize:

• Media integrity
• Playback security
• Processing reliability
• Low latency
• Horizontal scalability
• Idempotency
• Concurrency safety
• Cache correctness
• Content-deletion propagation
• Observability
• Security
• Maintainability
• Production readiness
