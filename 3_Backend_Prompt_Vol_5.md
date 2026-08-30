You are operating in Senior Engineering Team Mode.

Build the production-ready backend for direct messaging, notifications, moderation, reporting, content safety, copyright/rights management, creator safety, user blocking, abuse prevention, and platform trust systems for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The backend must follow the approved TikTok-like architecture, domain boundaries, video architecture, social graph, engagement, feed, recommendation, search, storage, security, event, queue, privacy, and Project Index architecture.

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

• Direct messaging
• Conversations
• Message delivery
• Read state
• Attachments
• Message moderation
• User blocking
• Messaging permissions
• Notifications
• Notification preferences
• Push notifications
• In-app notifications
• Email notifications where approved
• Content reporting
• User reporting
• Video reporting
• Comment reporting
• Message reporting
• Hashtag reporting
• Sound reporting
• Moderation cases
• Content safety
• Automated moderation orchestration
• Human moderation
• Appeals
• Enforcement
• Copyright claims
• Rights restrictions
• Takedowns
• Rights appeals
• Safety workflows
• Abuse prevention
• Spam protection
• Account abuse controls
• Engagement abuse controls

The implementation must support:

• Hundreds of millions of users
• Millions of creators
• Billions of interactions
• Massive messaging throughput
• Massive notification throughput
• Large moderation queues
• Large report volumes
• Multiple regions
• Strict privacy
• Strict access control
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

Object storage:

• AWS S3

Real-time:

• WebSockets
• Socket.IO

Notifications:

• Firebase Cloud Messaging
• Apple Push Notification Service
• Email provider abstraction
• SMS provider abstraction where approved

Search:

• Existing OpenSearch/Elasticsearch abstraction

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

Use idempotency for retriable operations.

Use authorization at every sensitive resource boundary.

Never expose internal moderation, risk, or rights information unnecessarily.

────────────────────────────────────────

DOMAIN OWNERSHIP

Maintain explicit boundaries between:

• Messaging
• Notifications
• Blocking
• Reporting
• Moderation
• Content safety
• Copyright/rights
• Appeals
• Abuse prevention

Do not combine:

• Message storage with notification delivery
• Public reports with private safety evidence
• Moderation policy with final content ownership
• Rights metadata with ordinary video metadata
• Block state with permanent recommendation state

────────────────────────────────────────

MESSAGING

Implement direct messaging.

Support:

• One-to-one conversations
• Group conversations only where product requirements justify them
• Conversation participants
• Messages
• Message delivery
• Read receipts
• Attachments
• Message deletion
• Message expiration where applicable
• Blocking
• Reporting
• Moderation

────────────────────────────────────────

CONVERSATION AUTHORIZATION

A user may access a conversation only when:

• They are an authorized participant
• The conversation is active
• Account restrictions permit access

Blocked users must not be able to continue unauthorized messaging.

────────────────────────────────────────

MESSAGE STATE

Support:

• Created
• Queued
• Delivered
• Read
• Failed
• Deleted
• Moderation Pending
• Restricted
• Expired

Server timestamps are authoritative.

────────────────────────────────────────

MESSAGE IDEMPOTENCY

Every message creation request should support:

• Client mutation ID
• Idempotency key
• Deterministic replay behavior

Prevent duplicate messages after:

• Retry
• Timeout
• Reconnect
• App restart

────────────────────────────────────────

MESSAGE ORDERING

Support:

• Server sequence
• Created timestamp
• Conversation ordering reference

Handle:

• Concurrent messages
• Reconnect
• Delayed delivery
• Duplicate delivery

Do not depend exclusively on client clocks.

────────────────────────────────────────

MESSAGE DELIVERY

Persist the authoritative message before or in a transactional workflow with delivery orchestration.

Support:

• WebSocket delivery
• Offline persistence
• Push fallback
• Delivery acknowledgment
• Read acknowledgment

A temporary real-time outage must not permanently lose an accepted message.

────────────────────────────────────────

REAL-TIME MESSAGING

Implement WebSocket/Socket.IO events:

• conversation.created
• message.created
• message.delivered
• message.read
• message.deleted
• message.restricted

Support:

• Authentication
• Authorization
• Conversation rooms
• Reconnection
• Heartbeats
• Duplicate suppression
• Backpressure
• Connection limits

────────────────────────────────────────

MESSAGE RATE LIMITING

Protect against:

• Spam
• Flooding
• Bot abuse
• Malicious automation

Define limits for:

• Messages/user
• Messages/conversation
• Attachments
• New-conversation creation
• Rapid recipient changes

Use Redis rate limiting.

────────────────────────────────────────

MESSAGE ATTACHMENTS

Where supported:

• Upload authorization
• File type validation
• Size limits
• Malware scanning
• Object storage
• Secure download authorization
• Expiration where appropriate

Never trust client MIME type alone.

────────────────────────────────────────

NOTIFICATION DOMAIN

Implement:

• Notification
• Notification type
• Recipient
• Source entity
• Delivery state
• Read state
• Preferences
• Channel
• Priority
• Expiration

Channels:

• Push
• In-app
• Email
• SMS where approved

────────────────────────────────────────

NOTIFICATION TYPES

Support:

• Follow
• Unfollow confirmation where applicable
• Like
• Comment
• Reply
• Mention
• Share
• Save-related notifications where appropriate
• Message
• Creator update
• Moderation action
• Copyright action
• Security
• Account
• System

────────────────────────────────────────

NOTIFICATION PREFERENCES

Support preferences for:

• Social interactions
• Messages
• Creator updates
• Recommendations
• Promotions
• Marketing
• Security
• Moderation
• Rights
• System

Security-critical notifications must remain enabled when required.

────────────────────────────────────────

NOTIFICATION DEDUPLICATION

Prevent duplicate notifications caused by:

• Kafka retries
• Queue retries
• Webhook retries
• Worker restarts

Use:

• Event ID
• Notification ID
• Idempotency keys

────────────────────────────────────────

PUSH NOTIFICATIONS

Implement:

• Device token registration
• FCM
• APNS
• Token rotation
• Invalid token cleanup
• Notification categories
• Deep links
• Retry
• Backoff

────────────────────────────────────────

NOTIFICATION QUEUES

Use BullMQ queues for:

• Push
• Email
• SMS
• Retry
• Scheduled notifications
• Cleanup

Every job must support:

• Idempotency
• Timeout
• Retry
• Backoff
• Dead-letter handling
• Metrics
• Structured logging

────────────────────────────────────────

REPORTING

Implement user reports for:

• Video
• Creator
• Profile
• Comment
• Message
• Sound
• Hashtag

Report fields:

• Reporter
• Target
• Category
• Reason
• Description
• Evidence reference
• Region
• Status
• Created time

────────────────────────────────────────

REPORT STATES

Support:

• Submitted
• Queued
• Assigned
• Investigating
• Action Taken
• Dismissed
• Appealed
• Resolved
• Closed

────────────────────────────────────────

REPORT ABUSE

Prevent:

• Duplicate reports
• Report flooding
• Coordinated false-report attacks
• Unauthorized report access

Use:

• Rate limits
• Deduplication
• Risk signals
• Case aggregation

Do not automatically punish content solely because a threshold number of reports was reached.

────────────────────────────────────────

MODERATION CASES

Implement:

• Case
• Target content
• Policy
• Evidence
• Decision
• Moderator
• Automation result
• Appeal
• Resolution

Targets:

• Video
• Comment
• Message
• Profile
• Sound
• Hashtag
• Creator

────────────────────────────────────────

MODERATION STATES

Support:

• Pending
• Under Review
• Approved
• Restricted
• Removed
• Reinstated
• Appealed
• Closed

────────────────────────────────────────

MODERATION ACTIONS

Support configurable actions:

• No action
• Warning
• Visibility restriction
• Recommendation restriction
• Search restriction
• Comment restriction
• Messaging restriction
• Temporary suspension
• Permanent removal
• Account restriction

Do not hard-code policy into controller logic.

────────────────────────────────────────

CONTENT-SAFETY ORCHESTRATION

Architecture:

Content
→ Detection
→ Classification
→ Policy
→ Decision
→ Enforcement
→ Appeal

Support automated providers such as:

• Text classification
• Image/video classification
• Audio classification
• Spam detection

All automated decisions must support human review when policy requires it.

────────────────────────────────────────

MODERATION PROVIDER ABSTRACTION

Create provider-neutral interfaces for:

• Text moderation
• Image moderation
• Video moderation
• Audio moderation
• Spam detection
• Safety classification

Normalize provider results.

Do not let provider-specific classifications become core domain contracts.

────────────────────────────────────────

VIDEO MODERATION

Support:

• Pre-publication moderation
• Post-publication moderation
• Reprocessing
• Escalation
• Removal
• Restoration

Moderation state must affect:

• Feed
• Recommendations
• Search
• Playback
• Comments
• Shares

────────────────────────────────────────

COMMENT MODERATION

Support:

• Automated filtering
• Human review
• Spam suppression
• Comment removal
• Creator controls where approved

Moderated comments should stop appearing in eligible public contexts.

────────────────────────────────────────

MESSAGE MODERATION

Messages require special privacy handling.

Support:

• User reports
• Automated detection where legally and technically appropriate
• Restricted-message state
• Investigation
• Appeal

Do not perform unrestricted background inspection of private messages without an approved policy and legal basis.

────────────────────────────────────────

CONTENT SAFETY

Define policy categories including:

• Harassment
• Hate
• Violence
• Sexual content
• Dangerous activity
• Self-harm
• Illegal content
• Spam
• Fraud
• Child-safety protections
• Copyright violations

Create policy-version references for moderation decisions.

────────────────────────────────────────

APPEALS

Support appeals for:

• Content removal
• Visibility restriction
• Account restriction
• Messaging restriction
• Creator suspension
• Rights takedown

Appeal states:

• Submitted
• Under Review
• Upheld
• Overturned
• Closed

────────────────────────────────────────

COPYRIGHT / RIGHTS DOMAIN

Implement:

• Rights reference
• Claim
• Takedown
• Restriction
• Appeal
• Restoration
• Rights expiration

Targets:

• Video
• Sound
• Audio asset
• Regional content

────────────────────────────────────────

RIGHTS CLAIM

Track:

• Claimant reference
• Content reference
• Rights type
• Region
• Effective dates
• Evidence reference
• Status

Do not store unnecessary proprietary claimant data.

────────────────────────────────────────

RIGHTS STATES

Support:

• Active
• Pending
• Restricted
• Removed
• Expired
• Appealed
• Restored

────────────────────────────────────────

RIGHTS ENFORCEMENT

Rights changes may affect:

• Playback
• Feed
• Recommendations
• Search
• Sound usage
• Monetization

Enforcement must propagate through derived systems.

────────────────────────────────────────

ABUSE PREVENTION

Protect against:

• Fake accounts
• Spam accounts
• Bot messaging
• Comment spam
• Follow spam
• Fake reports
• Coordinated abuse
• Content manipulation
• Recommendation manipulation
• Search manipulation
• Notification abuse

Use:

• Rate limits
• Device signals
• Behavioral signals
• Risk signals
• Graph signals
• Human review

────────────────────────────────────────

BLOCKING

Support:

• User block
• Unblock
• Block list
• Block propagation

A block must affect where appropriate:

• Messaging
• Comments
• Mentions
• Notifications
• Follow
• Feed
• Recommendations
• Search/discovery

Do not rely only on the client.

────────────────────────────────────────

BLOCK PROPAGATION

Publish block events.

Consumers include:

• Messaging
• Notifications
• Feed
• Recommendations
• Search
• Social graph

Block enforcement must happen at the appropriate authoritative boundary even if derived systems have not caught up.

────────────────────────────────────────

SAFETY WORKFLOWS

Support:

• Safety-related reports
• Escalation
• High-severity handling
• Evidence
• Moderator assignment
• Resolution

High-severity cases should support accelerated processing.

────────────────────────────────────────

SAFETY EVIDENCE

Evidence may reference:

• Video
• Image
• Message
• Screenshot
• Metadata
• Event history

Store sensitive evidence securely.

Use:

• Encryption
• Access control
• Audit
• Retention policy

────────────────────────────────────────

DATABASE

Implement Prisma models and migrations for:

• Conversation
• ConversationParticipant
• Message
• MessageDelivery
• MessageAttachment
• Notification
• NotificationPreference
• NotificationDelivery
• PushToken
• Report
• ModerationCase
• ModerationAction
• ModerationEvidenceReference
• ModerationPolicyVersion
• Appeal
• SafetyCase
• RightsReference
• RightsClaim
• RightsRestriction
• RightsAppeal
• UserBlock

Use:

• Primary keys
• Foreign keys
• Unique constraints
• Composite indexes
• Status
• Version
• Created/updated timestamps
• Expiration

Partition high-growth data where appropriate.

────────────────────────────────────────

DATABASE INDEXES

Create indexes for:

MESSAGING

• Conversation participant
• Conversation updated time
• Message conversation/created time
• Message sender/created time
• Delivery message/recipient

NOTIFICATIONS

• Recipient/created
• Recipient/unread
• Delivery state

REPORTING

• Target
• Reporter
• Status
• Created time

MODERATION

• Case status
• Target
• Assignee
• Created time

RIGHTS

• Content
• Region
• Status

BLOCKS

• Blocker/blocked
• Blocked/blocker

────────────────────────────────────────

REDIS

Use Redis for:

• Message rate limiting
• Notification deduplication
• WebSocket coordination
• Short-lived conversation presence
• Block-state caching where appropriate
• Moderation queue coordination
• Case-rate limiting

Redis must never be the source of truth for:

• Messages
• Notifications
• Reports
• Moderation cases
• Rights claims
• Blocks

────────────────────────────────────────

KAFKA EVENTS

Publish:

MESSAGING

• ConversationCreated
• MessageCreated
• MessageDelivered
• MessageRead
• MessageDeleted
• MessageRestricted

NOTIFICATIONS

• NotificationCreated
• NotificationDelivered
• NotificationFailed

BLOCKING

• UserBlocked
• UserUnblocked

REPORTING

• ReportCreated
• ReportUpdated
• ReportResolved

MODERATION

• ModerationCaseCreated
• ModerationActionTaken
• ModerationCaseResolved
• AppealCreated
• AppealResolved

RIGHTS

• RightsClaimCreated
• RightsRestrictionApplied
• RightsExpired
• RightsAppealCreated
• RightsRestored

SAFETY

• SafetyCaseCreated
• SafetyCaseEscalated
• SafetyCaseResolved

Events must be:

• Versioned
• Idempotent
• Minimal
• Privacy-aware

────────────────────────────────────────

BACKGROUND JOBS

Implement BullMQ queues for:

• Notification delivery
• Message cleanup
• Attachment cleanup
• Report aggregation
• Moderation processing
• Appeal processing
• Rights-processing workflows
• Expired-rights cleanup
• Block propagation
• Safety escalation
• Notification cleanup
• Data-retention cleanup

Every job must support:

• Retry
• Backoff
• Timeout
• Idempotency
• Dead-letter handling
• Metrics
• Structured logging

────────────────────────────────────────

API

MESSAGING

• Create conversation
• Get conversation
• List conversations
• List messages
• Send message
• Delete message
• Mark delivered
• Mark read
• Upload attachment authorization
• Report message

NOTIFICATIONS

• List notifications
• Mark read
• Mark all read
• Get preferences
• Update preferences
• Register device
• Remove device

REPORTING

• Create report
• Get report status
• List own reports where allowed

BLOCKING

• Block
• Unblock
• List blocked users

MODERATION

• Internal case APIs
• Assign case
• Review case
• Take action
• Appeal
• Resolve

RIGHTS

• Create claim
• Get claim
• Apply restriction
• Process appeal
• Restore

SAFETY

• Create safety case
• Get case
• Escalate
• Resolve

Every endpoint must implement:

• Authentication
• Authorization
• Validation
• Rate limiting
• Idempotency where appropriate
• OpenAPI
• Consistent errors
• Privacy rules
• Audit where required

────────────────────────────────────────

REAL-TIME API

WebSocket/Socket.IO events:

• message.created
• message.delivered
• message.read
• notification.created
• moderation.status
• rights.status
• safety.status where authorized

Every subscription must verify authorization.

────────────────────────────────────────

SECURITY

Protect against:

• Message interception
• Unauthorized conversation access
• Message scraping
• Notification abuse
• Report abuse
• Moderation-data leakage
• Rights-data leakage
• Safety-data leakage
• Block bypass
• Cross-user access
• Admin privilege escalation

Use:

• Authentication
• Authorization
• Resource ownership
• RBAC
• Rate limits
• Secure tokens
• Audit
• Least privilege

────────────────────────────────────────

PRIVACY

Protect:

• Private messages
• Safety reports
• Moderation evidence
• Rights claims
• User reports
• Block lists
• Notification preferences

Do not expose internal:

• Moderation reasoning
• Risk signals
• Safety evidence
• Provider-specific sensitive output

without explicit authorization.

────────────────────────────────────────

OBSERVABILITY

Instrument:

• Conversation creation
• Message send
• Message delivery
• Notification creation
• Notification delivery
• Reports
• Moderation
• Appeals
• Rights claims
• Safety cases
• Block propagation

Track:

• Message latency
• Delivery success
• Notification success
• Moderation backlog
• Report backlog
• Appeal processing latency
• Rights-processing latency
• Safety escalation latency
• Queue depth
• WebSocket connections

Never log:

• Private message bodies
• Sensitive safety evidence
• Internal moderation details
• Rights credentials
• Device secrets

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Conversation authorization
• Message states
• Message ordering
• Notification routing
• Notification preferences
• Block rules
• Report validation
• Moderation states
• Appeal states
• Rights states
• Safety states

MESSAGING TESTS

Test:

• Send
• Retry
• Duplicate message
• Delivery
• Read
• Reconnect
• Ordering
• Authorization
• Rate limiting

NOTIFICATION TESTS

Test:

• FCM
• APNS
• Token rotation
• Invalid token
• Deduplication
• Retry
• Deep link generation

REPORTING TESTS

Test:

• Duplicate report
• Report flooding
• Unauthorized report access
• Case creation
• Case aggregation

MODERATION TESTS

Test:

• Automated result
• Human review
• Enforcement
• Appeal
• Restoration
• Version changes

RIGHTS TESTS

Test:

• Claim
• Restriction
• Expiration
• Appeal
• Restoration
• Regional behavior

BLOCK TESTS

Test:

• Blocking
• Unblocking
• Messaging prevention
• Mention prevention
• Notification prevention
• Feed/recommendation propagation

SECURITY TESTS

Test:

• Conversation IDOR
• Cross-user messages
• Cross-case access
• Safety-data access
• Rights-data access
• Admin escalation

PERFORMANCE TESTS

Test:

• Messaging throughput
• Notification throughput
• Report ingestion
• Moderation queue throughput
• WebSocket concurrency

────────────────────────────────────────

DOCUMENTATION

Generate:

• Messaging architecture
• Conversation authorization
• Message lifecycle
• Message ordering
• Message delivery
• Attachment security
• WebSocket messaging
• Notification architecture
• Notification preferences
• Push delivery
• Reporting architecture
• Moderation architecture
• Content safety
• Automated moderation
• Human review
• Appeals
• Copyright/rights architecture
• Rights enforcement
• Safety workflows
• Blocking
• Abuse prevention
• API contracts
• WebSocket contracts
• Event catalog
• Queue catalog
• Database schema
• Redis key catalog
• Security
• Privacy
• Testing

────────────────────────────────────────

PROJECT INDEX

Update the backend Project Index with:

• Messaging services
• Conversations
• Participants
• Messages
• Message delivery
• Attachments
• Notifications
• Notification preferences
• Notification delivery
• Push tokens
• Reports
• Moderation cases
• Moderation actions
• Appeals
• Safety cases
• Rights references
• Rights claims
• Rights restrictions
• Rights appeals
• Blocks
• APIs
• WebSocket events
• Kafka topics
• BullMQ queues
• Redis keys
• Database migrations
• Tests
• Security
• Privacy
• Observability
• Generated files
• Remaining work
• Current milestone
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

BACKEND MILESTONE 41

Messaging, conversations, participants, message lifecycle, authorization, persistence, and APIs.

BACKEND MILESTONE 42

Real-time messaging, WebSockets, delivery receipts, read state, reconnection, ordering, rate limits, and attachments.

BACKEND MILESTONE 43

Notifications, notification preferences, device tokens, push providers, email/SMS abstraction, queues, retries, and deduplication.

BACKEND MILESTONE 44

Reporting, report validation, report aggregation, abuse controls, case creation, and user-report APIs.

BACKEND MILESTONE 45

Moderation cases, automated moderation orchestration, human review, enforcement actions, moderation policy versions, and appeals.

BACKEND MILESTONE 46

Content safety workflows, high-severity safety cases, evidence references, escalation, privacy controls, and safety events.

BACKEND MILESTONE 47

Copyright/rights claims, regional restrictions, takedowns, expiration, appeals, restoration, and rights propagation.

BACKEND MILESTONE 48

Blocking, abuse prevention, spam controls, coordinated-abuse detection interfaces, propagation events, and enforcement.

BACKEND MILESTONE 49

Observability, reconciliation, queue monitoring, privacy validation, security hardening, and administrative integration.

BACKEND MILESTONE 50

Messaging, notifications, moderation, rights, safety, blocking, concurrency, security, performance, resilience, and production-readiness testing.

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

• Messaging
• Conversations
• Messages
• Delivery
• Read state
• Attachments
• Real-time messaging
• Notifications
• Notification preferences
• Push
• Email/SMS abstraction
• Reports
• Moderation
• Content safety
• Appeals
• Copyright/rights
• Takedowns
• Rights restrictions
• Safety workflows
• Blocking
• Abuse prevention
• Related events
• Related queues
• Related workers

Do not implement complete:

• Feed ranking
• Recommendation ranking
• Search ranking
• Advertising
• Creator analytics
• Platform analytics
• Administration UI
• Privacy export/deletion platform
• Infrastructure
• Frontend
• Mobile

Use previously established video, social graph, engagement, feed, recommendation, search, and identity systems.

────────────────────────────────────────

QUALITY BAR

Treat messaging, safety, moderation, rights, and abuse prevention as highly sensitive platform systems.

Assume:

• Hundreds of millions of users
• Millions of creators
• Billions of interactions
• Massive messaging traffic
• Large notification traffic
• Large moderation queues
• Large report volumes
• Multiple regions
• Strict privacy
• Strict safety requirements
• Strict authorization

Prioritize:

• Privacy
• Safety
• Security
• Reliable messaging
• Reliable notifications
• Correct moderation
• Correct rights enforcement
• Abuse resistance
• Idempotency
• Auditability
• Scalability
• Observability
• Production readiness
