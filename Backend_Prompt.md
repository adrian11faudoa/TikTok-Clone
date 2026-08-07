Using the approved Architecture Blueprint and the Master Prompt above:

Begin backend implementation ONLY.

Do NOT generate mobile code.

Do NOT generate frontend code.

Do NOT generate infrastructure code unless required for backend execution.

Assume the Architecture Blueprint has been approved.

Follow it exactly.

Never redesign APIs.

Never redesign the database.

Never change architecture without explicit approval.

Generate code incrementally according to the Master Prompt milestone strategy.

──────────────────────────────────────

MISSION

Build the complete production-ready backend for the enterprise short-form video social platform.

The backend must be capable of supporting:

- TikTok-scale feeds
- Instagram Reels-style interactions
- AI-powered recommendations
- Millions of concurrent users
- Billions of video views
- Hundreds of millions of uploaded videos

Every implementation must compile successfully before continuing.

──────────────────────────────────────

TECH STACK

Language

- TypeScript

Framework

- NestJS

Runtime

- Node.js

Database

- PostgreSQL
- Prisma ORM

Cache

- Redis

Search

- Elasticsearch

Storage

- AWS S3

CDN

- CloudFront

Media Processing

- FFmpeg

Background Jobs

- BullMQ

Communication

- REST API
- WebSockets
- Server-Sent Events (where appropriate)

Documentation

- OpenAPI / Swagger

──────────────────────────────────────

ARCHITECTURE

Strictly follow:

- Clean Architecture
- Domain Driven Design
- SOLID
- Repository Pattern
- Service Layer
- Dependency Injection
- CQRS where beneficial
- Event-Driven Architecture
- Feature-first organization

Never violate architectural boundaries.

──────────────────────────────────────

IMPLEMENT THE FOLLOWING DOMAINS

Identity

Authentication

Authorization

Users

Profiles

Social Graph

Followers

Following

Blocks

Restrictions

Videos

Media

Video Upload

Video Processing

Streaming

Captions

Subtitles

Comments

Replies

Likes

Favorites

Bookmarks

Shares

Hashtags

Mentions

Search

Feeds

Recommendations

Trending

Discover

Messaging

Notifications

Reports

Moderation

Analytics

Creator Studio

Administration

Audit

Feature Flags

System Configuration

──────────────────────────────────────

AUTHENTICATION

Implement:

- Registration
- Login
- Logout
- Email Verification
- Password Reset
- JWT
- Refresh Tokens
- MFA-ready Architecture
- Google OAuth
- Apple OAuth
- Session Management
- Device Management
- Token Revocation

──────────────────────────────────────

AUTHORIZATION

Implement complete RBAC.

Support:

Guest

User

Creator

Verified Creator

Moderator

Support

Administrator

Super Administrator

System Services

Generate:

Permission Guards

Policies

Decorators

Permission Matrix

──────────────────────────────────────

DATABASE

Generate:

Prisma Schema

Repositories

Migrations

Indexes

Constraints

Optimized Queries

Transactions

Read Models

Seeders

Partitioning Strategy

──────────────────────────────────────

VIDEO UPLOAD

Implement:

Chunked Uploads

Resumable Uploads

Upload Validation

Virus Scanning Hooks

Metadata Extraction

Signed URLs

Duplicate Detection

Upload Progress

──────────────────────────────────────

VIDEO PROCESSING

Implement asynchronous pipeline using BullMQ.

Support:

Video Validation

Transcoding

Compression

Adaptive Bitrate Generation

Thumbnail Generation

Preview Clip Generation

Caption Generation

Subtitle Processing

Watermark Pipeline

Metadata Extraction

Publishing

Cleanup

Retry Policies

Dead Letter Queues

──────────────────────────────────────

MEDIA

Implement:

AWS S3 Storage

Media Organization

Versioning

Signed URLs

Lifecycle Management

CloudFront Integration

Media Cleanup

──────────────────────────────────────

STREAMING

Implement architecture for:

Adaptive Streaming

HLS

Playback URLs

CDN Delivery

Bandwidth Optimization

Future DRM Support

──────────────────────────────────────

FEED SERVICE

Implement services for:

For You Feed

Following Feed

Trending Feed

Local Feed

Newest Feed

Discover Feed

Support:

Cursor Pagination

Infinite Scrolling

Caching

Ranking

Filtering

Personalization

──────────────────────────────────────

RECOMMENDATION SERVICE

Generate AI-ready architecture.

Support:

Watch History

Completion Rate

Engagement Score

Interest Graph

Creator Affinity

Category Affinity

Trending Detection

Cold Start

Similarity Scoring

Future ML Models

──────────────────────────────────────

SEARCH

Implement Elasticsearch.

Generate:

Video Search

Creator Search

User Search

Hashtag Search

Autocomplete

Filters

Synonyms

Ranking

Search Analytics

Reindex Jobs

──────────────────────────────────────

SOCIAL GRAPH

Implement:

Follow

Unfollow

Followers

Following

Mutual Connections

Blocks

Mute Users

Restrict Users

Suggestions

──────────────────────────────────────

COMMENTS

Implement:

Nested Replies

Mentions

Likes

Moderation

Reports

Pinned Comments

──────────────────────────────────────

ENGAGEMENT

Implement:

Likes

Favorites

Bookmarks

Shares

Views

Unique Views

Completion Tracking

Watch Time

──────────────────────────────────────

MESSAGING

Implement:

Direct Messages

Media Attachments

Typing Indicators

Read Receipts

Conversation Management

Unread Counts

──────────────────────────────────────

NOTIFICATIONS

Generate queue-based services for:

Push

Email

In-App

Future SMS Support

Include:

Retry Policies

Scheduling

Priority Queues

──────────────────────────────────────

MODERATION

Implement:

Video Reports

Comment Reports

User Reports

Manual Review Queue

Automatic Moderation Hooks

Copyright Detection Hooks

NSFW Detection Hooks

Spam Detection Hooks

Appeals

Strike System

Shadow Ban

──────────────────────────────────────

ANALYTICS

Generate services for:

Views

Watch Time

Retention Curves

Completion Rates

Engagement

Followers

Creator Growth

Daily Active Users

Monthly Active Users

Session Length

Trending Metrics

──────────────────────────────────────

BACKGROUND WORKERS

Implement BullMQ workers for:

Video Processing

Thumbnail Generation

Caption Generation

Subtitle Generation

Search Indexing

Feed Generation

Recommendation Updates

Notification Delivery

Analytics Aggregation

Cache Invalidation

Media Cleanup

Scheduled Maintenance

──────────────────────────────────────

EVENT BUS

Generate complete event-driven architecture.

Implement events including:

UserRegistered

VideoUploaded

VideoValidated

VideoProcessed

VideoPublished

LikeCreated

CommentCreated

ShareCreated

FollowCreated

FeedGenerated

RecommendationUpdated

NotificationQueued

ModerationCompleted

ReportSubmitted

AnalyticsUpdated

Define publishers and subscribers.

──────────────────────────────────────

CACHE

Implement Redis for:

Sessions

Feed Cache

Recommendation Cache

Trending Cache

User Cache

Search Cache

Rate Limiting

Distributed Locks

──────────────────────────────────────

SECURITY

Implement:

JWT

Refresh Tokens

RBAC

Secure Headers

Rate Limiting

Input Validation

SQL Injection Protection

XSS Protection

Secrets Management

Audit Logging

Encryption at Rest

Encryption in Transit

OWASP Top 10 Compliance

Anti-Spam Protection

Abuse Detection Hooks

──────────────────────────────────────

OBSERVABILITY

Generate:

Structured Logging

Metrics

Distributed Tracing

Health Checks

Readiness Checks

Liveness Checks

Performance Monitoring

Error Monitoring

──────────────────────────────────────

RESILIENCY

Implement:

Retry Policies

Circuit Breakers

Timeouts

Graceful Shutdown

Dead Letter Queues

Failure Recovery

Idempotency

──────────────────────────────────────

TESTING

Generate:

Unit Tests

Integration Tests

Repository Tests

Service Tests

Controller Tests

API Contract Tests

Performance Tests

Security Tests

──────────────────────────────────────

PROJECT ORGANIZATION

Maintain throughout development:

Current Milestone

Generated Files

Completed Modules

Remaining Modules

Dependencies

Database Objects

API Endpoints

Workers

Events

──────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never generate pseudo-code.

Never generate placeholders.

Never omit implementations.

Never regenerate unchanged files.

Only modify files when required.

──────────────────────────────────────

STOP CONDITIONS

Generate the backend incrementally according to the Master Prompt.

Each milestone should contain approximately 20–40 files.

At the end of every milestone:

- Verify the backend compiles successfully.
- Update the project index.
- List completed modules.
- Identify the next file to generate.

STOP and wait for approval before generating the next milestone.
