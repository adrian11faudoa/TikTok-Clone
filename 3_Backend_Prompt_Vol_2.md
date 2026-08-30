You are operating in Senior Engineering Team Mode.

Build the production-ready backend for identity, accounts, profiles, creators, creator verification, sessions, devices, social graph, follows, blocks, video metadata, upload lifecycle, media assets, video processing orchestration, thumbnails, captions, sounds, hashtags, mentions, and foundational content lifecycle for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The backend must follow the approved TikTok-like architecture, domain boundaries, database ownership, API conventions, event architecture, queue architecture, Redis architecture, object-storage architecture, media-processing abstraction, security model, privacy model, and Project Index.

Do not redesign the architecture.

Do not generate frontend code.

Do not generate mobile code.

Do not generate infrastructure implementation code.

Do not generate Terraform.

Do not generate Kubernetes manifests.

Do not generate CI/CD workflows.

────────────────────────────────────────

MISSION

Implement the production-ready backend domains for:

• Users
• Accounts
• Profiles
• Sessions
• Devices
• Creators
• Creator verification
• Social graph
• Follows
• Blocks
• Videos
• Video metadata
• Video visibility
• Video publication
• Video upload lifecycle
• Upload sessions
• Video assets
• Media processing orchestration
• Video rendition metadata
• Thumbnail metadata
• Poster metadata
• Preview metadata
• Captions
• Sounds
• Sound catalog
• Sound usage
• Hashtags
• Mentions
• Content lifecycle
• Creator ownership
• Content permissions
• Content deletion foundation

The implementation must support:

• Hundreds of millions of users
• Millions of creators
• Very large follow graphs
• Millions of videos
• Very high upload throughput
• Large media-processing workloads
• Multiple devices
• Multiple regions
• Strong ownership controls
• Privacy
• Security
• Idempotency
• Auditability

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

Video processing:

• FFmpeg through the established media-processing abstraction
• Queue-driven workers

Search:

• Established Elasticsearch/OpenSearch abstraction

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

Use idempotency for retriable mutations.

Use optimistic concurrency where appropriate.

Never trust client-supplied ownership.

────────────────────────────────────────

DOMAIN OWNERSHIP

Maintain explicit boundaries between:

• Identity
• Accounts
• Profiles
• Creators
• Creator verification
• Social graph
• Follows
• Blocks
• Videos
• Upload sessions
• Video assets
• Media processing
• Captions
• Sounds
• Hashtags
• Mentions

Do not combine:

• User identity with creator permissions
• Creator verification with creator content
• Upload state with publication state
• Video metadata with physical storage
• Sound rights with simple sound metadata
• Follow relationships with recommendation state

────────────────────────────────────────

IDENTITY

Implement:

• User creation
• User lookup
• Account status
• Profile creation
• Profile update
• Account activation
• Account suspension
• Account deactivation
• Account deletion foundation

Support:

• Public user ID
• Internal database ID
• Account state
• Profile state

Do not expose internal IDs unnecessarily.

────────────────────────────────────────

PROFILE

Implement:

• Username
• Display name
• Avatar reference
• Bio
• Profile visibility
• Language
• Region preference where appropriate
• Profile status

Support:

• Username uniqueness
• Username validation
• Reserved usernames
• Profile updates
• Profile moderation state

Do not permit arbitrary profile metadata.

────────────────────────────────────────

SESSION MANAGEMENT

Implement:

• Session creation
• Session refresh
• Session expiration
• Session revocation
• Logout
• Logout-all
• Device association

Track:

• Session ID
• User ID
• Device ID
• Platform
• App version
• Created time
• Last activity
• Expiration
• Revocation

Never store plaintext authentication secrets.

────────────────────────────────────────

DEVICE MANAGEMENT

Implement:

• Device registration
• Platform
• Device reference
• Application version
• Push-token reference
• Last activity
• Session association
• Device revocation

Support:

• iOS
• Android
• Web

Do not use device identity as a replacement for user identity.

────────────────────────────────────────

CREATOR DOMAIN

Implement:

• Creator profile
• Creator status
• Creator permissions
• Creator ownership
• Creator verification reference
• Creator suspension
• Creator reinstatement

Creator states may include:

• Standard User
• Creator
• Verification Pending
• Verified
• Restricted
• Suspended
• Deactivated

Separate creator status from account status.

────────────────────────────────────────

CREATOR VERIFICATION

Implement:

• Verification application
• Eligibility
• Submission
• Review
• Approval
• Rejection
• Reverification
• Suspension

Support provider abstraction if external verification is required.

Do not store unnecessary raw identity information.

────────────────────────────────────────

CREATOR PERMISSIONS

Define permissions for:

• Create video
• Publish video
• Edit content
• Delete content
• View creator analytics later
• Manage creator profile

Where team accounts are supported, prepare for:

• Owner
• Manager
• Editor
• Analyst

Do not implement full team-management workflows in this volume unless required by existing architecture.

────────────────────────────────────────

SOCIAL GRAPH

Implement authoritative follow relationships.

Support:

• Follow
• Unfollow
• Follow state
• Follower count reference
• Following count reference
• Relationship lookup

The follow relationship must be unique per pair.

────────────────────────────────────────

FOLLOW CONCURRENCY

Prevent:

• Duplicate follows
• Duplicate unfollows
• Counter corruption
• Race-condition inconsistencies

Use:

• Database constraints
• Idempotency
• Event-driven counter aggregation where appropriate

────────────────────────────────────────

HIGH-FANOUT FOLLOWERS

Do not synchronously update every follower's feed when a creator publishes content.

The follow subsystem should produce events consumed by later feed infrastructure.

Support scalable read paths for:

• Followers
• Following
• Mutual relationships where supported

Use cursor pagination.

────────────────────────────────────────

BLOCKING

Implement:

• Block user
• Unblock user
• Block lookup
• Block list

A block should affect:

• Follow eligibility
• Profile visibility where required
• Comments
• Messaging later
• Feed
• Recommendations later
• Mentions
• Search visibility where policy requires

Do not rely solely on client filtering.

────────────────────────────────────────

BLOCK CONCURRENCY

Prevent:

• Duplicate blocks
• Conflicting follow state
• Messaging continuation after block
• Recommendation leakage after block

Blocking must propagate through events.

────────────────────────────────────────

VIDEO DOMAIN

Implement authoritative video records.

Support:

• Video ID
• Owner
• Creator
• Title
• Description
• Visibility
• Status
• Duration
• Dimensions
• Aspect ratio
• Language
• Region metadata
• Content references
• Publication time
• Deletion time
• Version

────────────────────────────────────────

VIDEO STATE MACHINE

Implement:

• Draft
• Uploading
• Uploaded
• Validating
• Processing
• Moderation
• Scheduled
• Published
• Restricted
• Removed
• Archived
• Deleted

Define all valid and invalid transitions.

Every transition must be:

• Authorized
• Idempotent
• Version-aware
• Auditable

────────────────────────────────────────

VIDEO OWNERSHIP

Only the authorized owner/creator may:

• Edit metadata
• Publish
• Unpublish
• Delete
• Modify visibility

Administrative overrides require explicit permissions and audit.

────────────────────────────────────────

VIDEO VISIBILITY

Support:

• Public
• Followers-only
• Private

Define effects on:

• Feed
• Search later
• Recommendations later
• Profile
• Shares
• Comments
• Playback authorization

────────────────────────────────────────

VIDEO PUBLICATION

Support:

• Draft editing
• Publish request
• Publication validation
• Scheduled publication
• Unpublish
• Re-publish where policy allows

Do not publish content before required media-processing and policy checks complete.

────────────────────────────────────────

UPLOAD SESSION

Use the upload foundation from the previous volume.

Implement:

• Create upload session
• Get upload status
• Complete upload
• Cancel upload
• Expire upload
• Associate with video

Support:

• Multipart
• Resumable
• Checksum
• Expected size
• Object reference
• Expiration

────────────────────────────────────────

UPLOAD COMPLETION

When upload completes:

1. Verify object exists.
2. Verify expected size/checksum where configured.
3. Mark upload completed.
4. Create processing job.
5. Publish required event.
6. Do not publish video automatically unless policy explicitly allows it.

The processing path must be asynchronous.

────────────────────────────────────────

MEDIA ASSET DOMAIN

Implement metadata for:

• Original upload
• Master asset
• Renditions
• Manifest
• Thumbnail
• Poster
• Preview
• Captions

Store:

• Asset ID
• Video ID
• Asset type
• Object reference
• Version
• State
• Duration
• Size
• Codec
• Resolution
• Bitrate
• Created time

Do not store physical segment bytes in PostgreSQL.

────────────────────────────────────────

MEDIA PROCESSING ORCHESTRATION

Implement orchestration for:

Upload
→ Validation
→ Processing
→ Transcoding
→ Thumbnail
→ Preview
→ Caption
→ Packaging
→ Validation
→ Ready

Each stage should have durable status.

────────────────────────────────────────

PROCESSING JOBS

Create BullMQ job orchestration for:

• Validation
• Metadata extraction
• Transcoding
• Thumbnail generation
• Preview generation
• Caption processing
• Packaging

Every job must support:

• Idempotency
• Retry
• Exponential backoff
• Timeout
• Concurrency
• Dead-letter handling
• Structured logging
• Metrics

────────────────────────────────────────

PROCESSING STATE CONSISTENCY

Prevent:

• Duplicate processing
• Publishing failed output
• Using stale rendition metadata
• Processing deleted videos
• Processing superseded versions

Use:

• Video version
• Asset version
• Job ID
• Idempotency key

────────────────────────────────────────

VIDEO RENDITION METADATA

Track renditions such as:

• 240p
• 360p
• 480p
• 720p
• 1080p
• Other approved profiles

For each store:

• Resolution
• Codec
• Frame rate
• Bitrate
• Audio metadata
• Object reference
• Manifest reference
• Processing state

Do not hard-code a fixed ladder into domain logic if platform configuration is intended to be dynamic.

────────────────────────────────────────

THUMBNAILS

Implement:

• Thumbnail generation
• Poster generation
• Preview generation
• Selection
• Processing state
• Object reference

Support multiple generated thumbnails if product requirements allow.

────────────────────────────────────────

CAPTIONS

Support:

• Caption track
• Language
• Source
• Format
• Status
• Object reference
• Version

Caption states:

• Pending
• Processing
• Ready
• Failed
• Rejected

────────────────────────────────────────

CAPTION SOURCES

Prepare abstraction for:

• Creator-provided captions
• Automatic transcription
• External caption provider

Do not make a third-party transcription service part of the core domain.

────────────────────────────────────────

SOUNDS

Implement sound catalog entities.

Support:

• Sound
• Creator/attribution reference
• Sound type
• Duration
• Asset reference
• Rights reference
• Availability
• Status

Sound states:

• Active
• Restricted
• Removed
• Expired

────────────────────────────────────────

ORIGINAL SOUNDS

Support creator-generated original sounds.

Define:

• Origin video
• Sound owner
• Attribution
• Usage count
• Status

Do not duplicate large audio objects for each usage.

────────────────────────────────────────

LICENSED SOUNDS

Support:

• Rights reference
• Territory
• Effective dates
• Usage restrictions
• Platform restrictions

Do not assume a sound is globally reusable.

────────────────────────────────────────

SOUND USAGE

Implement:

• Video-to-sound relationship
• Usage count reference
• Sound page reference
• Attribution metadata

The usage event becomes important later for trending and recommendations.

────────────────────────────────────────

HASHTAGS

Implement:

• Hashtag reference
• Normalized value
• Display value
• Video association
• Status
• Moderation state

Support:

• Hashtag pages later
• Search later
• Trending later

────────────────────────────────────────

HASHTAG NORMALIZATION

Normalize:

• Case
• Unicode variants where appropriate
• Leading marker handling
• Invalid characters

Preserve display representation separately from canonical representation.

────────────────────────────────────────

MENTIONS

Implement:

• Mention reference
• Mentioned user
• Mentioning video/comment reference
• Position/range metadata where needed
• Notification event

Mentions must validate:

• User existence
• Block state where policy requires
• Visibility
• Mention eligibility

────────────────────────────────────────

CONTENT METADATA

Support:

• Title
• Description
• Hashtags
• Mentions
• Sound
• Captions
• Language
• Cover/thumbnail
• Visibility

Metadata changes must be version-aware where necessary.

────────────────────────────────────────

CONTENT VERSIONING

Implement video metadata versioning sufficiently to support:

• Processing version
• Publication version
• Asset version
• Concurrency control

Do not allow stale updates to overwrite newer metadata.

────────────────────────────────────────

DELETE / UNPUBLISH

Implement content deletion semantics.

Deletion should:

• Revoke publication
• Stop future feed eligibility
• Stop new recommendation eligibility
• Prevent new playback authorization
• Schedule media cleanup
• Produce deletion event
• Preserve required audit/legal references

The deletion operation must be idempotent.

────────────────────────────────────────

CONTENT ACCESS

Create authorization policies for:

• Owner
• Creator manager where supported
• Public viewer
• Follower viewer
• Administrative viewer

Do not expose private content through API enumeration.

────────────────────────────────────────

VIDEO OBJECT SECURITY

Object keys must not be directly derived from arbitrary user input.

Use safe generated identifiers.

Protect against:

• Path traversal
• Guessable object URLs
• Unauthorized object access
• Cross-user access

────────────────────────────────────────

DATABASE

Implement Prisma models and migrations for:

• User
• Account
• Profile
• Session
• Device
• CreatorProfile
• CreatorVerification
• Follow
• Block
• Video
• VideoMetadata
• VideoPublication
• VideoVisibility
• UploadSession
• VideoAsset
• VideoRendition
• MediaProcessingJob
• MediaProcessingStage
• Thumbnail
• Poster
• PreviewAsset
• CaptionTrack
• Sound
• SoundAsset
• SoundRightsReference
• SoundUsage
• Hashtag
• VideoHashtag
• Mention
• ContentVersion

Use:

• Foreign keys
• Unique constraints
• Composite indexes
• State constraints
• Version fields
• Effective timestamps
• Expiration timestamps

────────────────────────────────────────

INDEXING

Create indexes for:

• Username
• Creator
• Video owner
• Publication state
• Visibility
• Created time
• Updated time
• Follow source/target
• Block source/target
• Sound
• Hashtag
• Mention target

Use cursor-based access patterns.

────────────────────────────────────────

REDIS

Use Redis for:

• Session-adjacent ephemeral state
• Rate limiting
• Upload-session acceleration
• Processing deduplication
• Notification preparation later
• Follow-count caching
• Profile caching
• Short-lived content-state caching

Define:

• Key pattern
• TTL
• Ownership
• Invalidation

Never use Redis as source of truth for:

• Users
• Creators
• Videos
• Follows
• Blocks
• Rights
• Media ownership

────────────────────────────────────────

EVENTS

Publish:

IDENTITY

• UserCreated
• ProfileUpdated
• SessionCreated
• DeviceRegistered

CREATOR

• CreatorCreated
• CreatorVerificationSubmitted
• CreatorVerified
• CreatorVerificationRejected
• CreatorSuspended

SOCIAL GRAPH

• FollowCreated
• FollowRemoved
• UserBlocked
• UserUnblocked

VIDEO

• VideoCreated
• VideoMetadataUpdated
• VideoUploadStarted
• VideoUploadCompleted
• VideoProcessingStarted
• VideoProcessingCompleted
• VideoProcessingFailed
• VideoPublished
• VideoUnpublished
• VideoRestricted
• VideoRemoved
• VideoDeleted

MEDIA

• MediaAssetCreated
• MediaRenditionCreated
• ThumbnailGenerated
• PreviewGenerated
• CaptionProcessed

SOUNDS

• SoundCreated
• SoundUsed
• SoundRestricted
• SoundRemoved

HASHTAGS

• HashtagReferenced

MENTIONS

• UserMentioned

Every event must:

• Be versioned
• Be idempotently consumable
• Carry appropriate correlation metadata
• Respect privacy
• Avoid unnecessary payload data

────────────────────────────────────────

BACKGROUND JOBS

Implement queues for:

• Upload expiration
• Processing orchestration
• Media validation
• Thumbnail generation
• Preview generation
• Caption processing
• Content cleanup
• Expired asset cleanup
• Creator verification
• Document expiration where applicable
• Follow-count reconciliation
• Content-state reconciliation

Every job must support:

• Retry
• Backoff
• Timeout
• Idempotency
• Dead-letter handling
• Metrics
• Structured logs

────────────────────────────────────────

API

Implement REST APIs.

AUTH / ACCOUNT

• Register
• Login
• Logout
• Refresh
• Get account
• Update profile
• Device registration
• Session management

CREATOR

• Get creator profile
• Update creator profile
• Submit verification
• Get verification status

SOCIAL GRAPH

• Follow user
• Unfollow user
• Get followers
• Get following
• Get relationship
• Block
• Unblock
• Get blocked users

VIDEO

• Create draft
• Get video
• Update metadata
• Create upload session
• Get upload status
• Complete upload
• Publish
• Unpublish
• Delete
• Update visibility

MEDIA

• Get asset status
• Get processing status

SOUNDS

• Create/reference sound
• Get sound
• Get sound usage reference

HASHTAGS

• Resolve hashtag
• Get hashtag reference

MENTIONS

• Validate mention target

Every endpoint must implement:

• Authentication
• Authorization
• Validation
• Rate limiting
• Idempotency where appropriate
• OpenAPI
• Consistent errors
• Resource ownership checks

────────────────────────────────────────

UPLOAD APIs

The upload API must return only safe temporary authorization.

Support:

• Upload session creation
• Multipart initiation
• Part authorization
• Completion
• Cancellation

The actual video bytes should go directly to object storage.

────────────────────────────────────────

VIDEO PUBLICATION RULES

A video may become published only when:

• Owner is authorized
• Upload completed
• Required media processing succeeded
• Required moderation preconditions are satisfied
• Visibility is valid
• Content is not deleted/restricted

Publication must be idempotent.

────────────────────────────────────────

SECURITY

Protect against:

• Account takeover
• IDOR
• Unauthorized video modification
• Unauthorized deletion
• Upload abuse
• Object access abuse
• Follow spam
• Block bypass
• Mention abuse
• Sound abuse
• Hashtag abuse
• Processing-job manipulation
• Creator impersonation

Use:

• Authentication
• Authorization
• Resource ownership
• Rate limiting
• Idempotency
• Secure object references
• Audit

────────────────────────────────────────

PRIVACY

Protect:

• Private profiles
• Private videos
• Follower relationships
• Block relationships
• Creator verification data
• Device metadata
• Upload metadata
• Processing metadata

Do not expose:

• Internal object keys
• Provider credentials
• Internal moderation metadata
• Verification-sensitive information

────────────────────────────────────────

OBSERVABILITY

Instrument:

• Registration
• Login
• Profile updates
• Creator verification
• Follow/unfollow
• Block/unblock
• Video creation
• Upload creation
• Upload completion
• Processing orchestration
• Thumbnail generation
• Caption processing
• Publication
• Deletion
• Sound creation
• Hashtag resolution

Track:

• API latency
• Upload success/failure
• Processing backlog
• Processing latency
• Failed processing rate
• Publication latency
• Follow throughput
• Block throughput
• Provider errors
• Queue depth

Never log:

• Passwords
• Access tokens
• Private object credentials
• Private content unnecessarily
• Sensitive creator verification information

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Profile rules
• Creator states
• Follow rules
• Block rules
• Video state machine
• Visibility rules
• Publication rules
• Metadata validation
• Mention validation
• Hashtag normalization
• Sound eligibility
• Content versioning

INTEGRATION TESTS

Test:

• PostgreSQL
• Prisma
• Redis
• Kafka
• BullMQ
• S3 abstraction

UPLOAD TESTS

Test:

• Create session
• Duplicate session
• Resume
• Complete
• Cancel
• Expire
• Missing object
• Checksum mismatch
• Unauthorized completion

PROCESSING TESTS

Test:

• Job creation
• Duplicate job
• Retry
• Failure
• Recovery
• Superseded version
• Deleted video

SOCIAL TESTS

Test:

• Follow
• Unfollow
• Duplicate follow
• Concurrent follow
• Block
• Concurrent block
• Block/follow interaction

SECURITY TESTS

Test:

• Video IDOR
• Profile IDOR
• Unauthorized publish
• Unauthorized delete
• Object-key manipulation
• Cross-user upload access
• Creator impersonation

CONCURRENCY TESTS

Test:

• Concurrent metadata update
• Concurrent publication
• Concurrent deletion
• Concurrent follow
• Duplicate upload completion
• Duplicate processing

PERFORMANCE TESTS

Test:

• Profile lookup
• Follow lookup
• Creator lookup
• Video metadata lookup
• Upload initialization
• Upload completion
• Processing orchestration

────────────────────────────────────────

DOCUMENTATION

Generate:

• Identity architecture
• Profile architecture
• Creator architecture
• Creator verification
• Session/device architecture
• Social graph
• Follow architecture
• Block architecture
• Video architecture
• Upload architecture
• Video state machine
• Media asset architecture
• Processing orchestration
• Rendition metadata
• Thumbnail architecture
• Caption architecture
• Sound architecture
• Hashtag architecture
• Mention architecture
• Content ownership
• Content visibility
• Publication lifecycle
• Deletion architecture
• API contracts
• Database schema
• Events
• Queues
• Redis key catalog
• Security
• Privacy
• Testing

────────────────────────────────────────

PROJECT INDEX

Update the backend Project Index with:

• Identity
• Accounts
• Profiles
• Sessions
• Devices
• Creators
• Creator verification
• Social graph
• Follows
• Blocks
• Videos
• Upload sessions
• Video metadata
• Video visibility
• Publication
• Video assets
• Renditions
• Processing jobs
• Thumbnails
• Posters
• Previews
• Captions
• Sounds
• Sound rights references
• Sound usage
• Hashtags
• Mentions
• Database objects
• Migrations
• API endpoints
• Events
• Kafka topics
• BullMQ queues
• Redis keys
• S3 objects
• Observability
• Security
• Privacy
• Tests
• Generated files
• Modified files
• Remaining work
• Current milestone
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

BACKEND MILESTONE 11

Users, accounts, profiles, sessions, devices, authentication integration, security policies, and account lifecycle.

BACKEND MILESTONE 12

Creators, creator profiles, creator verification, creator permissions, suspension, reinstatement, and verification-provider abstraction.

BACKEND MILESTONE 13

Social graph, follows, unfollows, relationship queries, follower/following pagination, counters, blocks, and graph events.

BACKEND MILESTONE 14

Video entity, metadata, visibility, ownership, publication state machine, versioning, and content authorization.

BACKEND MILESTONE 15

Upload sessions, multipart completion, object verification, resumable-upload lifecycle, upload expiration, and upload security.

BACKEND MILESTONE 16

Video assets, processing orchestration, processing jobs, media stages, rendition metadata, thumbnails, posters, previews, and processing recovery.

BACKEND MILESTONE 17

Captions, sound catalog, original sounds, licensed-sound references, sound usage, hashtags, mentions, and metadata associations.

BACKEND MILESTONE 18

Publication workflow, unpublish, deletion, content cleanup, version conflicts, ownership enforcement, events, and reconciliation.

BACKEND MILESTONE 19

Redis optimization, observability, queue monitoring, security hardening, privacy controls, and operational diagnostics.

BACKEND MILESTONE 20

Integration, concurrency, upload, media-processing, social-graph, security, and performance testing.

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

• Identity
• Accounts
• Profiles
• Sessions
• Devices
• Creators
• Creator verification
• Creator permissions
• Social graph
• Follows
• Blocks
• Videos
• Video metadata
• Visibility
• Publication
• Upload sessions
• Media assets
• Processing orchestration
• Renditions
• Thumbnails
• Posters
• Previews
• Captions
• Sounds
• Sound metadata
• Sound rights references
• Sound usage
• Hashtags
• Mentions
• Content ownership
• Content deletion foundation
• Related events
• Related queues
• Related workers

Do not implement complete:

• Feed generation
• Recommendation ranking
• For You feed
• Following feed generation
• Trending
• Search business logic
• Likes
• Comments
• Shares
• Saves
• Collections
• Reposts
• Messaging business logic
• Notifications business logic
• Moderation
• Safety
• Advertising
• Analytics platform
• Administration
• Privacy export/deletion platform beyond content lifecycle foundations
• Infrastructure
• Frontend
• Mobile

Those belong to later implementation volumes.

────────────────────────────────────────

QUALITY BAR

Treat identity, creator ownership, social relationships, video ownership, upload integrity, and media-processing orchestration as critical systems.

Assume:

• Hundreds of millions of users
• Millions of creators
• Millions of uploads per day
• Very large follow graphs
• Very high upload traffic
• Large video-processing queues
• Multiple content versions
• Multiple regions
• Strict privacy
• Strict ownership controls
• High availability

Prioritize:

• Ownership correctness
• Upload correctness
• Processing reliability
• Social-graph scalability
• Idempotency
• Security
• Privacy
• Observability
• Queue reliability
• Horizontal scalability
• Maintainability
• Production readiness
