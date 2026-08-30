
You are operating in Senior Engineering Team Mode.

Complete the remaining enterprise architecture for a production-ready global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

Use the approved architecture as the single source of truth.

Do not restart the architecture.

Do not implement backend code.

Do not implement frontend code.

Do not implement mobile code.

Do not generate Dockerfiles.

Do not generate Kubernetes manifests.

Do not generate Terraform files.

Do not generate CI/CD workflows.

Do not generate application source code.

Produce architecture, specifications, contracts, schemas, diagrams, ownership rules, state machines, engineering decisions, security models, operational strategies, and implementation guidance only.

────────────────────────────────────────

VOLUME 2 OBJECTIVE

Complete the advanced architecture for:

1. High-scale video ingestion
2. Resumable uploads
3. Media processing
4. Adaptive streaming
5. CDN architecture
6. Feed generation
7. Recommendation systems
8. Ranking
9. Personalization
10. Exploration
11. Trending
12. Social graph scalability
13. Engagement
14. Comments
15. Messaging
16. Notifications
17. Moderation
18. Content safety
19. Copyright and rights
20. Advertising
21. Creator analytics
22. Platform analytics
23. Privacy
24. Data export
25. Data deletion
26. Fraud and abuse
27. Search
28. Real-time systems
29. Multi-region architecture
30. Disaster recovery
31. Security
32. Observability
33. Capacity planning
34. Data consistency
35. Event contracts
36. Queue contracts
37. Administrative architecture
38. Backend implementation roadmap
39. Frontend implementation roadmap
40. Mobile implementation roadmap
41. Infrastructure implementation roadmap
42. QA implementation roadmap
43. Complete Project Index

────────────────────────────────────────

VIDEO INGESTION ARCHITECTURE

Complete the production video-upload architecture.

Flow:

Client
→ Upload Session
→ Direct Object Storage Upload
→ Upload Completion
→ Validation
→ Security Scan
→ Metadata Extraction
→ Processing Queue
→ Transcoding
→ Moderation
→ Packaging
→ Publication
→ CDN

Define:

• Upload session ownership
• Upload authorization
• Chunk size
• Multipart strategy
• Checksum validation
• Resume behavior
• Cancellation
• Expiration
• Cleanup
• Duplicate detection
• Upload quotas

The API layer must not proxy large video files unnecessarily.

────────────────────────────────────────

UPLOAD SESSION

Define:

• Upload ID
• User ID
• Video ID
• Object key
• Expected size
• Uploaded parts
• Checksum
• State
• Expiration
• Region
• Creation time

States:

• Created
• Uploading
• Paused
• Completing
• Completed
• Failed
• Canceled
• Expired

Define valid transitions.

────────────────────────────────────────

UPLOAD SECURITY

Protect against:

• Arbitrary object access
• Oversized files
• Malicious content
• MIME-type spoofing
• Path traversal
• Unauthorized upload
• Upload flooding
• Expired session reuse

Use:

• Short-lived signed upload authorization
• Server-side object validation
• Malware scanning
• File-type verification
• Size limits
• Quotas

────────────────────────────────────────

VIDEO PROCESSING STATE MACHINE

Define:

• Uploaded
• Validating
• Scanning
• Metadata Extraction
• Processing
• Transcoding
• Moderation
• Packaging
• Ready
• Published
• Restricted
• Failed
• Retrying
• Deleted

Every state transition must be:

• Idempotent
• Auditable
• Recoverable

────────────────────────────────────────

MEDIA PROCESSING PIPELINE

Define worker stages:

1. Input validation
2. Malware/security scanning
3. Container validation
4. Metadata extraction
5. Audio extraction
6. Video normalization
7. Transcoding
8. Thumbnail generation
9. Preview generation
10. Caption processing
11. Packaging
12. Quality validation
13. Moderation integration
14. Publication

Each stage should produce durable status.

────────────────────────────────────────

TRANSCODING ARCHITECTURE

Define:

• Source codec
• Output codecs
• Resolution ladder
• Bitrate ladder
• Frame rate
• Keyframe interval
• Audio settings
• Presets
• Hardware acceleration

Evaluate:

• CPU workers
• GPU workers
• Specialized media instances

Scale according to workload.

────────────────────────────────────────

ADAPTIVE STREAMING

Define HLS/DASH architecture.

Support:

• Master manifest
• Variant playlists
• Segments
• Bitrate
• Resolution
• Codec
• Audio tracks

Define:

• Segment duration
• Cache behavior
• Manifest expiration
• Access authorization

Do not expose private media through permanent public URLs.

────────────────────────────────────────

CDN SECURITY

Protect CDN media with:

• Origin access control
• Signed URLs/cookies or equivalent
• Short-lived playback authorization
• Origin protection
• Cache policy
• Rate controls where appropriate

Ensure direct origin access is restricted.

────────────────────────────────────────

VIDEO DELIVERY OPTIMIZATION

Optimize for:

• First-frame latency
• Segment cache hit ratio
• Global latency
• Bandwidth efficiency
• Mobile networks
• Low-end devices

Evaluate:

• Multiple bitrate ladders
• Regional caching
• Prewarming
• Adaptive bitrate
• Compression

────────────────────────────────────────

VIDEO RETENTION

Define policies for:

• Original uploads
• Intermediate processing assets
• Master videos
• Renditions
• Thumbnails
• Previews
• Captions
• Deleted media
• Failed uploads

Use object-storage lifecycle policies.

────────────────────────────────────────

ORPHANED MEDIA

Define reconciliation for:

• Objects without database records
• Database records without objects
• Failed processing artifacts
• Expired uploads
• Deleted content still in storage

Do not delete media solely based on one inconsistent signal.

────────────────────────────────────────

FEED ARCHITECTURE

Complete feed generation.

FOR YOU:

Request
→ Candidate Retrieval
→ Eligibility
→ Safety
→ Filtering
→ Ranking
→ Re-ranking
→ Diversity
→ Exploration
→ Response

FOLLOWING:

Follow Graph
→ Candidate Retrieval
→ Eligibility
→ Ranking
→ Diversity
→ Response

TRENDING:

Events
→ Aggregation
→ Decay
→ Anti-Abuse
→ Ranking
→ Trending Set

────────────────────────────────────────

CANDIDATE GENERATION

Sources:

• Followed creators
• Watch history
• Likes
• Comments
• Shares
• Saves
• Sound affinity
• Hashtag affinity
• Creator affinity
• Similar content
• Trending
• New content
• Regional trends
• Exploration
• Editorial content

Define candidate quotas by source.

────────────────────────────────────────

ELIGIBILITY FILTER

Before ranking, remove content that violates:

• Visibility
• User blocks
• Creator blocks
• Moderation
• Age restrictions
• Rights
• Region
• Safety policies
• Feature availability

Eligibility must be authoritative.

────────────────────────────────────────

RANKING ARCHITECTURE

Define ranking stages:

• Retrieval ranking
• Lightweight ranking
• Heavy ranking
• Re-ranking

Features may include:

• Watch probability
• Completion probability
• Rewatch probability
• Like probability
• Comment probability
• Share probability
• Save probability
• Follow probability
• Freshness
• Creator affinity
• Sound affinity
• Topic affinity
• Negative feedback
• Safety
• Diversity

Do not expose internal model scores to users.

────────────────────────────────────────

EXPLORATION / EXPLOITATION

Support controlled exploration.

Exploration sources:

• New creators
• New topics
• New sounds
• New content
• Under-exposed content

Define:

• Exploration percentage
• Eligibility
• Safety checks
• Feedback signals
• Experimentation

Do not allow exploration to bypass safety or rights.

────────────────────────────────────────

RECOMMENDATION FEEDBACK LOOP

Track:

• Impression
• Start
• Watch duration
• Completion
• Rewatch
• Skip
• Like
• Comment
• Share
• Save
• Follow
• Not interested
• Report

Feed these signals asynchronously into recommendation systems.

────────────────────────────────────────

NEGATIVE SIGNALS

Support:

• Skip
• Not interested
• Hide creator
• Hide sound
• Report
• Unfollow
• Block

Negative signals must have appropriate ranking weight.

────────────────────────────────────────

FEED CONSISTENCY

Define behavior when:

• Content is deleted after candidate generation
• Creator is blocked
• Rights expire
• Moderation changes
• User logs out
• Region changes

The final eligibility layer must run close to delivery.

────────────────────────────────────────

FEED PAGINATION

Use cursor-based pagination.

Cursor should account for:

• Feed generation timestamp
• Ranking version
• Candidate set/version
• Page state
• Expiration

Do not depend on mutable offset positions.

────────────────────────────────────────

FEED CACHE

Define caches for:

• Personalized feed candidates
• Following feed
• Trending
• Creator recommendations
• Sound recommendations

Use:

• TTL
• User scoping
• Region
• Version
• Stampede protection

Never allow private personalized data to leak through shared cache keys.

────────────────────────────────────────

SOCIAL GRAPH

Complete high-scale graph architecture.

Support:

• Followers
• Following
• Mutual relationships
• Block
• Unblock
• Mute where appropriate

Define:

• Authoritative relationship store
• Read model
• Cached counts
• High-fanout strategy

────────────────────────────────────────

HIGH-FANOUT CREATORS

For creators with millions of followers:

• Do not synchronously write every follower feed entry.
• Use asynchronous fan-out.
• Use hybrid fan-out.
• Maintain creator content as candidate sources.

────────────────────────────────────────

ENGAGEMENT COUNTERS

Design scalable counters for:

• Views
• Likes
• Comments
• Shares
• Saves
• Followers
• Sound usage

Separate:

• Authoritative relationship
• Event stream
• Derived aggregate count

Define reconciliation.

────────────────────────────────────────

COMMENT SYSTEM

Complete architecture for:

• Comments
• Replies
• Likes
• Pinning
• Deletion
• Moderation
• Reporting

Define:

• Pagination
• Sort order
• Ranking
• Spam controls
• Rate limits

────────────────────────────────────────

COMMENT RANKING

Support:

• Relevance
• Recency
• Engagement
• Creator pinning
• Safety
• Spam suppression

Never let engagement alone override safety policies.

────────────────────────────────────────

MESSAGING ARCHITECTURE

Complete direct messaging.

Support:

• One-to-one
• Group conversations where justified
• Messages
• Read state
• Delivery state
• Attachments
• Blocking
• Reporting
• Notifications

Define:

• Conversation authorization
• Message ordering
• Idempotency
• Delivery guarantees
• Retention

────────────────────────────────────────

REAL-TIME MESSAGING

Use WebSockets.

Support:

• Connection authentication
• Conversation authorization
• Message delivery
• Read receipts
• Reconnect
• Duplicate detection
• Backpressure

Persist messages before or in conjunction with real-time delivery so disconnects do not lose authoritative history.

────────────────────────────────────────

NOTIFICATIONS

Define notification architecture for:

• Follow
• Like
• Comment
• Reply
• Mention
• Share
• Message
• Creator updates
• Moderation
• Security
• System

Support:

• Push
• In-app
• Email where appropriate

Define:

• Preferences
• Deduplication
• Retry
• Rate limits
• Localization

────────────────────────────────────────

MODERATION ARCHITECTURE

Complete:

Content
→ Detection
→ Classification
→ Policy
→ Human Review
→ Enforcement
→ Appeal
→ Resolution

Moderate:

• Videos
• Captions
• Comments
• Messages
• Profiles
• Sounds
• Hashtags

────────────────────────────────────────

CONTENT MODERATION STATES

Support:

• Pending
• Under Review
• Approved
• Restricted
• Removed
• Appealed
• Reinstated

Define whether content is:

• Visible
• Searchable
• Recommended
• Playable
• Commentable

for every state.

────────────────────────────────────────

CONTENT SAFETY

Define policy architecture for:

• Harassment
• Hate
• Violence
• Sexual content
• Dangerous activities
• Self-harm
• Illegal content
• Spam
• Fraud
• Child-safety protections
• Copyright violations

The safety system must support:

• Automated classifiers
• Human review
• Appeals
• Policy updates

────────────────────────────────────────

COPYRIGHT / RIGHTS ENGINE

Support rights for:

• Videos
• Sounds
• Music
• Regions
• Platforms
• Effective dates

Rights may impact:

• Playback
• Feed
• Search
• Recommendations
• Sound availability
• Monetization

────────────────────────────────────────

TAKEDOWN WORKFLOW

Support:

• Claim
• Review
• Restriction
• Removal
• Appeal
• Restoration

Every rights action must be auditable.

────────────────────────────────────────

ADVERTISING ARCHITECTURE

Define:

Advertiser
→ Campaign
→ Ad Group
→ Creative
→ Placement
→ Eligibility
→ Delivery
→ Impression
→ Completion
→ Reporting

Support:

• Budget
• Scheduling
• Frequency cap
• Targeting
• Creative approval
• Campaign state

────────────────────────────────────────

AD TARGETING

Support configurable targeting using permitted signals such as:

• Region
• Language
• Context
• Device category
• Broad audience attributes

Do not use sensitive personal characteristics for prohibited targeting.

────────────────────────────────────────

AD SAFETY

Ads must pass:

• Policy
• Creative moderation
• Landing-page validation
• Eligibility
• Regional restrictions

Do not let advertising bypass content-safety controls.

────────────────────────────────────────

CREATOR ANALYTICS

Define:

• Views
• Watch time
• Completion
• Likes
• Comments
• Shares
• Saves
• Followers
• Traffic source
• Sound usage
• Audience geography
• Audience demographics where permitted

Ensure creators only access authorized analytics.

────────────────────────────────────────

PLATFORM ANALYTICS

Track:

• DAU
• WAU
• MAU
• Retention
• Sessions
• Watch time
• Completion
• Engagement
• Creator activity
• Upload volume
• Processing latency
• CDN performance
• Search
• Recommendation
• Moderation
• Advertising

Keep analytical workloads separate from transactional workloads.

────────────────────────────────────────

PRIVACY ARCHITECTURE

Define:

• Data classification
• Data retention
• Data access
• Data export
• Data deletion
• User controls
• Recommendation controls
• Advertising controls

Classify:

• Identity data
• Content
• Social graph
• Behavioral data
• Analytics
• Messages
• Moderation
• Fraud
• Audit

────────────────────────────────────────

DATA EXPORT

Support:

• Request
• Scope
• Processing
• Secure package
• Expiration
• Download authorization

Use asynchronous processing.

────────────────────────────────────────

DATA DELETION

Define deletion/anonymization workflows.

Account deletion may affect:

• Profile
• Videos
• Comments
• Likes
• Follows
• Messages
• Collections
• Analytics references

Some records may require retention due to:

• Legal
• Financial
• Safety
• Security
• Audit

requirements.

────────────────────────────────────────

FRAUD AND ABUSE

Design controls against:

• Fake accounts
• Fake followers
• Fake views
• Bot likes
• Bot comments
• Bot shares
• Recommendation manipulation
• Search manipulation
• Promo abuse
• Advertising fraud
• Account takeover
• Upload abuse

Use:

• Rate limits
• Device signals
• Behavioral signals
• Graph signals
• Risk scoring
• Manual review

────────────────────────────────────────

ENGAGEMENT FRAUD

Detect:

• Coordinated accounts
• Repeated device patterns
• Suspicious viewing loops
• Artificial engagement
• Rapid account networks
• Unusual geographic patterns

Do not automatically penalize legitimate users based on one noisy signal.

────────────────────────────────────────

SEARCH ARCHITECTURE

Complete search for:

• Videos
• Creators
• Hashtags
• Sounds

Define:

• Ingestion
• Indexing
• Ranking
• Autocomplete
• Typo tolerance
• Region
• Safety
• Visibility
• Deletion
• Reindexing

────────────────────────────────────────

SEARCH FRESHNESS

Define target freshness for:

• New videos
• New creators
• New hashtags
• New sounds
• Deleted content
• Restricted content

Search must eventually converge to authoritative state.

────────────────────────────────────────

MULTI-REGION

Define:

• User region
• Content processing region
• Feed region
• Recommendation region
• Search region
• Moderation region
• Analytics region

Keep latency-sensitive operations regionally close.

────────────────────────────────────────

GLOBAL CDN

Use global CDN distribution for:

• Video
• Thumbnails
• Posters
• Static assets

Define:

• Regional cache
• Origin failover
• Cache invalidation
• Signed access
• Traffic management

────────────────────────────────────────

REGIONAL FAILURE

Define behavior when:

• API region fails
• Feed region fails
• Recommendation region fails
• Search fails
• Media processing region fails
• WebSocket region fails
• Database region fails

Prioritize:

• Existing playback
• Safety
• Account security
• Content integrity

────────────────────────────────────────

FAILURE MODES

For every major dependency define:

• Detection
• Timeout
• Retry
• Circuit breaker
• Fallback
• Degraded mode
• Recovery
• Reconciliation

────────────────────────────────────────

DISASTER RECOVERY

Define:

• RTO
• RPO
• PostgreSQL recovery
• S3 recovery
• Kafka recovery
• Redis recovery
• Search rebuild
• EKS reconstruction
• CDN/origin recovery

Video media must remain recoverable independently from transactional metadata.

────────────────────────────────────────

OBSERVABILITY

Define metrics, logs, and traces for:

• Uploads
• Video processing
• Feed generation
• Recommendation
• Search
• Playback authorization
• CDN
• Messaging
• Notifications
• Moderation
• Advertising
• Analytics
• Privacy

Critical metrics:

• Upload success
• Processing latency
• Feed latency
• Recommendation latency
• Search latency
• First-frame latency
• CDN cache hit ratio
• WebSocket connections
• Queue depth
• Consumer lag
• Moderation backlog

────────────────────────────────────────

SLO / SLI

Define measurable SLOs for:

• Authentication
• Feed generation
• Search
• Playback authorization
• Upload initialization
• Upload completion
• Video processing
• Messaging
• Notifications
• Moderation
• Analytics ingestion

For each:

• SLI
• Measurement
• Target
• Error budget
• Alert threshold

────────────────────────────────────────

CAPACITY PLANNING

Model:

• Users
• Daily active users
• Creators
• Uploads/day
• Video bytes/day
• Watch minutes/day
• Feed requests
• Recommendation requests
• Search requests
• Messages
• Notifications
• Moderation events
• Advertising events

Estimate:

• Storage
• Bandwidth
• CPU
• GPU where relevant
• Redis memory
• Kafka throughput
• Search capacity
• Database capacity

────────────────────────────────────────

DATA CONSISTENCY

Define consistency models for:

STRONG:

• Identity
• Permissions
• Content ownership
• Visibility changes
• Rights enforcement
• Moderation enforcement
• Account deletion authorization

EVENTUAL:

• Likes count
• View count
• Follower count
• Trending
• Search index
• Recommendations
• Analytics
• Notifications

Clearly define acceptable staleness.

────────────────────────────────────────

EVENT CONTRACTS

For every core event define:

• Event name
• Version
• Producer
• Consumers
• Partition key
• Ordering requirement
• Schema
• Privacy classification
• Retention
• Replay policy
• Idempotency

────────────────────────────────────────

QUEUE CONTRACTS

For every queue define:

• Producer
• Consumer
• Job schema
• Retry
• Backoff
• Timeout
• Concurrency
• Dead-letter policy
• Scaling signal
• Monitoring

────────────────────────────────────────

ADMINISTRATION ARCHITECTURE

Support administrators for:

• Users
• Creators
• Videos
• Sounds
• Hashtags
• Reports
• Moderation
• Rights
• Advertising
• Analytics
• Feature flags
• Configuration
• Privacy
• Audit

Use least privilege.

────────────────────────────────────────

ADMIN SECURITY

High-risk actions require:

• Explicit permission
• Reason
• Audit
• Confirmation
• Additional approval where configured

Examples:

• Delete content
• Restore content
• Suspend creator
• Modify rights
• Change moderation state
• Change feature flag
• Change configuration
• Access sensitive privacy data

────────────────────────────────────────

FEATURE FLAGS

Support:

• Global
• Environment
• Region
• Platform
• App version
• User cohort
• Creator cohort
• Percentage rollout

Support:

• Canary
• Kill switch
• Rollback
• Expiration
• Audit

Never use feature flags as authorization.

────────────────────────────────────────

SYSTEM CONFIGURATION

Support configuration for:

• Feed limits
• Ranking weights
• Exploration percentage
• Upload limits
• Processing policies
• Moderation thresholds
• Search behavior
• Notification limits
• Rate limits
• Trending windows
• CDN settings

All configuration must be:

• Typed
• Validated
• Versioned
• Audited
• Rollback-capable

────────────────────────────────────────

SECURITY ARCHITECTURE

Complete:

• Authentication
• Authorization
• RBAC
• Object-level authorization
• Rate limits
• WAF
• Secure uploads
• Signed media access
• Secrets management
• Encryption
• Audit
• Network security
• Supply-chain security

────────────────────────────────────────

THREAT MODEL

Analyze:

• Account takeover
• Credential stuffing
• Upload abuse
• Malicious media
• CDN scraping
• Playback credential theft
• Bot engagement
• Fake accounts
• Search abuse
• Recommendation abuse
• Messaging abuse
• Moderation abuse
• Privacy leakage
• Admin compromise
• Supply-chain attacks
• DDoS

For each:

• Prevention
• Detection
• Response
• Recovery

────────────────────────────────────────

TESTING ARCHITECTURE

Define:

UNIT:

• Upload state
• Processing state
• Visibility
• Rights
• Feed ranking
• Eligibility
• Engagement
• Moderation
• Privacy
• Feature flags

INTEGRATION:

• PostgreSQL
• Redis
• Kafka
• BullMQ
• OpenSearch
• S3
• WebSockets

CONTRACT:

• REST
• WebSockets
• Events
• Queue payloads

VIDEO:

• Upload
• Resume
• Processing
• Transcoding
• Packaging
• CDN authorization
• Deletion

FEED:

• Candidate generation
• Eligibility
• Ranking
• Diversity
• Pagination
• Cache
• Fallback

SECURITY:

• IDOR
• Signed access
• Upload security
• Rate limits
• Admin authorization

PERFORMANCE:

• Upload
• Processing
• Feed
• Search
• Recommendation
• Playback authorization
• WebSockets

RESILIENCE:

• Worker failure
• Dependency failure
• Region failure

────────────────────────────────────────

ARCHITECTURAL DECISION RECORDS

Create ADRs for:

• Architecture style
• Video ingestion
• Direct upload
• Video processing
• Transcoding
• Adaptive streaming
• CDN
• Feed architecture
• Fan-out strategy
• Recommendation architecture
• Ranking
• Exploration
• Trending
• Social graph
• Engagement counters
• Search
• Messaging
• Moderation
• Copyright/rights
• Advertising
• Analytics
• Privacy
• Data deletion
• Multi-region
• Disaster recovery
• Observability
• Security
• Infrastructure

Each ADR must contain:

• Context
• Decision
• Alternatives considered
• Consequences

────────────────────────────────────────

IMPLEMENTATION ROADMAP

Define the exact implementation sequence.

BACKEND

Milestone 1:
Foundation and platform infrastructure.

Milestone 2:
Identity, accounts, profiles, sessions, devices.

Milestone 3:
Creators, verification, social graph.

Milestone 4:
Video upload, assets, storage, processing.

Milestone 5:
Transcoding, packaging, playback authorization, CDN integration.

Milestone 6:
Engagement, comments, shares, saves, collections.

Milestone 7:
Feed candidates, Following feed, For You foundation.

Milestone 8:
Recommendation, ranking, exploration, trending.

Milestone 9:
Search, sounds, hashtags, mentions.

Milestone 10:
Messaging, notifications, moderation, reporting.

Milestone 11:
Rights, advertising, creator analytics, platform analytics.

Milestone 12:
Privacy, administration, feature flags, configuration, audit.

Milestone 13:
Fraud/abuse, reconciliation, security hardening.

Milestone 14:
Performance, resilience, disaster recovery, production readiness.

FRONTEND

Milestone 1:
Foundation, authentication, design system.

Milestone 2:
Feed, video player, discovery.

Milestone 3:
Profiles, follow, engagement.

Milestone 4:
Upload/creator tools.

Milestone 5:
Search, sounds, hashtags.

Milestone 6:
Messaging, notifications, moderation interactions.

Milestone 7:
Creator analytics, administration.

Milestone 8:
Privacy, accessibility, localization, performance.

MOBILE

Milestone 1:
Foundation, navigation, authentication.

Milestone 2:
Feed, video player, discovery.

Milestone 3:
Profiles, follows, engagement.

Milestone 4:
Upload, creator tools, drafts.

Milestone 5:
Search, sounds, hashtags.

Milestone 6:
Messaging, notifications.

Milestone 7:
Offline-aware behavior, privacy, accessibility.

Milestone 8:
Performance, security, E2E, production readiness.

INFRASTRUCTURE

Milestone 1:
Terraform, networking, IAM.

Milestone 2:
EKS, Kubernetes, Helm.

Milestone 3:
PostgreSQL, Redis, Kafka, OpenSearch.

Milestone 4:
S3, CloudFront, Route 53, WAF.

Milestone 5:
Video-processing worker infrastructure.

Milestone 6:
Autoscaling and workload-specific infrastructure.

Milestone 7:
CI/CD and container security.

Milestone 8:
Observability and SLOs.

Milestone 9:
Multi-region and disaster recovery.

Milestone 10:
Security hardening, testing, cost controls, production readiness.

QA

Milestone 1:
Testing infrastructure.

Milestone 2:
Identity/social/content.

Milestone 3:
Video pipeline/CDN.

Milestone 4:
Feed/recommendations/search.

Milestone 5:
Engagement/messaging/notifications.

Milestone 6:
Moderation/rights/advertising.

Milestone 7:
Security/privacy/abuse.

Milestone 8:
Performance/load/stress/soak.

Milestone 9:
Resilience/chaos/disaster recovery.

Milestone 10:
Production certification.

────────────────────────────────────────

ARCHITECTURE VOLUME 2 OUTPUT

Produce:

1. Video Ingestion Architecture
2. Upload Session Architecture
3. Upload Security
4. Video Processing State Machine
5. Media Processing Pipeline
6. Transcoding Architecture
7. Adaptive Streaming
8. CDN Security
9. Video Delivery Optimization
10. Video Retention
11. Orphaned Media Reconciliation
12. Feed Architecture
13. Candidate Generation
14. Eligibility Filtering
15. Ranking Architecture
16. Exploration/Exploitation
17. Recommendation Feedback Loop
18. Negative Signals
19. Feed Consistency
20. Feed Pagination
21. Feed Cache
22. Social Graph
23. High-Fanout Strategy
24. Engagement Counters
25. Comment Architecture
26. Comment Ranking
27. Messaging Architecture
28. Real-Time Messaging
29. Notification Architecture
30. Moderation Architecture
31. Content Moderation States
32. Content Safety
33. Copyright/Rights Engine
34. Takedown Workflow
35. Advertising Architecture
36. Ad Targeting
37. Ad Safety
38. Creator Analytics
39. Platform Analytics
40. Privacy Architecture
41. Data Export
42. Data Deletion
43. Fraud and Abuse
44. Engagement Fraud
45. Search Architecture
46. Search Freshness
47. Multi-Region
48. Global CDN
49. Regional Failure
50. Failure Modes
51. Disaster Recovery
52. Observability
53. SLO/SLI
54. Capacity Planning
55. Data Consistency
56. Event Contracts
57. Queue Contracts
58. Administration Architecture
59. Admin Security
60. Feature Flags
61. System Configuration
62. Security Architecture
63. Threat Model
64. Testing Architecture
65. Architectural Decision Records
66. Backend Implementation Roadmap
67. Frontend Implementation Roadmap
68. Mobile Implementation Roadmap
69. Infrastructure Implementation Roadmap
70. QA Implementation Roadmap
71. Complete Project Index

────────────────────────────────────────

QUALITY REQUIREMENTS

Every architectural decision must evaluate:

• Scalability
• Availability
• Security
• Privacy
• Feed latency
• Video-delivery latency
• Processing throughput
• Recommendation quality
• Data consistency
• Operational complexity
• Cost
• Developer productivity
• Maintainability
• Future extensibility

Prefer:

• Direct-to-object-storage uploads
• Queue-driven processing
• Immutable media identifiers
• CDN-first delivery
• Hybrid feed fan-out
• Cursor-based pagination
• Event-driven analytics
• Idempotent consumers
• Transactional outbox
• Strong visibility and rights enforcement
• Rebuildable search
• Regional processing
• Graceful degradation
• Provider abstraction
• Explicit data ownership

Avoid:

• Large media through API servers
• Synchronous transcoding
• Global synchronous feed fan-out
• Massive synchronous follower writes
• Private content in public search
• Redis as source of truth
• Recommendation blocking upload
• Unbounded WebSocket fan-out
• Permanent raw telemetry in PostgreSQL
• Search as authoritative content storage
• Feature flags as authorization
• Frontend-only safety enforcement
• Single points of failure
• Hard coupling to one cloud/media/search provider

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

Provide detailed:

• Architecture specifications
• Domain boundaries
• Service responsibilities
• State machines
• Data ownership
• API contracts
• Event contracts
• Queue contracts
• Feed architecture
• Recommendation architecture
• Media architecture
• Search architecture
• Moderation architecture
• Advertising architecture
• Privacy architecture
• Security architecture
• Multi-region architecture
• Disaster recovery
• Testing architecture
• ADRs
• Implementation roadmaps
• Project Index

The resulting architecture must be sufficiently detailed that separate backend, web, mobile, media infrastructure, recommendation, search, moderation, advertising, analytics, infrastructure, DevOps, QA, and security teams can implement the complete platform without making major architectural decisions themselves.
