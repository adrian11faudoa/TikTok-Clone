You are operating in Senior Engineering Team Mode.

Build the production-ready backend for advertising, monetization foundations, creator analytics, platform analytics, administration, moderation administration, feature flags, dynamic configuration, audit, privacy workflows, data export, data deletion, fraud/abuse analytics, reconciliation, and final backend operational hardening for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The backend must follow the approved TikTok-like architecture, domain boundaries, database ownership, video architecture, media-processing architecture, feed architecture, recommendation architecture, search architecture, messaging architecture, moderation architecture, rights architecture, security model, event architecture, queue architecture, privacy model, and Project Index.

Do not redesign the architecture.

Do not generate frontend code.

Do not generate mobile code.

Do not generate infrastructure implementation code.

Do not generate Terraform.

Do not generate Kubernetes manifests.

Do not generate CI/CD workflows.

────────────────────────────────────────

MISSION

Complete the production-ready backend required for:

• Advertisers
• Advertising accounts
• Campaigns
• Ad groups
• Ad creatives
• Ad placements
• Ad eligibility
• Ad delivery references
• Budgets
• Scheduling
• Frequency caps
• Advertising events
• Impressions
• Clicks
• Video completions
• Conversion references
• Campaign analytics
• Creator monetization foundations
• Creator analytics
• Platform analytics
• Operational analytics
• Content analytics
• Recommendation analytics
• Search analytics
• Moderation analytics
• Safety analytics
• Fraud analytics
• Administration
• Administrative permissions
• Feature flags
• Experiment configuration
• System configuration
• Configuration versioning
• Audit
• Privacy requests
• Data export
• Data deletion/anonymization
• Retention policies
• Reconciliation
• Cross-domain integrity validation
• Final security hardening
• Final production backend validation

The implementation must support:

• Hundreds of millions of users
• Millions of creators
• Large advertiser populations
• Billions of impressions
• Massive analytics-event volume
• Multiple regions
• Multiple currencies
• Strict privacy requirements
• Strict advertising controls
• Strict administrative isolation
• High availability
• Horizontal scalability

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

Search:

• Elasticsearch/OpenSearch

Object storage:

• AWS S3

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
• Contract testing tools

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

Use idempotency for all retriable financial, advertising, privacy, configuration, and administrative operations.

Every administrative mutation must be auditable.

Every privacy mutation must be idempotent.

Analytics must never block transactional product operations.

────────────────────────────────────────

DOMAIN OWNERSHIP

Maintain explicit boundaries between:

• Advertising
• Campaign management
• Ad delivery references
• Ad analytics
• Creator analytics
• Platform analytics
• Administration
• Moderation administration
• Feature flags
• System configuration
• Audit
• Privacy
• Data retention
• Reconciliation

Do not combine:

• Advertising with core recommendation authority
• Analytics with transactional source-of-truth records
• Audit logs with normal application logs
• Feature flags with authorization
• Privacy workflows with arbitrary deletion logic
• Configuration with secrets

────────────────────────────────────────

ADVERTISING DOMAIN

Implement:

• Advertiser account
• Campaign
• Ad group
• Creative
• Placement
• Campaign budget
• Scheduling
• Targeting reference
• Frequency cap
• Campaign status
• Approval state

Campaign states:

• Draft
• Pending Review
• Approved
• Active
• Paused
• Exhausted
• Completed
• Rejected
• Archived

────────────────────────────────────────

ADVERTISER ACCOUNTS

Support:

• Advertiser profile
• Organization
• Billing reference
• Members
• Roles
• Permissions
• Campaign ownership

Roles may include:

• Owner
• Admin
• Campaign Manager
• Creative Manager
• Analyst
• Billing Manager

Organization isolation is mandatory.

────────────────────────────────────────

AD GROUPS

Support:

• Campaign association
• Creative association
• Budget reference
• Scheduling
• Audience configuration
• Placement configuration
• Frequency cap
• Status

Do not place all campaign logic in the ad-creative entity.

────────────────────────────────────────

AD CREATIVES

Support:

• Video creative
• Image creative
• Text
• Call-to-action
• Destination reference
• Creative version
• Moderation state
• Approval state

Validate:

• Media
• Text
• Destination
• Policy
• Region

────────────────────────────────────────

AD PLACEMENTS

Support configurable placements such as:

• Feed
• Search
• Discovery
• Creator/content contexts where approved

Do not hard-code all placements into campaign persistence.

────────────────────────────────────────

AD TARGETING

Support permitted targeting references such as:

• Region
• Language
• Broad audience segment
• Context
• Device category
• Content category

Do not use prohibited sensitive personal characteristics.

Do not expose internal targeting logic to consumers.

────────────────────────────────────────

AD FREQUENCY CAP

Support:

• User-level frequency
• Campaign-level frequency
• Creative-level frequency
• Time window

Use Redis or approved ephemeral state for low-latency enforcement.

Persistent campaign policy remains authoritative in PostgreSQL.

────────────────────────────────────────

AD BUDGETS

Support:

• Daily budget
• Campaign budget
• Remaining budget
• Spend reference
• Currency
• Scheduling

Protect against double-spending and race conditions where budget reservation is authoritative.

────────────────────────────────────────

AD ELIGIBILITY

Before serving an ad evaluate:

• Campaign status
• Creative approval
• Placement
• Region
• Schedule
• Budget
• Frequency
• Content-safety policy
• User privacy/consent controls
• Feature availability

Ads must not bypass content-safety policies.

────────────────────────────────────────

AD EVENTS

Track:

• AdEligible
• AdServed
• AdImpression
• AdClick
• AdVideoStarted
• AdVideoCompleted
• AdConversionReference
• AdRejected
• AdCampaignPaused
• AdCampaignCompleted

Events must be:

• Idempotent
• Versioned
• Privacy-aware
• Region-aware

────────────────────────────────────────

AD FRAUD

Detect:

• Automated impressions
• Click spam
• Suspicious completion patterns
• Repeated device behavior
• Coordinated activity
• Invalid conversion patterns

Do not treat every anomalous event as confirmed fraud.

Support:

• Monitoring
• Investigation
• Restriction
• Manual review

────────────────────────────────────────

CREATOR MONETIZATION FOUNDATION

Implement architecture for creator monetization references.

Support:

• Creator eligibility
• Monetization status
• Revenue attribution references
• Campaign/advertising associations
• Earnings analytics reference

Do not create a second financial ledger if a financial system is introduced later.

Keep financial ownership explicit and extensible.

────────────────────────────────────────

CREATOR ANALYTICS

Implement asynchronous creator analytics.

Metrics:

• Video views
• Unique viewers where approved
• Watch time
• Completion rate
• Average watch duration
• Rewatch rate
• Likes
• Comments
• Shares
• Saves
• Follower growth
• Traffic source
• Search discovery
• Sound usage
• Regional summaries
• Content performance

Do not expose raw sensitive behavioral data unnecessarily.

────────────────────────────────────────

CREATOR ANALYTICS ACCESS

Creators may access only:

• Their own content
• Their own aggregate performance
• Their authorized organization/team data

Do not expose:

• Internal recommendation scores
• Fraud signals
• Private user identities
• Sensitive user-level behavioral data

unless explicitly authorized.

────────────────────────────────────────

PLATFORM ANALYTICS

Support aggregate metrics for:

• DAU
• WAU
• MAU
• Sessions
• Watch time
• Completion
• Engagement
• Uploads
• Processing latency
• Feed latency
• Search activity
• Recommendation activity
• Moderation volume
• Rights actions
• Notification delivery
• Messaging
• Advertising

Analytics must be separated from transactional workloads.

────────────────────────────────────────

OPERATIONAL ANALYTICS

Support:

• API traffic
• Error rates
• Feed performance
• Search performance
• Processing backlog
• Queue health
• Moderation backlog
• Notification health
• WebSocket connections
• CDN references

Do not make analytics queries against hot transactional tables when a derived aggregate is more appropriate.

────────────────────────────────────────

ANALYTICS INGESTION

Implement:

Application Events
→ Kafka/Redpanda
→ Validation
→ Enrichment
→ Processing
→ Aggregation
→ Analytical Storage

All analytics processing must be asynchronous.

────────────────────────────────────────

ANALYTICS EVENT VALIDATION

Validate:

• Event type
• Version
• Producer
• Timestamp
• Region
• Entity reference
• Schema
• Privacy classification

Reject malformed analytics events.

────────────────────────────────────────

ANALYTICS RETENTION

Define retention for:

• Raw behavioral events
• Aggregated creator metrics
• Platform metrics
• Advertising events
• Moderation analytics
• Fraud analytics
• Safety analytics

Apply privacy and legal requirements.

────────────────────────────────────────

ADMINISTRATION

Implement backend administrative APIs for:

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

ADMIN ROLES

Support:

• Support Agent
• Moderator
• Safety Agent
• Rights Agent
• Fraud Analyst
• Finance Analyst
• Operations Manager
• Advertising Manager
• Analytics Analyst
• System Administrator
• Security Administrator
• Privacy Administrator
• Super Administrator

Do not grant broad permissions merely because someone has an administrator label.

────────────────────────────────────────

ADMIN PERMISSIONS

Separate:

• Read
• Create
• Update
• Suspend
• Remove
• Restore
• Refund reference where another financial service owns it
• Configuration change
• Feature-flag change
• Privacy access
• Audit access
• Security action

Resource access must remain scoped.

────────────────────────────────────────

SENSITIVE ADMIN ACTIONS

Require:

• Explicit permission
• Reason
• Confirmation
• Audit
• Additional approval where configured

Sensitive actions include:

• Content removal/restoration
• Creator suspension
• Rights changes
• Advertising approval
• Configuration changes
• Feature kill switches
• Privacy-data access
• Privacy deletion
• Security restrictions
• Account suspension

────────────────────────────────────────

MODERATION ADMINISTRATION

Provide administrative workflows for:

• Moderation queues
• Cases
• Appeals
• Reports
• Evidence
• Actions
• Policy versions
• Reinstatement

Only expose necessary sensitive content.

────────────────────────────────────────

FEATURE FLAGS

Implement backend feature flags.

Support:

• Boolean
• Percentage rollout
• Region
• Platform
• App version
• User cohort
• Creator cohort
• Advertiser
• Environment

Support:

• Canary
• Kill switch
• Rollback
• Expiration
• Audit

Feature flags never replace authorization.

────────────────────────────────────────

EXPERIMENTS

Support:

• Experiment
• Variant
• Assignment
• Eligibility
• Exposure
• Metrics reference
• Start/end dates

Experiments may target:

• Feed
• Recommendation
• Search
• Video-processing settings
• UI-supported backend behaviors
• Advertising

Do not expose experiment internals to ordinary users.

────────────────────────────────────────

SYSTEM CONFIGURATION

Support typed dynamic configuration for:

• Upload limits
• Video duration
• Processing profiles
• Feed limits
• Recommendation thresholds
• Search ranking
• Trending windows
• Notification limits
• Moderation thresholds
• Rights rules
• Ad frequency
• Ad budgets/limits
• Rate limits

Configuration must be:

• Typed
• Validated
• Versioned
• Audited
• Rollback-capable

────────────────────────────────────────

CONFIGURATION STATES

Support:

• Draft
• Pending Approval
• Approved
• Active
• Superseded
• Rolled Back

Configuration must never execute arbitrary code.

────────────────────────────────────────

AUDIT

Implement immutable audit records.

Audit:

• Administrative actions
• Moderation actions
• Rights actions
• Advertising approvals
• Feature-flag changes
• Configuration changes
• Privacy requests
• Data exports
• Data deletions
• Security actions
• Access to sensitive administrative resources

Store:

• Actor
• Role
• Action
• Resource type
• Resource ID
• Reason
• Request ID
• Correlation ID
• Region
• Timestamp
• Result

Never store secrets.

────────────────────────────────────────

AUDIT SEARCH

Support:

• Actor
• Action
• Resource
• Date
• Region
• Result
• Correlation ID

Audit records must be:

• Append-only
• Immutable
• Paginated
• Restricted

────────────────────────────────────────

PRIVACY

Implement privacy workflows for:

• Data access
• Data export
• Data deletion
• Account deletion
• Consent/preferences references
• Recommendation personalization controls
• Advertising personalization controls
• Retention

Classify:

• Identity
• Social graph
• Content
• Behavioral
• Analytics
• Messaging
• Moderation
• Rights
• Advertising
• Security
• Audit

────────────────────────────────────────

DATA EXPORT

Implement asynchronous export.

Support:

• Export request
• Scope
• Status
• Progress
• Artifact
• Expiration
• Authorization

Use BullMQ.

Store generated exports securely in S3.

Do not create publicly accessible downloads.

────────────────────────────────────────

DATA EXPORT SCOPE

Potential categories:

• Profile
• Social graph
• Videos
• Comments
• Collections
• Messages where legally/technically supported
• Notifications
• Settings
• Analytics available to the user
• Advertising preferences

Never export another user's data.

────────────────────────────────────────

DATA DELETION

Implement controlled deletion/anonymization.

Support:

• Request
• Validation
• Dependency analysis
• De-identification
• Deletion
• Verification
• Completion

Coordinate with:

• Identity
• Profiles
• Videos
• Comments
• Likes
• Follows
• Collections
• Messages
• Notifications
• Analytics
• Advertising
• Moderation
• Rights

────────────────────────────────────────

RETENTION EXCEPTIONS

Certain records may require:

• Retention
• Restricted archival
• Pseudonymization

for:

• Legal
• Financial
• Safety
• Security
• Fraud
• Audit

requirements.

Do not indiscriminately destroy retained records.

────────────────────────────────────────

PRIVACY RECONCILIATION

After deletion/export processing verify:

• User data
• Profile data
• Social relationships
• Content metadata
• Derived analytics references
• Search index references
• Recommendation references
• Advertising references
• Support/moderation references

Derived systems may converge asynchronously but must follow deletion policy.

────────────────────────────────────────

CROSS-DOMAIN RECONCILIATION

Implement reconciliation for:

IDENTITY

• User/profile consistency

SOCIAL GRAPH

• Follow/block consistency
• Aggregate counts

CONTENT

• Video state
• Asset state
• Search state
• CDN/object references

DISCOVERY

• Feed eligibility
• Recommendation eligibility
• Search eligibility
• Trending eligibility

MESSAGING

• Conversation/message consistency

NOTIFICATIONS

• Delivery state consistency

MODERATION

• Case/action consistency

RIGHTS

• Rights restrictions vs playback/search/discovery

ADVERTISING

• Campaign/creative/placement consistency

ANALYTICS

• Event processing lag
• Aggregate freshness

────────────────────────────────────────

SEARCH RECONCILIATION

Detect:

• Deleted content still indexed
• Restricted content still indexed
• Missing published content
• Stale creator metadata
• Stale hashtags
• Stale sounds

Support:

• Incremental repair
• Full rebuild

Never modify authoritative source data from search reconciliation.

────────────────────────────────────────

FEED RECONCILIATION

Detect:

• Deleted videos in candidate stores
• Blocked creators still appearing
• Restricted content
• Stale candidates
• Missing visibility changes

Use asynchronous repair.

────────────────────────────────────────

RECOMMENDATION RECONCILIATION

Detect stale recommendation state after:

• Block
• Unfollow
• Content deletion
• Moderation
• Rights expiration
• Privacy changes

Recommendation systems must have a way to invalidate stale features/candidates.

────────────────────────────────────────

ADVERTISING RECONCILIATION

Detect:

• Campaign budget mismatch
• Invalid creative state
• Expired campaign still active
• Frequency-cap inconsistency
• Impression-event duplication

Support:

• Detection
• Safe correction
• Audit

────────────────────────────────────────

CROSS-DOMAIN HEALTH

Provide operational health checks for:

• PostgreSQL
• Redis
• Kafka
• BullMQ
• OpenSearch
• S3
• External providers
• Analytics processing
• Recommendation processing
• Search indexing
• Moderation queues
• Notification queues

Differentiate:

• Liveness
• Readiness
• Dependency health
• Functional health

────────────────────────────────────────

SECURITY HARDENING

Perform a final backend security review for:

AUTHENTICATION

• Credential storage
• Sessions
• Token handling
• Device security

AUTHORIZATION

• User
• Creator
• Advertiser
• Organization
• Admin
• Privacy administrator

API

• Validation
• Rate limiting
• Request limits
• Error handling
• Timeouts

MEDIA

• Upload security
• Signed access
• Object isolation

SEARCH

• Query injection
• Scraping
• Private-content leakage

ADMIN

• Privilege escalation
• Cross-organization access
• Sensitive-data access

PRIVACY

• Export leakage
• Deletion leakage
• Behavioral-data exposure

────────────────────────────────────────

PERFORMANCE REVIEW

Audit:

• N+1 queries
• Hot Redis keys
• Hot Kafka partitions
• Long transactions
• Excessive synchronous dependencies
• Expensive analytics queries
• Large admin queries
• Unbounded report generation
• High-cardinality metrics
• Search overload

Optimize:

• Pagination
• Caching
• Aggregations
• Batch jobs
• Asynchronous processing

────────────────────────────────────────

DATABASE REVIEW

Validate:

• Index coverage
• Foreign keys
• Constraints
• Transactions
• Partitioning
• Retention
• Migration safety
• Connection pooling
• Read replicas where required

Identify:

• Lock contention
• Deadlocks
• Sequential scans
• Connection exhaustion

────────────────────────────────────────

REDIS REVIEW

Validate:

• Namespaces
• TTL
• Eviction policy
• Hot keys
• Memory pressure
• Failure behavior

Redis must never be authoritative for:

• Users
• Videos
• Rights
• Moderation
• Financial data
• Privacy records

────────────────────────────────────────

KAFKA REVIEW

Validate:

• Topic ownership
• Partitioning
• Retention
• Consumer groups
• Lag
• Replay
• Dead-letter topics

Detect hot partitions.

────────────────────────────────────────

QUEUE REVIEW

Validate all BullMQ queues for:

• Retry
• Backoff
• Timeout
• Concurrency
• Dead-letter behavior
• Poison-job handling
• Scaling
• Monitoring

No queue may retry indefinitely.

────────────────────────────────────────

OBSERVABILITY

Instrument:

• Advertising
• Analytics
• Administration
• Moderation
• Rights
• Privacy
• Export
• Deletion
• Reconciliation
• Feature flags
• Configuration

Track:

• Ad request latency
• Impression processing
• Analytics lag
• Report generation
• Admin API latency
• Privacy workflow latency
• Reconciliation mismatches
• Queue depth
• Kafka lag

Never log:

• User passwords
• Access tokens
• Private messages
• Sensitive behavioral profiles
• Privacy-export contents
• Security secrets
• Internal risk data unnecessarily

────────────────────────────────────────

SLO / SLI

Define SLOs for:

• Advertising eligibility
• Analytics ingestion
• Report generation
• Admin APIs
• Feature-flag propagation
• Configuration propagation
• Privacy export
• Privacy deletion
• Reconciliation

For each define:

• SLI
• Measurement source
• Target
• Error budget
• Alert threshold

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Ad eligibility
• Budget rules
• Frequency caps
• Campaign states
• Creator analytics aggregation
• Feature flags
• Configuration validation
• Privacy workflow
• Reconciliation rules

INTEGRATION TESTS

Test:

• PostgreSQL
• Redis
• Kafka
• BullMQ
• OpenSearch
• S3

ADVERTISING TESTS

Test:

• Campaign lifecycle
• Creative approval
• Budget limits
• Frequency cap
• Regional targeting
• Privacy controls
• Fraud signals

ANALYTICS TESTS

Test:

• Event validation
• Deduplication
• Aggregation
• Retention
• Report generation

ADMIN TESTS

Test:

• RBAC
• Sensitive actions
• Audit
• Organization isolation

PRIVACY TESTS

Test:

• Export
• Deletion
• Anonymization
• Retention exceptions
• Cross-domain cleanup

RECONCILIATION TESTS

Test:

• Stale search
• Stale feed candidates
• Stale recommendations
• Rights inconsistencies
• Ad-state inconsistencies
• Analytics lag

SECURITY TESTS

Test:

• Admin escalation
• Cross-advertiser access
• Cross-organization access
• Privacy leakage
• Configuration abuse
• Feature-flag abuse

PERFORMANCE TESTS

Test:

• Analytics ingestion
• Ad eligibility
• Admin search
• Report generation
• Privacy export
• Reconciliation workload

────────────────────────────────────────

DOCUMENTATION

Generate:

• Advertising architecture
• Advertiser accounts
• Campaign architecture
• Ad group architecture
• Creative architecture
• Placement architecture
• Targeting
• Frequency caps
• Budgeting
• Advertising events
• Ad fraud
• Creator monetization foundation
• Creator analytics
• Platform analytics
• Analytics ingestion
• Administration
• Admin permissions
• Moderation administration
• Feature flags
• Experimentation
• Dynamic configuration
• Audit
• Privacy architecture
• Data export
• Data deletion
• Retention
• Reconciliation
• Security hardening
• Performance review
• Database review
• Redis review
• Kafka review
• Queue review
• Observability
• SLO/SLI
• Testing
• Production-readiness validation

────────────────────────────────────────

PROJECT INDEX

Update the backend Project Index with:

• Advertising
• Advertisers
• Campaigns
• Ad groups
• Creatives
• Placements
• Targeting references
• Frequency caps
• Budgets
• Advertising events
• Creator monetization
• Creator analytics
• Platform analytics
• Operational analytics
• Analytics ingestion
• Reports
• Administration
• Admin roles
• Admin permissions
• Moderation administration
• Feature flags
• Experiments
• System configuration
• Audit
• Privacy requests
• Data export
• Data deletion
• Retention
• Reconciliation
• Search reconciliation
• Feed reconciliation
• Recommendation reconciliation
• Advertising reconciliation
• Security hardening
• Performance review
• Database review
• Redis review
• Kafka review
• Queue review
• Observability
• SLO/SLI
• Tests
• Generated files
• Modified files
• Remaining work
• Known risks
• Technical debt
• Current milestone
• Production-readiness status
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

BACKEND MILESTONE 51

Advertiser accounts, organizations, advertiser roles, permissions, campaign lifecycle, ad groups, and creative management.

BACKEND MILESTONE 52

Ad placements, eligibility, targeting references, frequency caps, budgets, scheduling, and advertising-policy integration.

BACKEND MILESTONE 53

Advertising events, impression/click/completion processing, campaign analytics, ad-fraud signals, and reconciliation.

BACKEND MILESTONE 54

Creator analytics, creator performance aggregates, analytics access control, and report generation.

BACKEND MILESTONE 55

Platform and operational analytics ingestion, validation, aggregation, retention, and analytics reporting.

BACKEND MILESTONE 56

Administration APIs, roles, permissions, sensitive administrative actions, moderation administration, and audit.

BACKEND MILESTONE 57

Feature flags, experiments, rollout evaluation, dynamic system configuration, approvals, activation, and rollback.

BACKEND MILESTONE 58

Privacy requests, data export, secure export artifacts, data deletion/anonymization, retention exceptions, and privacy reconciliation.

BACKEND MILESTONE 59

Cross-domain reconciliation, search/feed/recommendation reconciliation, advertising reconciliation, health diagnostics, security hardening, and performance review.

BACKEND MILESTONE 60

Final integration, security, privacy, concurrency, analytics, advertising, administration, resilience, disaster-recovery validation, production smoke testing, documentation, and Project Index completion.

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

• Advertising
• Advertisers
• Campaigns
• Ad groups
• Creatives
• Placements
• Targeting references
• Frequency caps
• Budgets
• Advertising events
• Ad analytics
• Ad fraud foundations
• Creator analytics
• Platform analytics
• Operational analytics
• Reporting
• Administration
• Admin permissions
• Moderation administration
• Feature flags
• Experiments
• Dynamic configuration
• Audit
• Privacy
• Data export
• Data deletion/anonymization
• Retention
• Reconciliation
• Security hardening
• Performance review
• Operational diagnostics
• Final backend integration

Do not redesign or reimplement previously completed:

• Identity
• Profiles
• Creators
• Social graph
• Videos
• Uploads
• Media processing
• Playback
• Engagement
• Feed
• Recommendation
• Trending
• Search
• Messaging
• Notifications
• Moderation
• Rights

Use their established APIs, events, repositories, and ownership boundaries.

Do not implement:

• Web frontend
• Mobile frontend
• Infrastructure
• Terraform
• Kubernetes
• CI/CD

────────────────────────────────────────

QUALITY BAR

Treat advertising, analytics, administration, privacy, audit, and configuration as enterprise-critical systems.

Assume:

• Hundreds of millions of users
• Millions of creators
• Large advertiser organizations
• Billions of impressions
• Massive analytics streams
• Large administration workloads
• Multiple regions
• Strict privacy requirements
• Strict security requirements
• Strict organization isolation
• High availability
• Disaster recovery

Prioritize:

• Privacy
• Security
• Organization isolation
• Auditability
• Data integrity
• Analytics correctness
• Advertising integrity
• Reconciliation
• Idempotency
• Scalability
• Observability
• Maintainability
• Production readiness
