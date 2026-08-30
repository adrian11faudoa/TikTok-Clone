You are operating in Senior Engineering Team Mode.

Design the complete foundational architecture for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

This is an ARCHITECTURE PHASE.

Do not implement backend code.

Do not implement frontend code.

Do not implement mobile code.

Do not generate Dockerfiles.

Do not generate Kubernetes manifests.

Do not generate Terraform files.

Do not generate CI/CD workflows.

Do not generate application source code.

Produce architecture, specifications, contracts, schemas, diagrams, ownership rules, engineering decisions, operational strategies, security models, and implementation guidance only.

────────────────────────────────────────

PROJECT

Build a production-ready global short-form video social platform supporting:

• Users
• Accounts
• Profiles
• Creator profiles
• Creator verification
• Followers
• Following
• User blocking
• Short-form videos
• Video uploads
• Resumable uploads
• Multipart uploads
• Video metadata
• Video processing
• Video transcoding
• Multiple video renditions
• Adaptive video streaming
• Thumbnails
• Posters
• Preview clips
• Captions
• Sounds
• Sound discovery
• Hashtags
• Mentions
• Likes
• Comments
• Comment replies
• Shares
• Saves
• Collections
• Reposts where supported
• For You feed
• Following feed
• Trending
• Search
• Recommendations
• Personalization
• Notifications
• Direct messaging
• Moderation
• Reporting
• Content safety
• Copyright/right management
• Advertising
• Creator analytics
• Administration
• Privacy
• Data export
• Data deletion
• Feature flags
• Dynamic configuration
• Audit
• Multi-region operation
• CDN delivery
• High availability
• Disaster recovery

The platform must be designed for:

• Hundreds of millions of users
• Millions of creators
• Millions of uploads per day
• Billions of video impressions
• Massive watch-time event volume
• Massive feed request volume
• Large recommendation workloads
• Large search traffic
• Global CDN delivery
• Low-latency feed generation
• High concurrent playback traffic

────────────────────────────────────────

PRIMARY TECHNOLOGY STACK

WEB

• Next.js
• React
• TypeScript
• Tailwind CSS
• shadcn/ui
• TanStack Query
• Zustand

MOBILE

• React Native
• Expo
• TypeScript

BACKEND

• Node.js
• NestJS
• TypeScript

DATABASE

• PostgreSQL
• Prisma ORM

CACHE

• Redis

EVENT STREAMING

• Kafka or Redpanda

BACKGROUND PROCESSING

• BullMQ

SEARCH

• Elasticsearch or OpenSearch

OBJECT STORAGE

• AWS S3

CDN

• CloudFront

VIDEO PROCESSING

• FFmpeg
• Queue-driven workers
• Hardware-accelerated processing where justified

REAL-TIME

• WebSockets
• Socket.IO where appropriate

PUSH NOTIFICATIONS

• Firebase Cloud Messaging
• Apple Push Notification Service

OBSERVABILITY

• OpenTelemetry
• Prometheus
• Grafana
• Loki
• Tempo

INFRASTRUCTURE

• Docker
• Kubernetes
• Helm
• Terraform
• GitHub Actions

SECURITY

• IAM
• KMS
• Secrets Manager
• WAF
• RBAC
• NetworkPolicies

────────────────────────────────────────

ARCHITECTURAL APPROACH

Determine the appropriate architecture between:

• Modular Monolith
• Service-Oriented Architecture
• Microservices

Do not blindly create a microservice for every domain.

Evaluate:

• Video-processing scale
• Feed latency
• Recommendation workloads
• Search workloads
• Event volume
• Social-graph scale
• Creator workload
• Moderation workload
• CDN delivery
• Real-time requirements
• Operational complexity
• Team ownership
• Global deployment
• Failure isolation
• Cost
• Developer productivity

Clearly identify:

• Independently deployable services
• Shared transactional boundaries
• Authoritative data ownership
• Derived data
• Read models
• Cache ownership
• Synchronous communication
• Asynchronous communication
• Real-time communication
• Stream processing
• Batch processing

Provide a future service-extraction strategy.

────────────────────────────────────────

DOMAIN DECOMPOSITION

Define bounded contexts for:

Identity

Accounts

Profiles

Sessions

Devices

Creators

Creator Verification

Social Graph

Followers

Following

Blocking

Videos

Video Metadata

Video Assets

Video Upload

Video Processing

Video Renditions

Video Thumbnails

Captions

Sounds

Sound Catalog

Hashtags

Mentions

Likes

Comments

Comment Replies

Shares

Saves

Collections

Reposts

Feeds

Feed Candidates

Feed Ranking

Recommendations

Personalization

Trending

Search

Notifications

Messaging

Moderation

Content Safety

Reporting

Copyright/Rights

Advertising

Creator Analytics

Platform Analytics

Administration

Audit

Feature Flags

System Configuration

Privacy

────────────────────────────────────────

SERVICE OWNERSHIP

Evaluate services such as:

API Gateway

Identity Service

Account Service

Profile Service

Session Service

Device Service

Creator Service

Creator Verification Service

Social Graph Service

Video Service

Upload Service

Video Processing Service

Transcoding Service

Media Packaging Service

Thumbnail Service

Caption Service

Sound Service

Hashtag Service

Engagement Service

Comment Service

Share Service

Save/Collection Service

Feed Service

Feed Candidate Service

Ranking Service

Recommendation Service

Trending Service

Search Service

Notification Service

Messaging Service

Moderation Service

Safety Service

Reporting Service

Rights Service

Advertising Service

Creator Analytics Service

Analytics Ingestion Service

Administration Service

Audit Service

Feature Flag Service

Configuration Service

Privacy Service

Do not create unnecessary services.

For every final service define:

• Responsibility
• Owned data
• APIs
• Events produced
• Events consumed
• Synchronous dependencies
• Asynchronous dependencies
• Scaling profile
• Availability requirements
• Security boundaries

────────────────────────────────────────

SERVICE OWNERSHIP MATRIX

Create a complete matrix defining:

• Authoritative service
• Database owner
• Cache owner
• Search owner
• Event owner
• Read-model owner
• Administrative owner

No service may write directly to another service's authoritative database.

────────────────────────────────────────

SYSTEM ARCHITECTURE

Generate text-based diagrams for:

CLIENT LAYER

• Web
• iOS
• Android
• Creator interfaces
• Administration

EDGE LAYER

• DNS
• CDN
• WAF
• Load balancer
• API gateway
• WebSocket gateway

APPLICATION LAYER

• Identity
• Profiles
• Social graph
• Video
• Feed
• Recommendations
• Search
• Engagement
• Messaging
• Moderation
• Notifications
• Advertising
• Analytics
• Administration

MEDIA LAYER

• Upload
• Object storage
• Processing
• Transcoding
• Packaging
• CDN

STREAMING LAYER

• Kafka/Redpanda
• Consumer groups
• Stream processing
• Analytics

DATA LAYER

• PostgreSQL
• Redis
• Search
• S3

OBSERVABILITY

• Metrics
• Logs
• Traces
• Alerts

SECURITY

• Authentication
• Authorization
• Secrets
• Encryption
• Audit

Do not use images.

────────────────────────────────────────

MONOREPO ARCHITECTURE

Design:

apps/

• Consumer Web
• Creator Web
• Admin Web
• Mobile Customer App
• Mobile Creator App where justified

services/

• API Gateway
• Domain services
• Recommendation services
• Feed services
• Search
• Media processing
• Notification
• Messaging
• Moderation
• Analytics

workers/

• Video processing
• Transcoding
• Thumbnail generation
• Caption processing
• Search indexing
• Feed refresh
• Recommendation refresh
• Trending
• Moderation
• Notifications
• Analytics
• Privacy jobs

packages/

• API contracts
• Event contracts
• Shared types
• Validation
• Configuration
• Authentication
• Authorization
• Media abstractions
• Storage abstractions
• Search abstractions
• Observability
• Testing utilities

infra/

• Docker
• Kubernetes
• Helm
• Terraform
• CI/CD

docs/

• Architecture
• API
• Events
• Media
• Feed
• Recommendations
• Search
• Security
• Privacy
• Operations
• ADRs
• Runbooks

────────────────────────────────────────

FOLDER HIERARCHY

Generate a detailed production-ready hierarchy for:

• Consumer web
• Creator web
• Admin web
• Customer mobile
• Creator mobile where applicable
• API gateway
• Backend services
• Video processing
• Feed
• Recommendation
• Search
• Moderation
• Analytics
• Workers
• Shared packages
• Database
• Infrastructure
• Tests
• Documentation

The hierarchy must support future implementation prompts without major structural redesign.

────────────────────────────────────────

IDENTITY ARCHITECTURE

Define:

• User
• Account
• Profile
• Session
• Device
• Creator status

Support:

• Registration
• Login
• OAuth
• MFA
• Passkeys where justified
• Session management
• Device management
• Account recovery

Define account and profile boundaries.

────────────────────────────────────────

CREATOR ARCHITECTURE

Define:

• Creator profile
• Creator verification
• Creator status
• Creator metadata
• Creator team where supported
• Organization/management roles

Support:

• Verification
• Reverification
• Suspension
• Creator permissions
• Content ownership

────────────────────────────────────────

SOCIAL GRAPH

Design the follow graph.

Support:

• Follow
• Unfollow
• Followers
• Following
• Mutual relationships
• Blocking

Evaluate storage options for:

• Source-of-truth relationship
• High-scale read paths
• Cached follower counts
• Feed generation

Avoid synchronously updating millions of follower records on a single creator action.

────────────────────────────────────────

FOLLOW GRAPH SCALABILITY

Evaluate:

• Fan-out-on-write
• Fan-out-on-read
• Hybrid fan-out

For high-fanout creators:

• Avoid massive synchronous writes
• Use asynchronous propagation
• Maintain scalable candidate sources

────────────────────────────────────────

VIDEO ARCHITECTURE

Design lifecycle:

Upload
→ Validation
→ Security scan
→ Metadata extraction
→ Processing
→ Moderation
→ Transcoding
→ Thumbnail generation
→ Caption processing
→ Packaging
→ Publication
→ CDN
→ Playback analytics

Support:

• Draft
• Uploading
• Processing
• Moderation
• Scheduled
• Published
• Restricted
• Removed
• Archived
• Deleted

────────────────────────────────────────

VIDEO UPLOAD

Support:

• Multipart upload
• Resumable upload
• Upload sessions
• Chunk validation
• Checksum
• Resume
• Cancel
• Retry
• Expiration

The API must not proxy large video files unnecessarily.

Use object-storage direct-upload mechanisms.

────────────────────────────────────────

VIDEO ASSET MODEL

Define:

• Original asset
• Master asset
• Rendition
• Manifest
• Segment set
• Thumbnail
• Poster
• Preview
• Caption track

Store large media in object storage.

Store metadata and authoritative state in PostgreSQL.

────────────────────────────────────────

VIDEO PROCESSING

Design queue-driven workers.

Support:

• FFmpeg
• Codec validation
• Resolution normalization
• Frame-rate handling
• Audio processing
• Bitrate ladder
• Thumbnail extraction
• Preview generation
• Caption processing
• Quality validation

Long-running jobs must not execute inside latency-sensitive API services.

────────────────────────────────────────

VIDEO RENDITIONS

Define adaptive streaming renditions.

Support configurable:

• Resolution
• Frame rate
• Bitrate
• Codec
• Audio bitrate

Evaluate:

• HLS
• DASH where useful

Define manifest and segment naming strategy.

────────────────────────────────────────

CDN ARCHITECTURE

Support CloudFront for:

• Video manifests
• Video segments
• Thumbnails
• Posters
• Static assets

Define:

• Origin access control
• Cache policies
• Signed access
• Expiration
• Invalidation
• Regional distribution

Immutable media should use long-lived caching where appropriate.

────────────────────────────────────────

PLAYBACK AUTHORIZATION

Define backend authorization based on:

• Visibility
• User status
• Creator status
• Region
• Content restrictions
• Moderation state
• Rights

Support:

• Signed access
• Short-lived authorization
• Manifest authorization where appropriate

Application servers should not proxy every video segment.

────────────────────────────────────────

CONTENT VISIBILITY

Support:

• Public
• Followers-only
• Private

Define effects on:

• Feed
• Search
• Recommendations
• Profile
• Shares
• Comments
• Playback
• CDN

Private videos must never become publicly discoverable through stale indexes or caches.

────────────────────────────────────────

VIDEO DELETION

When content is deleted:

• Revoke publication
• Remove feed eligibility
• Remove recommendation eligibility
• Remove search visibility
• Revoke playback access
• Schedule object cleanup
• Preserve legally required metadata

Deletion must be idempotent.

────────────────────────────────────────

SOUND ARCHITECTURE

Define:

• Sound
• Original sound
• Licensed sound
• Sound asset
• Rights
• Availability
• Usage count

Support:

• Sound page
• Search
• Trending
• Video association

Do not duplicate a sound's audio bytes for every video.

────────────────────────────────────────

RIGHTS ARCHITECTURE

Support:

• Content rights
• Sound rights
• Region
• Effective dates
• Platform
• Usage restrictions

Rights affect:

• Playback
• Feed
• Search
• Recommendations
• Sounds
• Advertising

────────────────────────────────────────

HASHTAG ARCHITECTURE

Support:

• Hashtag creation/reference
• Video association
• Discovery
• Search
• Trending
• Moderation

Prevent:

• Hashtag spam
• Malicious abuse

────────────────────────────────────────

MENTIONS

Support:

• User mention
• Creator mention
• Mention validation
• Notification
• Privacy controls

Define behavior for:

• Blocked users
• Deleted users
• Private profiles

────────────────────────────────────────

ENGAGEMENT

Define:

• Like
• Comment
• Reply
• Share
• Save
• Repost

Each interaction must be:

• Idempotent
• Authorized
• Auditable where required

────────────────────────────────────────

LIKE ARCHITECTURE

Support:

• User-like state
• Like count
• Unlike
• Duplicate protection

Separate:

• Source-of-truth relationship
• Aggregate count
• Feed/recommendation event

Do not update enormous counters synchronously without scalability safeguards.

────────────────────────────────────────

COMMENT ARCHITECTURE

Support:

• Comment
• Reply
• Like
• Pin
• Delete
• Moderation
• Reporting

Protect against:

• Spam
• Flooding
• Automated abuse

────────────────────────────────────────

SHARE ARCHITECTURE

Support:

• Internal share
• External share
• Share references
• Share count

Share access must respect visibility.

────────────────────────────────────────

SAVE / COLLECTION ARCHITECTURE

Support:

• Save video
• Unsave
• Collection
• Collection item
• Rename
• Delete
• Private collections

────────────────────────────────────────

FOR YOU FEED

Design:

Request
→ Candidate generation
→ Eligibility
→ Safety
→ Ranking
→ Diversity
→ Exploration
→ Response

Candidate sources:

• Follow graph
• Watch history
• Likes
• Comments
• Shares
• Saves
• Sounds
• Hashtags
• Creators
• Similar videos
• Trending
• New content
• Regional trends
• Exploration

────────────────────────────────────────

FEED CANDIDATE ARCHITECTURE

Separate:

• Candidate generation
• Eligibility
• Ranking
• Re-ranking
• Diversity

Candidates may originate from:

• Social graph
• Content similarity
• Behavioral signals
• Trending
• Editorial systems
• Exploration systems

────────────────────────────────────────

FOLLOWING FEED

Support:

• Followed creators
• Recent posts
• Ranking
• Chronology mode where appropriate
• Candidate refresh
• Pagination

Use hybrid fan-out for scale.

────────────────────────────────────────

RECOMMENDATION ARCHITECTURE

Support:

• Candidate retrieval
• Feature extraction
• Ranking
• Re-ranking
• Personalization
• Diversity
• Exploration

Initial signals:

• Watch duration
• Completion
• Rewatch
• Skip
• Like
• Comment
• Share
• Save
• Follow
• Search
• Sound interaction
• Hashtag interaction

Future architecture should support:

• Embeddings
• Collaborative filtering
• ML ranking
• Feature store
• Model serving
• Online experimentation

Do not make advanced ML infrastructure mandatory for the first implementation.

────────────────────────────────────────

RECOMMENDATION SAFETY

Recommendations must exclude:

• Removed videos
• Restricted videos
• Blocked users
• Blocked creators
• Unauthorized content
• Regionally unavailable content
• Rights-expired content
• Safety-restricted content

Eligibility must be enforced before final ranking.

────────────────────────────────────────

FEED PAGINATION

Use cursor-based pagination.

Define:

• Cursor
• Ranking snapshot
• Candidate version
• Expiration
• Consistency expectations

Avoid offset pagination for high-scale personalized feeds.

────────────────────────────────────────

DIVERSITY

Support configurable diversity for:

• Creators
• Sounds
• Hashtags
• Topics
• Content types
• Freshness

Avoid repetitive feed loops.

────────────────────────────────────────

TRENDING

Support:

• Global trends
• Regional trends
• Hashtag trends
• Sound trends
• Creator trends
• Topic trends

Use:

• Time windows
• Engagement decay
• Freshness
• Anti-abuse signals

────────────────────────────────────────

SEARCH ARCHITECTURE

Search:

• Videos
• Creators
• Hashtags
• Sounds

Support:

• Full text
• Prefix
• Autocomplete
• Typo tolerance
• Ranking
• Filters
• Region
• Safety
• Visibility

Search must be rebuildable from authoritative data.

────────────────────────────────────────

MESSAGING

Design direct messaging.

Support:

• One-to-one conversations
• Group messaging where justified
• Messages
• Delivery state
• Read state
• Attachments
• Blocking
• Reporting

Use WebSockets.

Define message retention and privacy.

────────────────────────────────────────

NOTIFICATIONS

Support:

• Follows
• Likes
• Comments
• Replies
• Mentions
• Shares
• Messages
• Creator updates
• Moderation
• Security
• System

Define:

• Push
• In-app
• Email where appropriate
• Preference
• Deduplication
• Retry
• Scheduling

────────────────────────────────────────

MODERATION ARCHITECTURE

Support moderation for:

• Videos
• Captions
• Comments
• Messages
• Profiles
• Sounds
• Hashtags

Architecture:

Content
→ Detection
→ Classification
→ Review
→ Decision
→ Enforcement
→ Appeal

Support:

• Automated classification
• Human review
• Appeals
• Reinstatement

────────────────────────────────────────

CONTENT SAFETY

Define policy categories for:

• Hate
• Harassment
• Violence
• Sexual content
• Dangerous activity
• Self-harm
• Illegal content
• Spam
• Fraud
• Copyright violations

Do not make one automated model the sole safety authority.

────────────────────────────────────────

REPORTING

Support reports for:

• Video
• User
• Creator
• Comment
• Message
• Sound
• Hashtag

A report may create:

• Moderation case
• Safety case
• Fraud case
• Copyright case

────────────────────────────────────────

COPYRIGHT

Support:

• Rights reference
• Takedown
• Content claim
• Sound claim
• Regional restriction
• Appeal
• Reinstatement

Keep legal workflow separate from ordinary moderation.

────────────────────────────────────────

ADVERTISING

Design:

• Advertiser
• Campaign
• Ad group
• Creative
• Placement
• Targeting
• Budget
• Frequency cap
• Impression
• Click
• Video completion

Advertising must respect:

• Privacy
• User controls
• Regional restrictions
• Content safety

────────────────────────────────────────

CREATOR ANALYTICS

Support:

• Views
• Watch time
• Completion
• Likes
• Comments
• Shares
• Saves
• Follower growth
• Traffic sources
• Sound usage
• Regional summaries

Do not expose data beyond creator authorization.

────────────────────────────────────────

ANALYTICS ARCHITECTURE

Separate:

• Transactional database
• Event stream
• Stream processing
• Aggregations
• Long-term analytical storage

Do not store unlimited raw impression/watch telemetry in PostgreSQL.

────────────────────────────────────────

EVENT-DRIVEN ARCHITECTURE

Define core events:

IDENTITY

• UserCreated
• ProfileUpdated
• SessionCreated
• DeviceRegistered

CREATOR

• CreatorVerified
• CreatorSuspended

SOCIAL

• FollowCreated
• FollowRemoved
• UserBlocked
• UserUnblocked

VIDEO

• VideoUploadStarted
• VideoUploadCompleted
• VideoProcessingStarted
• VideoProcessingCompleted
• VideoProcessingFailed
• VideoPublished
• VideoRestricted
• VideoRemoved
• VideoDeleted

MEDIA

• RenditionCreated
• ThumbnailCreated
• CaptionProcessed

ENGAGEMENT

• VideoLiked
• VideoUnliked
• CommentCreated
• CommentDeleted
• CommentLiked
• VideoShared
• VideoSaved
• CollectionUpdated
• RepostCreated

DISCOVERY

• SearchPerformed
• FeedGenerated
• RecommendationServed
• RecommendationClicked
• TrendUpdated

SOUNDS

• SoundCreated
• SoundUsed
• SoundRestricted

MODERATION

• ReportCreated
• ModerationCaseCreated
• ModerationActionTaken
• AppealCreated
• AppealResolved

MESSAGING

• ConversationCreated
• MessageCreated
• MessageDelivered
• MessageRead

NOTIFICATIONS

• NotificationCreated
• NotificationDelivered
• NotificationFailed

ADVERTISING

• AdImpression
• AdClick
• AdCompleted

PRIVACY

• PrivacyRequestCreated
• DataExportCompleted
• DataDeletionCompleted

ADMIN

• FeatureFlagChanged
• ConfigurationChanged
• AdministrativeActionTaken

────────────────────────────────────────

EVENT DESIGN

Every event should define:

• Event ID
• Event type
• Version
• Aggregate type
• Aggregate ID
• Region
• Timestamp
• Producer
• Correlation ID
• Causation ID where appropriate
• Payload

Events must be:

• Versioned
• Idempotent
• Replayable where appropriate
• Minimal
• Privacy-aware

────────────────────────────────────────

QUEUE ARCHITECTURE

Define BullMQ queues for:

• Video processing
• Transcoding
• Thumbnail generation
• Caption processing
• Moderation
• Search indexing
• Feed refresh
• Recommendation refresh
• Trending calculation
• Notification delivery
• Analytics aggregation
• Report generation
• Data export
• Data deletion
• Cleanup

For every queue define:

• Producer
• Consumer
• Job schema
• Retry
• Backoff
• Timeout
• Concurrency
• Dead-letter behavior
• Scaling strategy
• Monitoring

────────────────────────────────────────

DATABASE ARCHITECTURE

Use PostgreSQL as authoritative transactional storage.

Conceptual entities:

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
• VideoAsset
• VideoRendition
• VideoManifest
• Thumbnail
• Poster
• PreviewAsset
• CaptionTrack
• Sound
• SoundAsset
• SoundRights
• SoundUsage
• Hashtag
• VideoHashtag
• Mention
• Like
• Comment
• CommentLike
• Share
• SavedVideo
• Collection
• CollectionItem
• Repost
• Notification
• NotificationPreference
• Conversation
• ConversationParticipant
• Message
• MessageDelivery
• Report
• ModerationCase
• ModerationAction
• Appeal
• RightsReference
• AdCampaign
• AdGroup
• AdCreative
• FeatureFlag
• FeatureFlagRule
• SystemConfiguration
• AuditLog
• PrivacyRequest

Do not store:

• Every video segment
• Every CDN request
• Unlimited raw feed impressions
• Unlimited raw watch events
• High-frequency transient ranking state

in ordinary transactional tables.

────────────────────────────────────────

DATABASE SCALABILITY

Evaluate partitioning for:

• Engagement events
• Comments
• Notifications
• Messages
• Reports
• Audit logs
• Analytics references

Use appropriate indexes for:

• Creator
• Visibility
• Publication state
• Hashtag
• Sound
• Follow relationships
• User interactions

────────────────────────────────────────

REDIS ARCHITECTURE

Use Redis for:

• Feed caches
• Following candidates
• Trending
• Rate limiting
• Session-adjacent ephemeral state
• Notification deduplication
• WebSocket coordination
• Recommendation caches
• Upload session state
• Job coordination where appropriate

Define:

• Key pattern
• TTL
• Ownership
• Invalidation
• Stampede protection
• Failure behavior

Redis is never the source of truth for:

• Users
• Videos
• Rights
• Financial data
• Moderation cases
• Privacy records

────────────────────────────────────────

SEARCH INDEX ARCHITECTURE

Indexes:

• Videos
• Creators
• Hashtags
• Sounds

Support:

• Versioned indexes
• Aliases
• Reindexing
• Incremental indexing
• Deletion
• Staleness detection

Search must be rebuildable from PostgreSQL/object metadata.

────────────────────────────────────────

MEDIA STORAGE

Define S3 buckets/prefix strategies for:

• Original uploads
• Processing artifacts
• Master videos
• Renditions
• Manifests
• Segments
• Thumbnails
• Posters
• Preview clips
• Captions
• Creator assets
• Reports
• Privacy exports

Support:

• Encryption
• Versioning where needed
• Lifecycle
• Replication
• Access controls

────────────────────────────────────────

VIDEO PROCESSING SCALABILITY

Design dedicated worker pools for:

• Standard CPU
• High-CPU transcoding
• GPU/hardware acceleration where justified
• Caption processing
• Moderation
• Thumbnail generation

Scale using:

• Queue depth
• Processing latency
• CPU
• Memory
• GPU utilization where applicable

Do not run heavy media jobs on API nodes.

────────────────────────────────────────

MULTI-REGION ARCHITECTURE

Design:

• Regional APIs
• Regional WebSocket gateways
• Regional feed processing
• Regional video processing
• Regional recommendation processing
• Regional search where appropriate
• Global CDN
• Global DNS
• Regional analytics processing

Keep latency-sensitive user interactions regionally close.

────────────────────────────────────────

REGIONAL CONTENT OWNERSHIP

Define:

• User home region
• Creator home region
• Content metadata ownership
• Video processing region
• Analytics region
• Moderation region

Avoid unnecessary cross-region synchronous writes.

────────────────────────────────────────

SECURITY ARCHITECTURE

Design:

AUTHENTICATION

• Passwords
• OAuth
• MFA
• Passkeys
• Sessions
• Device trust

AUTHORIZATION

• RBAC
• Resource ownership
• Creator scope
• Team scope
• Admin scope

MEDIA

• Upload authorization
• Signed access
• Object isolation
• Malware scanning

APPLICATION

• Input validation
• Rate limiting
• Secure headers
• CORS
• CSRF where applicable
• XSS prevention
• SQL injection protection
• SSRF mitigation

────────────────────────────────────────

VIDEO SECURITY

Protect against:

• Unauthorized uploads
• Malicious files
• Arbitrary object access
• CDN bypass
• Playback URL theft
• Content scraping
• Upload flooding

Use:

• Signed uploads
• Object isolation
• File validation
• Malware scanning
• Short-lived playback authorization
• Rate limiting

────────────────────────────────────────

PRIVACY ARCHITECTURE

Protect:

• User identity
• Behavioral data
• Watch history
• Search history
• Messaging
• Private videos
• Private collections
• Creator analytics
• Moderation data
• Fraud signals

Support:

• Data export
• Data deletion
• Retention
• Access control
• Audit

────────────────────────────────────────

THREAT MODEL

Evaluate:

• Account takeover
• Credential stuffing
• Video scraping
• Playback credential theft
• Malicious upload
• Bot engagement
• Fake accounts
• Spam
• Comment abuse
• Messaging abuse
• Search scraping
• Recommendation scraping
• Moderation abuse
• Admin privilege escalation
• Privacy leakage
• CDN abuse
• Supply-chain attack
• DDoS

For each define:

• Prevention
• Detection
• Response
• Recovery
• Audit

────────────────────────────────────────

OBSERVABILITY

Design metrics/logs/traces for:

• Authentication
• Uploads
• Video processing
• Feed generation
• Recommendation serving
• Search
• Playback authorization
• Engagement
• Messaging
• Notifications
• Moderation
• Advertising
• Analytics

Critical metrics:

• Upload success
• Processing latency
• Processing failure
• Feed latency
• Recommendation latency
• Search latency
• Playback authorization latency
• CDN error rate
• Queue depth
• Kafka lag
• WebSocket connections
• Moderation backlog

Never log:

• Passwords
• Tokens
• Secrets
• Private messages
• Signed playback credentials
• Sensitive behavioral data unnecessarily

────────────────────────────────────────

SLO / SLI

Define SLOs for:

• Authentication
• Feed generation
• Search
• Playback authorization
• Upload initialization
• Upload completion state
• Video processing
• Messaging
• Notifications
• Moderation queue processing
• Recommendation serving

For each define:

• SLI
• Measurement source
• Target
• Alert threshold
• Error budget

────────────────────────────────────────

FAILURE SCENARIOS

Define graceful behavior for:

• PostgreSQL failure
• Redis failure
• Kafka failure
• BullMQ failure
• Search failure
• S3 failure
• CloudFront degradation
• Video-worker failure
• Recommendation failure
• Moderation failure
• Notification failure
• WebSocket failure
• Region failure

For each define:

• Detection
• Timeout
• Retry
• Fallback
• Degraded mode
• Recovery
• Reconciliation

────────────────────────────────────────

DISASTER RECOVERY

Define:

• RTO
• RPO
• PostgreSQL backup
• PITR
• S3 replication
• Search snapshots
• Kafka recovery
• Redis recovery
• EKS recovery

Define recovery procedures for:

• Database loss
• Video-processing failure
• Feed failure
• Search failure
• Region failure

────────────────────────────────────────

TESTING ARCHITECTURE

Define:

UNIT:

• Visibility
• Feed ranking
• Recommendation filters
• Engagement
• Moderation
• Privacy
• Rights
• Upload state
• Processing state

INTEGRATION:

• PostgreSQL
• Redis
• Kafka
• BullMQ
• Search
• S3
• WebSockets

CONTRACT:

• REST
• WebSockets
• Events

VIDEO:

• Upload
• Resume
• Processing
• Transcoding
• Renditions
• Manifest
• Playback authorization
• Delete

FEED:

• Candidate generation
• Ranking
• Pagination
• Diversity
• Cache
• Fallback

SECURITY:

• Authorization
• Signed access
• Upload security
• IDOR
• Rate limits

PERFORMANCE:

• Feed
• Search
• Video processing
• Playback authorization
• WebSockets

RESILIENCE:

• Dependency failures
• Worker failures
• Region failures

────────────────────────────────────────

ARCHITECTURAL DECISION RECORDS

Create ADRs for:

• Architecture style
• Video processing
• Video streaming
• CDN
• Upload architecture
• Feed architecture
• Fan-out strategy
• Recommendation architecture
• Search
• Social graph
• Redis caching
• Kafka
• Moderation
• Copyright/rights
• Sounds
• Messaging
• Multi-region
• Privacy
• Deletion
• Observability
• Infrastructure

Each ADR must contain:

• Context
• Decision
• Alternatives considered
• Consequences

────────────────────────────────────────

ARCHITECTURE VOLUME 1 OUTPUT

Produce:

1. Executive Architecture Overview
2. System Context
3. Architectural Approach
4. System Architecture
5. Client Architecture
6. Domain Decomposition
7. Service Decomposition
8. Service Ownership Matrix
9. Communication Matrix
10. Monorepo Architecture
11. Detailed Folder Hierarchy
12. Identity Architecture
13. Creator Architecture
14. Social Graph Architecture
15. Social-Graph Scalability
16. Video Architecture
17. Upload Architecture
18. Video Asset Model
19. Video Processing Architecture
20. Video Renditions
21. CDN Architecture
22. Playback Authorization
23. Content Visibility
24. Video Deletion
25. Sound Architecture
26. Rights Architecture
27. Hashtag Architecture
28. Mention Architecture
29. Engagement Architecture
30. Like Architecture
31. Comment Architecture
32. Share Architecture
33. Save/Collection Architecture
34. For You Feed
35. Feed Candidate Architecture
36. Following Feed
37. Recommendation Architecture
38. Recommendation Safety
39. Feed Pagination
40. Diversity
41. Trending
42. Search Architecture
43. Messaging
44. Notifications
45. Moderation Architecture
46. Content Safety
47. Reporting
48. Copyright/Rights Enforcement
49. Advertising Architecture
50. Creator Analytics
51. Analytics Architecture
52. Event-Driven Architecture
53. Event Catalog
54. Queue Architecture
55. Database Architecture
56. Database Scalability
57. Redis Architecture
58. Search Index Architecture
59. Media Storage
60. Video Processing Scalability
61. Multi-Region Architecture
62. Regional Content Ownership
63. Security Architecture
64. Video Security
65. Privacy Architecture
66. Threat Model
67. Observability
68. SLO/SLI
69. Failure Scenarios
70. Disaster Recovery
71. Testing Architecture
72. Architectural Decision Records

────────────────────────────────────────

QUALITY REQUIREMENTS

Every architectural decision must evaluate:

• Scalability
• Availability
• Security
• Privacy
• Feed latency
• Video delivery performance
• Recommendation quality
• Data consistency
• Operational complexity
• Cost
• Developer productivity
• Maintainability
• Future extensibility

Prefer:

• Queue-driven video processing
• Direct-to-object-storage upload
• CDN video delivery
• Hybrid feed fan-out
• Cursor-based pagination
• Event-driven analytics
• Idempotent event consumers
• Transactional outbox
• Strong visibility enforcement
• Rebuildable search
• Regional processing
• Graceful degradation
• Provider abstraction

Avoid:

• Video bytes through API servers
• Synchronous transcoding
• Global fan-out on every creator post
• Massive synchronous follower writes
• Private videos in public search
• Redis as source of truth
• Recommendation generation blocking upload
• Unlimited raw telemetry in PostgreSQL
• Unbounded WebSocket fan-out
• Single-point-of-failure recommendation systems
• Frontend-only authorization
• Hard coupling to one storage/CDN/provider

────────────────────────────────────────

OUTPUT RULES

This is an architecture document only.

Do not generate source code.

Do not generate Dockerfiles.

Do not generate Kubernetes manifests.

Do not generate Terraform files.

Do not generate CI/CD files.

Do not generate frontend components.

Do not generate mobile components.

Do not implement backend services.

Provide architecture, specifications, contracts, diagrams, schemas, ownership rules, ADRs, operational strategies, and implementation guidance.

The resulting architecture must be sufficiently detailed that separate backend, web, mobile, video infrastructure, recommendation, infrastructure, DevOps, QA, security, moderation, and analytics teams can implement the platform without making major architectural decisions themselves.
