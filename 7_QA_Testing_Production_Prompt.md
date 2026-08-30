You are operating in Senior Engineering Team Mode.

Build the complete production-grade QA, testing, security validation, privacy validation, performance validation, resilience validation, accessibility validation, infrastructure validation, and production-readiness system for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

Use the approved backend, frontend, mobile, video infrastructure, recommendation, search, moderation, advertising, analytics, infrastructure, and security architecture as the single source of truth.

Do not redesign the architecture.

Do not implement unrelated product features.

────────────────────────────────────────

MISSION

Build a complete quality-engineering system covering:

• Unit testing
• Integration testing
• API testing
• Contract testing
• WebSocket testing
• Event testing
• Queue testing
• Database testing
• Redis testing
• Search testing
• S3/media testing
• Video-processing testing
• Transcoding testing
• Playback testing
• CDN testing
• Feed testing
• Recommendation testing
• Ranking testing
• Trending testing
• Social-graph testing
• Engagement testing
• Comment testing
• Messaging testing
• Notification testing
• Moderation testing
• Rights/copyright testing
• Advertising testing
• Creator analytics testing
• Platform analytics testing
• Privacy testing
• Administration testing
• Feature-flag testing
• Configuration testing
• Web frontend testing
• Mobile testing
• Accessibility testing
• Security testing
• Abuse testing
• Performance testing
• Load testing
• Stress testing
• Soak testing
• Resilience testing
• Chaos testing
• Disaster-recovery testing
• Backup restoration testing
• Infrastructure testing
• CI/CD validation
• Production smoke testing
• Regression testing
• Release certification

The final QA system must provide objective evidence for:

• Functional correctness
• Video/media correctness
• Feed correctness
• Recommendation correctness
• Search correctness
• Security
• Privacy
• Availability
• Reliability
• Scalability
• Performance
• Accessibility
• Recoverability
• Maintainability
• Production readiness

────────────────────────────────────────

TECHNOLOGY STACK

BACKEND

• Node.js
• NestJS
• TypeScript
• PostgreSQL
• Prisma
• Redis
• Kafka/Redpanda
• BullMQ
• OpenSearch/Elasticsearch
• AWS S3
• WebSockets
• Socket.IO

WEB

• Next.js
• React
• TypeScript
• Tailwind CSS
• TanStack Query
• Zustand

MOBILE

• React Native
• Expo
• TypeScript
• React Navigation
• TanStack Query
• Zustand

MEDIA

• FFmpeg
• HLS
• CloudFront

INFRASTRUCTURE

• Docker
• Kubernetes
• Helm
• Terraform
• AWS
• GitHub Actions

OBSERVABILITY

• OpenTelemetry
• Prometheus
• Grafana
• Loki
• Tempo

TESTING

• Jest
• Supertest
• React Testing Library
• Playwright
• React Native Testing Library
• Detox or approved mobile E2E framework
• Load-testing framework
• Accessibility testing tools
• Security scanners
• Infrastructure validation tools

────────────────────────────────────────

TESTING PRINCIPLES

Use a layered test strategy.

Do not rely on E2E tests alone.

Use:

• Unit tests for pure domain logic
• Integration tests for real dependencies
• Contract tests for service boundaries
• API tests for REST endpoints
• WebSocket tests for real-time behavior
• Event tests for Kafka contracts
• Queue tests for BullMQ jobs
• E2E tests for critical journeys
• Performance tests for scale
• Security tests for attack resistance
• Resilience tests for failure behavior
• Recovery tests for operational readiness

Avoid:

• Arbitrary sleeps
• Test-order dependence
• Shared mutable test state
• Production credentials
• Production user data
• Real private messages
• Real payment credentials
• Real sensitive identity documents

────────────────────────────────────────

TEST PYRAMID

UNIT

Broad and fast.

INTEGRATION

Use real or production-equivalent:

• PostgreSQL
• Redis
• Kafka/Redpanda
• BullMQ
• OpenSearch
• S3-compatible storage
• WebSocket infrastructure where appropriate

CONTRACT

Validate:

• REST
• WebSockets
• Kafka events
• Queue payloads
• Webhooks

E2E

Validate:

• Consumer
• Creator
• Advertiser
• Administrator
• Moderator
• Privacy workflows

────────────────────────────────────────

TEST ENVIRONMENT

Provide isolated environments for:

• Unit
• Integration
• E2E
• Performance
• Security
• Resilience

Use deterministic synthetic data.

Do not use production data directly.

────────────────────────────────────────

TEST DATA FACTORIES

Create deterministic factories for:

• Users
• Accounts
• Profiles
• Creators
• Creator verification
• Followers
• Blocks
• Videos
• Video assets
• Upload sessions
• Renditions
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
• Feed sessions
• Recommendations
• Search documents
• Messages
• Notifications
• Reports
• Moderation cases
• Rights claims
• Advertisers
• Campaigns
• Ad groups
• Creatives
• Analytics events
• Privacy requests

Support:

• Small datasets
• Medium datasets
• Large synthetic datasets

────────────────────────────────────────

IDENTITY TESTING

Validate:

• Registration
• Login
• Logout
• Session refresh
• Session expiry
• Session revocation
• Password reset
• Email verification
• Device registration
• Account suspension
• Account deletion

Security cases:

• Credential stuffing
• Brute force
• Invalid credentials
• Session replay
• Token replay
• Revoked session access
• Password-reset token reuse
• Account enumeration

────────────────────────────────────────

PROFILE TESTING

Test:

• Profile creation
• Profile update
• Username uniqueness
• Reserved usernames
• Profile visibility
• Creator status
• Avatar references
• Block interactions

Prevent:

• Unauthorized profile modification
• Cross-user access
• Hidden-profile leakage

────────────────────────────────────────

CREATOR TESTING

Test:

• Creator application
• Verification
• Reverification
• Approval
• Rejection
• Suspension
• Restoration
• Content ownership
• Creator permissions

Provider cases:

• Timeout
• Duplicate callback
• Invalid response
• Out-of-order response
• Provider outage

────────────────────────────────────────

SOCIAL GRAPH TESTING

Test:

• Follow
• Unfollow
• Relationship lookup
• Followers
• Following
• Blocking
• Unblocking

Concurrency:

• Double follow
• Concurrent follow/unfollow
• Follow while blocked
• Block while following
• Unfollow during feed generation

Validate aggregate counter reconciliation.

────────────────────────────────────────

VIDEO UPLOAD TESTING

Test:

• Upload initialization
• Multipart upload
• Resume
• Pause
• Completion
• Cancellation
• Expiration
• Duplicate completion
• Missing object
• Checksum mismatch
• Size mismatch
• Unauthorized completion

Security:

• Object-key manipulation
• Path traversal
• Oversized input
• MIME spoofing
• Malicious file
• Unauthorized object access

────────────────────────────────────────

VIDEO PROCESSING TESTING

Test:

• Validation
• Security scan
• Metadata extraction
• Processing
• Transcoding
• Thumbnail generation
• Preview generation
• Caption processing
• Packaging
• Quality validation

Cases:

• Corrupt file
• Unsupported codec
• Invalid container
• Missing audio
• Missing video
• Oversized file
• Very long duration
• Multiple renditions
• Duplicate processing
• Worker crash
• Job retry
• Dead-letter

────────────────────────────────────────

TRANSCODING TESTING

Validate:

• Supported codecs
• Resolution ladder
• Bitrate ladder
• Frame rate
• Audio
• Keyframes
• Output naming
• Processing version

Verify no older processing job overwrites newer assets.

────────────────────────────────────────

HLS TESTING

Validate:

• Master manifest
• Variant playlists
• Segment existence
• Segment references
• Correct rendition mapping
• Manifest consistency
• Version consistency
• Secure access

Test partial-processing failures.

────────────────────────────────────────

PLAYBACK AUTHORIZATION TESTING

Test:

• Public video
• Followers-only video
• Private video
• Removed video
• Restricted video
• Moderation-restricted video
• Rights-restricted video
• Region-restricted video
• Blocked creator
• Expired authorization
• Token replay

Verify:

• Short-lived access
• No permanent unauthorized URL
• No origin bypass

────────────────────────────────────────

CDN TESTING

Validate:

• Cache behavior
• Origin access control
• Signed access
• Cache invalidation
• Deleted content
• Restricted content
• Expired authorization

Ensure deleted/private media is no longer accessible through stale authorization.

────────────────────────────────────────

ENGAGEMENT TESTING

Test:

• Like
• Unlike
• Comment
• Reply
• Comment like
• Share
• Save
• Collection
• Repost

Concurrency:

• Double like
• Like/unlike race
• Duplicate comment
• Concurrent collection changes
• Duplicate repost

Validate derived counters.

────────────────────────────────────────

COMMENT TESTING

Test:

• Pagination
• Reply hierarchy
• Ranking
• Pin
• Delete
• Moderation
• Report

Security:

• Comment IDOR
• Unauthorized deletion
• Unauthorized pin
• Private video comment leakage

────────────────────────────────────────

FEED TESTING

Test:

• For You
• Following
• Creator feed
• Trending
• Cursor pagination
• Refresh
• Cache
• Fallback

Eligibility must remove:

• Deleted content
• Restricted content
• Blocked creators
• Unavailable regions
• Expired rights

────────────────────────────────────────

FEED PAGINATION TESTING

Validate:

• Stable cursor
• Cursor expiration
• Duplicate prevention
• Candidate changes
• Ranking-version changes

Ensure clients do not receive duplicate or missing content due to pagination state.

────────────────────────────────────────

RECOMMENDATION TESTING

Test:

• Candidate generation
• Feature retrieval
• Ranking
• Re-ranking
• Diversity
• Freshness
• Exploration
• Negative feedback
• Seen-content filtering

Simulate:

• Missing features
• Recommendation dependency failure
• Model version change
• Experiment assignment
• Stale cache
• Deleted content

────────────────────────────────────────

RECOMMENDATION SAFETY

Verify recommendation never returns:

• Removed content
• Private content
• Blocked creators
• Regionally unavailable content
• Rights-expired content
• Safety-restricted content

────────────────────────────────────────

RANKING TESTING

Test deterministic behavior of:

• Weighted ranking
• Ranking-version changes
• Diversity
• Freshness
• Exploration

Do not require an exact production ML score.

Validate contract-level behavior and policy constraints.

────────────────────────────────────────

TRENDING TESTING

Test:

• Global trends
• Regional trends
• Sound trends
• Hashtag trends
• Creator trends
• Time decay
• Velocity
• Freshness

Anti-abuse:

• Bot engagement
• Burst attacks
• Coordinated engagement
• Artificial view generation

────────────────────────────────────────

SEARCH TESTING

Test:

• Video search
• Creator search
• Hashtag search
• Sound search
• Prefix search
• Full-text
• Autocomplete
• Typo tolerance
• Filters
• Region
• Language

Verify:

• Deleted content removed
• Private content excluded
• Restricted content excluded
• Index catches up after updates

────────────────────────────────────────

SEARCH REINDEX TESTING

Test:

• Full reindex
• Incremental indexing
• Alias switching
• Failed indexing
• Retry
• Deleted content
• Reindex validation

Search must remain rebuildable from authoritative data.

────────────────────────────────────────

MESSAGING TESTING

Test:

• Conversation creation
• Message creation
• Delivery
• Read
• Reconnect
• Ordering
• Duplicate suppression
• Attachments
• Block state
• Report

Concurrency:

• Duplicate sends
• Simultaneous messages
• Delayed delivery
• Reconnect during send

────────────────────────────────────────

WEBSOCKET TESTING

Test:

• Authentication
• Authorization
• Room membership
• Heartbeats
• Subscribe
• Unsubscribe
• Reconnect
• Duplicate events
• Stale events
• Backpressure
• Connection drain

Load-test:

• Concurrent connections
• Connection churn
• Broadcast volume

────────────────────────────────────────

NOTIFICATION TESTING

Test:

• Device registration
• FCM
• APNS
• Token rotation
• Invalid tokens
• Push delivery
• In-app notification
• Deep links
• Deduplication
• Retry

────────────────────────────────────────

MODERATION TESTING

Test:

• Video moderation
• Comment moderation
• Message moderation
• Profile moderation
• Sound moderation
• Hashtag moderation
• Reports
• Case creation
• Human review
• Enforcement
• Appeals
• Restoration

Validate content visibility after every moderation action.

────────────────────────────────────────

RIGHTS TESTING

Test:

• Rights claim
• Regional restriction
• Expiration
• Takedown
• Appeal
• Restoration

Verify rights state propagates to:

• Playback
• Feed
• Search
• Recommendation
• Sounds

────────────────────────────────────────

ADVERTISING TESTING

Test:

• Advertiser organization
• Campaign
• Ad group
• Creative
• Placement
• Targeting
• Budget
• Scheduling
• Frequency cap
• Approval
• Impression
• Click
• Video completion

Concurrency:

• Budget reservation
• Frequency cap
• Campaign pause
• Creative rejection

────────────────────────────────────────

ANALYTICS TESTING

Test:

• Event validation
• Event versioning
• Event deduplication
• Kafka publishing
• Consumer processing
• Aggregation
• Retention
• Creator analytics
• Platform analytics
• Advertising analytics

Ensure analytics processing never blocks transactional flows.

────────────────────────────────────────

PRIVACY TESTING

Test:

• Data access
• Data export
• Data deletion
• Account deletion
• Retention
• Anonymization
• Behavioral-data controls
• Advertising preferences

Verify data is not leaked across:

• Users
• Creators
• Advertisers
• Administrators

────────────────────────────────────────

ADMINISTRATION TESTING

Test:

• Admin authentication
• RBAC
• Resource authorization
• User administration
• Creator administration
• Content moderation
• Rights management
• Advertising management
• Feature flags
• Configuration
• Audit

Test:

• Horizontal privilege escalation
• Vertical privilege escalation
• Cross-tenant access
• Sensitive-data access

────────────────────────────────────────

FEATURE-FLAG TESTING

Test:

• Global
• Region
• Platform
• User cohort
• Creator cohort
• Percentage rollout
• Canary
• Kill switch
• Rollback
• Expiration

Verify feature flags cannot override authorization.

────────────────────────────────────────

CONFIGURATION TESTING

Validate:

• Schema
• Type
• Required values
• Bounds
• Effective timestamps
• Rollback
• Versioning
• Approval

Reject invalid configurations before activation.

────────────────────────────────────────

AUDIT TESTING

Verify:

• Administrative actions audited
• Moderation actions audited
• Rights changes audited
• Configuration changes audited
• Feature changes audited
• Privacy actions audited

Audit records must be:

• Immutable
• Append-only
• Searchable
• Access-controlled

────────────────────────────────────────

WEB TESTING

CONSUMER

Test:

• Authentication
• Feed
• Video playback
• Search
• Profile
• Follow
• Like
• Comment
• Share
• Save
• Repost
• Messaging
• Notifications
• Reporting
• Privacy

CREATOR

Test:

• Creator profile
• Upload
• Resumable upload
• Drafts
• Metadata
• Captions
• Sounds
• Hashtags
• Mentions
• Publication
• Analytics

ADVERTISER

Test:

• Organization
• Campaign
• Creative
• Budget
• Analytics

ADMIN

Test:

• Login
• Search
• Moderation
• Rights
• Advertising
• Feature flags
• Configuration
• Audit
• Privacy

────────────────────────────────────────

WEB VIDEO TESTING

Validate:

• Autoplay
• Pause
• Mute
• Captions
• Poster
• Buffering
• HLS
• Playback authorization
• Token expiration
• CDN errors
• Deleted content

Ensure only the intended video actively consumes resources.

────────────────────────────────────────

MOBILE TESTING

CONSUMER

Test:

• Authentication
• Feed
• Video playback
• Search
• Profiles
• Engagement
• Messaging
• Notifications
• Sharing
• Privacy

CREATOR

Test:

• Camera
• Media picker
• Drafts
• Upload
• Resume
• Metadata
• Publication
• Analytics

────────────────────────────────────────

MOBILE MEDIA TESTING

Test:

• Camera permission
• Media permission
• Video selection
• Recording
• Pause/resume
• Encoding
• Upload
• Background/foreground
• Low-memory conditions

────────────────────────────────────────

MOBILE NETWORK TESTING

Simulate:

• Offline
• Weak network
• High latency
• Packet loss
• Reconnection
• Wi-Fi/cellular transition

Verify:

• No duplicate upload
• No duplicate publication
• Correct feed reconciliation
• Correct message reconciliation
• Safe retries

────────────────────────────────────────

MOBILE LIFECYCLE TESTING

Test:

• App launch
• Background
• Foreground
• Screen lock
• Notification open
• Deep link
• Termination
• OS process kill
• Reconnect

Verify state restoration from authoritative backend state.

────────────────────────────────────────

ACCESSIBILITY TESTING

WEB:

Target WCAG 2.2 AA.

Test:

• Keyboard navigation
• Focus management
• Screen readers
• Captions
• Forms
• Dialogs
• Tables
• Charts
• Reduced motion
• High contrast

MOBILE:

Test:

• VoiceOver
• TalkBack
• Dynamic Type
• Large text
• Labels
• Touch targets
• Captions
• Accessible actions

────────────────────────────────────────

SECURITY TESTING

Test:

• Authentication bypass
• Authorization bypass
• IDOR
• Privilege escalation
• SQL injection
• XSS
• CSRF where applicable
• SSRF where applicable
• Path traversal
• Malicious uploads
• Webhook spoofing
• Session hijacking
• Token replay
• Rate-limit bypass
• WebSocket abuse
• Media scraping
• CDN origin bypass
• Recommendation scraping
• Search scraping
• Admin escalation

────────────────────────────────────────

ABUSE TESTING

Test:

• Fake accounts
• Fake followers
• Fake likes
• Fake views
• Fake comments
• Fake shares
• Spam
• Bot activity
• Coordinated engagement
• Report abuse
• Promotion abuse
• Advertising fraud
• Upload abuse

Verify appropriate:

• Detection
• Throttling
• Restriction
• Review

────────────────────────────────────────

PERFORMANCE BUDGETS

Define budgets for:

• API latency
• Feed latency
• Recommendation latency
• Search latency
• Upload initialization
• Playback authorization
• WebSocket message latency
• Notification processing
• Media-processing latency

Do not define performance goals without measurable sources.

────────────────────────────────────────

LOAD TESTING

Simulate:

• Normal traffic
• Peak traffic
• Burst traffic
• Major-event traffic
• Creator upload bursts
• Recommendation spikes
• Search spikes
• Messaging spikes
• Notification spikes
• Moderation spikes

Measure:

• Throughput
• Latency
• Error rate
• Resource usage
• Queue growth
• Kafka lag
• Redis load
• Database load

────────────────────────────────────────

VIDEO LOAD TESTING

Test:

• Upload initialization
• Upload completion
• Processing queue
• Transcoding throughput
• Thumbnail throughput
• Packaging throughput
• Playback authorization

Do not transmit massive synthetic video through the wrong layer just to create artificial load.

Use representative test assets and direct-storage flows where appropriate.

────────────────────────────────────────

FEED LOAD TESTING

Simulate:

• Large concurrent users
• High request rates
• Cache misses
• Cache stampedes
• Recommendation dependency failures
• Trending fallback

Measure:

• Candidate latency
• Ranking latency
• Cache hit rate
• End-to-end latency

────────────────────────────────────────

SEARCH LOAD TESTING

Simulate:

• Prefix queries
• Full-text queries
• Trending queries
• Autocomplete
• Reindexing
• High concurrent searches

Measure:

• Search latency
• Indexing latency
• Cluster health
• Memory
• CPU
• Disk

────────────────────────────────────────

WEBSOCKET LOAD TESTING

Simulate:

• Large connection count
• Connection churn
• Message traffic
• Notification broadcasts
• Reconnect storms

Verify:

• Backpressure
• Connection limits
• Memory stability
• Graceful draining

────────────────────────────────────────

STRESS TESTING

Exceed expected capacity.

Identify:

• API saturation
• Feed saturation
• Recommendation saturation
• Search saturation
• PostgreSQL saturation
• Redis saturation
• Kafka saturation
• Media-worker saturation
• WebSocket limits

Document:

• Failure point
• Failure mode
• Recovery
• Scaling action

────────────────────────────────────────

SOAK TESTING

Run long-duration workloads.

Detect:

• Memory leaks
• Connection leaks
• Queue growth
• Kafka lag
• Redis growth
• Database degradation
• Worker degradation
• Search instability
• Log/storage growth

────────────────────────────────────────

RESILIENCE TESTING

Inject controlled failures into:

• PostgreSQL
• Redis
• Kafka
• BullMQ
• OpenSearch
• S3
• CloudFront/origin
• Media workers
• Feed workers
• Recommendation workers
• Search workers
• Notification workers
• Moderation workers
• WebSocket gateways

Verify:

• Timeout
• Retry
• Fallback
• Degraded mode
• Recovery
• Reconciliation

────────────────────────────────────────

CHAOS TESTING

Run controlled scenarios:

• Pod termination
• Node termination
• AZ failure
• Redis failover
• PostgreSQL failover
• Kafka broker failure
• Search node failure
• Media-worker failure
• Feed-worker failure
• Recommendation-worker failure
• WebSocket gateway failure
• Regional failure

Start in:

• Test
• Staging

Only run approved production scenarios under controlled operations.

────────────────────────────────────────

DISASTER RECOVERY TESTING

Validate:

• PostgreSQL restore
• PITR
• S3 restore
• OpenSearch restore
• Kafka recovery
• Redis recovery
• EKS reconstruction
• Terraform reconstruction
• Region failover
• Region failback

Measure:

• Actual RTO
• Actual RPO

Compare with approved objectives.

────────────────────────────────────────

BACKUP TESTING

A backup is valid only after successful restoration.

Test:

• Database
• S3
• Search snapshots
• Terraform state
• Critical configuration

Record:

• Test date
• Restore duration
• Result
• Data-integrity verification

────────────────────────────────────────

INFRASTRUCTURE TESTING

Validate:

• Terraform fmt
• Terraform validate
• Terraform plan
• Terraform policy
• Helm lint
• Kubernetes schema
• Kubernetes security
• Docker builds
• Container scans
• IAM policies
• Security groups
• NetworkPolicies
• WAF
• TLS
• Backup configuration
• Autoscaling

────────────────────────────────────────

CI/CD QUALITY GATES

PULL REQUEST:

• Format
• Lint
• Type-check
• Unit tests
• Integration tests
• Contract tests
• Security scanning
• Secret scanning
• Dependency scanning
• Docker validation
• Terraform validation
• Helm validation
• Kubernetes validation

RELEASE:

• Build
• Unit tests
• Integration tests
• Contracts
• E2E smoke tests
• Security scans
• Image scans
• Deployment validation
• Production smoke tests

────────────────────────────────────────

PRODUCTION SMOKE TESTING

After deployment safely validate:

• Authentication
• Public discovery
• Feed
• Search
• Video playback authorization
• Upload initialization
• Creator API
• Messaging
• Notifications
• Advertising API
• Administration
• Privacy APIs

Use:

• Synthetic accounts
• Synthetic content
• Non-destructive transactions

Do not create real financial charges or expose real user data.

────────────────────────────────────────

REGRESSION STRATEGY

Every production defect must lead to:

• Root-cause analysis
• Regression test
• Monitoring improvement where appropriate
• Documentation

Maintain a protected critical-path regression suite.

────────────────────────────────────────

FLAKY TEST MANAGEMENT

Track:

• Test name
• Failure frequency
• Environment
• Failure signature
• Owner
• Status

Do not permanently disable flaky tests without documented justification.

────────────────────────────────────────

QUALITY METRICS

Track:

• Unit-test coverage
• Integration coverage
• Contract coverage
• Critical-path E2E coverage
• Test pass rate
• Flaky-test rate
• Test duration
• Security findings
• Critical defects
• Performance regressions
• Recovery success
• Release failure rate

Do not treat code coverage as the sole quality metric.

────────────────────────────────────────

RELEASE CERTIFICATION

A release is production-ready only when:

• Required automated tests pass
• Critical-path E2E passes
• Security gates pass
• Privacy gates pass
• Performance budgets pass
• Contract compatibility passes
• Infrastructure validation passes
• Smoke tests pass
• Monitoring is operational
• Backup validation is current
• Rollback is available
• Known risks are documented
• Required approvals are complete

────────────────────────────────────────

PROJECT INDEX

Maintain the QA Project Index.

Track:

• Unit suites
• Integration suites
• Contract suites
• API tests
• WebSocket tests
• Event tests
• Queue tests
• Database tests
• Redis tests
• Search tests
• Video tests
• Upload tests
• Transcoding tests
• HLS tests
• Playback tests
• CDN tests
• Feed tests
• Recommendation tests
• Ranking tests
• Trending tests
• Social-graph tests
• Engagement tests
• Comment tests
• Messaging tests
• Notification tests
• Moderation tests
• Rights tests
• Advertising tests
• Creator analytics tests
• Platform analytics tests
• Privacy tests
• Administration tests
• Feature-flag tests
• Configuration tests
• Audit tests
• Web frontend tests
• Mobile tests
• Accessibility tests
• Security tests
• Abuse tests
• Performance tests
• Load tests
• Stress tests
• Soak tests
• Resilience tests
• Chaos tests
• Disaster-recovery tests
• Backup tests
• Infrastructure tests
• CI/CD gates
• Smoke tests
• Regression tests
• Release certification
• Coverage
• Flaky tests
• Known defects
• Known risks
• Generated files
• Remaining work
• Current milestone
• Production-readiness status

────────────────────────────────────────

IMPLEMENTATION MILESTONES

QA MILESTONE 11

Testing infrastructure, fixtures, factories, test databases, mocks, integration environments, reporting, and CI quality foundations.

QA MILESTONE 12

Identity, accounts, profiles, creators, creator verification, social graph, follows, blocks, sessions, and authorization.

QA MILESTONE 13

Video upload, media validation, processing, transcoding, thumbnails, captions, HLS packaging, playback authorization, CDN, and deletion.

QA MILESTONE 14

Likes, comments, shares, saves, collections, reposts, engagement counters, feed, pagination, and eligibility.

QA MILESTONE 15

Recommendations, ranking, re-ranking, exploration, trending, search, indexing, autocomplete, creator discovery, hashtags, and sounds.

QA MILESTONE 16

Messaging, WebSockets, notifications, blocking, reports, moderation, safety, rights, and appeals.

QA MILESTONE 17

Advertising, analytics, creator analytics, platform analytics, administration, feature flags, configuration, audit, and privacy.

QA MILESTONE 18

Web frontend unit/component/integration/E2E, accessibility, video playback, uploads, feed performance, search performance, and security.

QA MILESTONE 19

Mobile unit/component/integration/E2E, media/camera, upload resilience, background/foreground, deep links, accessibility, network resilience, battery, and performance.

QA MILESTONE 20

Full security testing, abuse testing, load/stress/soak testing, resilience, chaos, disaster recovery, backup restoration, infrastructure validation, production smoke testing, regression certification, release certification, documentation, and Project Index completion.

Each milestone should contain approximately 20–40 files where practical.

Every milestone must produce measurable and verifiable results.

────────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never truncate code.

Never summarize implementation instead of generating it.

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

This prompt is dedicated to:

• QA
• Testing
• Security validation
• Privacy validation
• Abuse validation
• Performance validation
• Scalability validation
• Resilience validation
• Accessibility validation
• Infrastructure validation
• Disaster-recovery validation
• Backup validation
• CI/CD quality gates
• Regression testing
• Production smoke testing
• Release certification
• Production-readiness validation

Do not redesign the approved architecture.

Do not implement unrelated product features.

────────────────────────────────────────

FINAL QUALITY BAR

The completed TikTok-like platform must provide objective evidence that it can operate as a production-grade global social-video service supporting:

• Hundreds of millions of users
• Millions of creators
• Millions of uploads per day
• Billions of video impressions
• Massive feed traffic
• Massive recommendation traffic
• Massive video-processing workloads
• Massive CDN delivery
• Large search traffic
• Massive messaging traffic
• Large moderation workloads
• Large advertising workloads
• Large analytics workloads
• Multiple regions
• High availability
• Disaster recovery
• Strict privacy
• Strict security
• Strict accessibility

The final QA program must demonstrate:

• Correctness
• Video/media integrity
• Feed integrity
• Recommendation safety
• Search correctness
• Security
• Privacy
• Performance
• Scalability
• Reliability
• Resilience
• Observability
• Recoverability
• Accessibility
• Maintainability
• Production readiness
