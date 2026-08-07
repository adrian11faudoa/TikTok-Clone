Using the approved Master Prompt above:

DO NOT begin implementation.

Your only task in this phase is to produce the complete engineering blueprint for the platform.

This architecture document will become the single source of truth for every future implementation phase.

All Backend, Frontend, Mobile, Infrastructure, DevOps and Testing implementations must strictly follow this blueprint.

Do not generate source code.

Do not generate placeholder implementations.

Produce only architecture, engineering specifications, API contracts, infrastructure decisions, domain models, and implementation plans.

──────────────────────────────────────

PROJECT

Build a production-ready enterprise short-form video social platform comparable to:

- TikTok
- Instagram Reels
- YouTube Shorts

The platform must support hundreds of millions of videos, AI-powered recommendations, creator tools, global delivery, and real-time interactions.

Design for long-term scalability, modularity, and maintainability.

──────────────────────────────────────

PRIMARY TECHNOLOGY STACK

Mobile

- React Native
- Expo
- TypeScript

Backend

- Node.js
- NestJS
- TypeScript

Database

- PostgreSQL
- Prisma ORM
- Redis
- Elasticsearch

Media Processing

- FFmpeg
- BullMQ

Storage

- AWS S3
- CloudFront CDN

Infrastructure

- Docker
- Kubernetes
- GitHub Actions

Observability

- Prometheus
- Grafana
- Loki
- OpenTelemetry

──────────────────────────────────────

SYSTEM REQUIREMENTS

Design for:

- 100M+ registered users
- 10M+ daily active users
- Billions of video views
- Hundreds of millions of uploaded videos
- Multi-region deployment
- Horizontal auto-scaling
- Zero-downtime deployments
- Event-driven communication
- High availability

──────────────────────────────────────

APPLICATIONS

Design complete architecture for:

- Mobile App
- Creator Studio
- Admin Dashboard
- Moderation Dashboard
- Public API
- Internal APIs

──────────────────────────────────────

ROLES

Design complete RBAC model for:

- Guest
- User
- Creator
- Verified Creator
- Moderator
- Support Agent
- Administrator
- Super Administrator
- System Services

Generate a complete permission matrix.

──────────────────────────────────────

DOMAIN MODULES

Design domain boundaries for:

Identity

Authentication

Authorization

Users

Profiles

Followers

Following

Social Graph

Videos

Media

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

Music

Discover

Trending

Feed

Recommendations

Search

Messaging

Notifications

Reports

Moderation

Analytics

Creator Studio

Advertising (future-ready)

Monetization (future-ready)

Administration

Audit

Feature Flags

System Configuration

──────────────────────────────────────

MICROSERVICE DECISION

Determine whether the platform should initially use:

- Modular Monolith
- Service-Oriented Architecture
- Microservices

Provide justification.

Design a migration strategy for future scaling.

──────────────────────────────────────

C4 ARCHITECTURE

Generate:

- Context Diagram
- Container Diagram
- Component Diagram
- Deployment Diagram

Describe every component and its responsibilities.

──────────────────────────────────────

DOMAIN-DRIVEN DESIGN

Define:

- Bounded Contexts
- Aggregates
- Entities
- Value Objects
- Repositories
- Domain Services
- Domain Events
- Application Services
- Policies
- Specifications

──────────────────────────────────────

DATABASE DESIGN

Generate complete database architecture including:

- ER Diagram
- Normalization Strategy
- Tables
- Indexes
- Foreign Keys
- Constraints
- Partitioning Strategy
- Read Replica Strategy
- Backup Strategy
- Audit Tables
- Soft Deletes
- Retention Policies

Include optimization for extremely large datasets.

──────────────────────────────────────

MEDIA ARCHITECTURE

Design:

- Upload Pipeline
- Video Validation
- Video Metadata
- FFmpeg Processing Pipeline
- Adaptive Bitrate Streaming
- Thumbnail Generation
- Preview Clip Generation
- Caption Generation
- Subtitle Storage
- CDN Delivery
- Media Lifecycle Policies
- Storage Organization

──────────────────────────────────────

FEED ARCHITECTURE

Design multiple feeds including:

- For You
- Following
- Trending
- Local
- Newest
- Discover

Explain ranking strategies and data flow.

──────────────────────────────────────

RECOMMENDATION SYSTEM

Design AI-ready recommendation architecture supporting:

- Personalized Ranking
- Watch History
- Completion Rate
- Engagement Scoring
- Interest Graph
- Similar Videos
- Similar Creators
- Trending Detection
- Cold Start Strategy
- Diversity Ranking

Design feature storage for future machine learning models.

──────────────────────────────────────

VIDEO PROCESSING

Design complete asynchronous pipeline for:

- Upload
- Validation
- Virus Scan
- Metadata Extraction
- Transcoding
- Compression
- Thumbnail Generation
- Caption Generation
- CDN Publishing

Describe every processing stage.

──────────────────────────────────────

SEARCH

Design Elasticsearch architecture.

Include:

- Video Search
- User Search
- Creator Search
- Hashtag Search
- Autocomplete
- Filters
- Synonyms
- Ranking
- Search Analytics
- Reindex Strategy

──────────────────────────────────────

SOCIAL GRAPH

Design architecture for:

- Followers
- Following
- Blocks
- Mutes
- Restrictions
- Friend Suggestions
- Mutual Connections

──────────────────────────────────────

MESSAGING

Design:

- Direct Messages
- Attachments
- Read Receipts
- Typing Indicators
- Conversation Storage
- Notification Flow

──────────────────────────────────────

NOTIFICATIONS

Design:

- Push Notifications
- Email Notifications
- In-App Notifications
- Notification Preferences
- Delivery Pipeline
- Retry Strategy

──────────────────────────────────────

MODERATION

Design moderation architecture supporting:

- User Reports
- Video Reports
- Comment Reports
- Automated Moderation
- Manual Review
- Appeals
- Shadow Bans
- Strike System
- Copyright Detection
- NSFW Detection
- Spam Detection

──────────────────────────────────────

EVENT ARCHITECTURE

Define all domain events including:

- UserRegistered
- VideoUploaded
- VideoProcessed
- FeedGenerated
- RecommendationUpdated
- LikeCreated
- CommentCreated
- ShareCreated
- CreatorFollowed
- NotificationQueued
- ModerationCompleted
- ReportSubmitted

Describe publishers and consumers.

──────────────────────────────────────

ASYNC PROCESSING

Identify all background workers.

Examples:

- Video Processing
- Search Indexing
- Recommendation Updates
- Notification Delivery
- Analytics Aggregation
- Thumbnail Generation
- Caption Generation
- Cache Invalidation
- Cleanup Jobs

──────────────────────────────────────

CACHE STRATEGY

Design Redis usage for:

- Sessions
- Feed Cache
- Trending Cache
- User Cache
- Search Cache
- Recommendation Cache
- Rate Limiting
- Distributed Locks

──────────────────────────────────────

SECURITY

Design:

- Authentication
- Authorization
- RBAC
- JWT
- Refresh Tokens
- Secrets Management
- Encryption
- Audit Logging
- Content Security
- OWASP Top 10 Compliance
- Fraud Prevention
- Abuse Prevention

──────────────────────────────────────

OBSERVABILITY

Design:

- Structured Logging
- Metrics
- Distributed Tracing
- Dashboards
- Alerts
- Health Checks
- Performance Monitoring

──────────────────────────────────────

AI ARCHITECTURE

Design architecture supporting:

- Recommendation Engine
- Caption Generation
- Subtitle Generation
- Video Tagging
- Smart Search
- Creator Insights
- Demand Forecasting
- Trend Prediction
- Future LLM Integrations

──────────────────────────────────────

FRONTEND ARCHITECTURE

Define:

- Feature-first Folder Structure
- Navigation
- State Management
- API Layer
- Feed Rendering Strategy
- Offline Support
- Video Caching
- Error Boundaries
- Accessibility
- Responsive Design

──────────────────────────────────────

MOBILE ARCHITECTURE

Define:

- Navigation
- Offline Synchronization
- Push Notifications
- Background Tasks
- Deep Linking
- Secure Storage
- Download Cache
- Playback Architecture

──────────────────────────────────────

DEVOPS ARCHITECTURE

Design:

- CI/CD Pipeline
- Branch Strategy
- Environment Strategy
- Container Strategy
- Kubernetes Organization
- Monitoring
- Rollback Strategy
- Disaster Recovery

──────────────────────────────────────

TESTING STRATEGY

Design:

- Unit Testing
- Integration Testing
- End-to-End Testing
- Contract Testing
- Performance Testing
- Load Testing
- Security Testing

──────────────────────────────────────

DOCUMENTATION

Generate:

- Architecture Overview
- Architecture Decision Records (ADRs)
- Folder Structure
- Coding Standards
- API Standards
- Database Standards
- Security Standards
- Deployment Standards
- Operational Runbooks
- Disaster Recovery Plan

──────────────────────────────────────

DELIVERABLE

Produce a complete enterprise engineering blueprint.

This blueprint must be sufficiently detailed that separate engineering teams can independently implement:

- Backend
- Mobile
- Infrastructure
- DevOps
- QA

without making additional architectural decisions.

STOP after completing the architecture blueprint.

Wait for approval before implementation begins.
