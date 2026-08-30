You are operating in Senior Engineering Team Mode.

Build the production-ready backend for feeds, personalized recommendations, ranking, exploration, trending, search, hashtags, sounds, creator discovery, and high-scale content distribution for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The backend must follow the approved TikTok-like architecture, domain boundaries, video architecture, social-graph architecture, engagement architecture, database ownership, Redis strategy, Kafka strategy, queue architecture, search abstraction, security model, privacy model, and Project Index.

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

• For You feed
• Following feed
• Creator/profile feed
• Trending feed
• Feed candidate generation
• Candidate retrieval
• Content eligibility
• Feed ranking
• Re-ranking
• Diversity
• Freshness
• Exploration
• Personalization
• Recommendation signals
• Recommendation feedback
• Recommendation caching
• Feed cursors
• Feed pagination
• Feed recovery
• Trending videos
• Trending hashtags
• Trending sounds
• Trending creators
• Search
• Search suggestions
• Creator search
• Video search
• Hashtag search
• Sound search
• Autocomplete
• Typo tolerance
• Search ranking
• Search indexing
• Search deletion
• Search reindexing
• Creator discovery
• Recommendation safety
• Block-aware discovery
• Region-aware discovery
• Experimentation foundations
• Recommendation observability
• Feed analytics

The implementation must support:

• Hundreds of millions of users
• Millions of creators
• Billions of video impressions
• Massive feed requests
• Large recommendation workloads
• Large search volumes
• High-frequency engagement signals
• Multiple regions
• Very low-latency feed generation
• High availability
• Eventual consistency for derived discovery systems

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

• Elasticsearch or OpenSearch

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
• Load/performance testing tools

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

Keep ranking/recommendation logic outside controllers.

Use repositories for persistence.

Use DTOs for external contracts.

Use centralized validation.

Use centralized error handling.

Use structured logging.

Use idempotency for asynchronous event processing.

Use cursor-based pagination.

Use cache versioning.

Never allow stale private/restricted content to become visible through discovery.

────────────────────────────────────────

DOMAIN OWNERSHIP

Maintain explicit boundaries between:

• Feed
• Candidate generation
• Recommendation
• Ranking
• Re-ranking
• Personalization
• Exploration
• Trending
• Search
• Search indexing
• Creator discovery
• Hashtag discovery
• Sound discovery
• Eligibility
• Experimentation
• Analytics

Do not combine:

• Search index with source-of-truth video data
• Feed cache with authoritative content state
• Recommendation ranking with engagement counters
• Trending with permanent content state
• Experiment assignment with authorization

────────────────────────────────────────

FEED TYPES

Implement separate feed strategies for:

1. For You
2. Following
3. Creator/profile
4. Trending
5. Search/discovery

Each feed must define:

• Candidate sources
• Eligibility filters
• Ranking
• Pagination
• Caching
• Refresh
• Fallback
• Observability

────────────────────────────────────────

FOR YOU FEED

Implement:

Request
→ User Context
→ Candidate Sources
→ Candidate Generation
→ Deduplication
→ Eligibility
→ Safety
→ Ranking
→ Re-ranking
→ Diversity
→ Exploration
→ Response

Candidate sources include:

• Follow graph
• User history
• Similar content
• Creator affinity
• Sound affinity
• Hashtag affinity
• Trending
• Fresh content
• Regional content
• Exploration pool

────────────────────────────────────────

USER CONTEXT

Construct an internal recommendation context containing only approved data such as:

• Recent watch history references
• Long-term content affinity
• Creator affinity
• Sound affinity
• Hashtag/topic affinity
• Negative feedback
• Follow graph references
• Region
• Language
• Platform
• Device class
• Content preferences

Do not expose internal user embeddings or sensitive internal signals to clients.

────────────────────────────────────────

WATCH SIGNALS

Consume signals such as:

• Impression
• Start
• Watch duration
• Completion
• Rewatch
• Skip
• Pause
• Like
• Comment
• Share
• Save
• Follow
• Not interested
• Report

Separate:

• Raw events
• Aggregated features
• Online recommendation state

────────────────────────────────────────

WATCH HISTORY

Design a scalable history system.

Support:

• Recent watched content
• Recent creators
• Recent sounds
• Recent hashtags/topics

Use appropriate retention.

Do not permanently retain unnecessary behavioral data.

────────────────────────────────────────

CANDIDATE GENERATION

Implement pluggable candidate sources.

Examples:

• Following
• Similar videos
• Creator affinity
• Sound affinity
• Hashtag affinity
• Trending
• Fresh uploads
• Regional trends
• Exploration

Each source should define:

• Candidate count
• Priority
• Eligibility
• Refresh behavior
• Failure fallback

────────────────────────────────────────

CANDIDATE DEDUPLICATION

Before ranking:

• Remove duplicates
• Remove already-seen content where policy requires
• Remove deleted content
• Remove blocked creators
• Remove restricted content
• Remove regionally unavailable content

Use efficient set membership.

────────────────────────────────────────

CONTENT ELIGIBILITY

Eligibility must evaluate:

• Video state
• Visibility
• Publication
• Moderation
• Rights
• Region
• User blocks
• Creator blocks
• Age restrictions
• Safety policy
• Feature flags
• Account restrictions

This is the final security/safety gate before content is returned.

────────────────────────────────────────

SEEN-CONTENT MANAGEMENT

Track recently served content.

Use Redis or approved ephemeral storage for:

• Recently served video IDs
• Feed session state
• Deduplication windows

Define:

• TTL
• Size limits
• User scope
• Region

Do not allow unbounded per-user memory growth.

────────────────────────────────────────

RANKING ARCHITECTURE

Implement ranking layers:

1. Candidate retrieval
2. Lightweight scoring
3. Main ranking
4. Re-ranking

Initial scoring signals may include:

• Predicted watch duration
• Completion
• Rewatch
• Like
• Comment
• Share
• Save
• Follow
• Freshness
• Creator affinity
• Sound affinity
• Topic affinity
• Negative feedback
• Content quality
• Region relevance

The system must allow later ML integration.

────────────────────────────────────────

RANKING ABSTRACTION

Create interfaces so ranking implementations can evolve from:

• Rule-based
• Weighted ranking
• Statistical models
• ML inference

without changing feed orchestration.

Do not bind feed services directly to one model implementation.

────────────────────────────────────────

MODEL VERSIONING

Ranking/recommendation responses should carry internal metadata such as:

• Model version
• Ranking version
• Feature version
• Experiment identifier

Do not expose sensitive model data to clients.

────────────────────────────────────────

RE-RANKING

After initial ranking, support:

• Creator diversity
• Sound diversity
• Topic diversity
• Freshness
• Exploration
• Safety
• Repetition controls

Re-ranking must not bypass eligibility.

────────────────────────────────────────

DIVERSITY

Prevent repetitive feeds.

Support configurable constraints for:

• Same creator
• Same sound
• Same topic
• Same hashtag
• Similar content

Define:

• Maximum consecutive content
• Sliding-window diversity
• Category quotas

────────────────────────────────────────

FRESHNESS

Balance:

• New content
• High-performing content
• Evergreen content
• Emerging creators

Use configurable freshness decay.

────────────────────────────────────────

EXPLORATION

Support controlled exploration.

Sources:

• New creators
• New videos
• New sounds
• New hashtags
• Less-exposed content

Define:

• Exploration ratio
• Eligibility
• Safety
• Diversity
• Feedback

Exploration must never bypass rights or safety.

────────────────────────────────────────

NEGATIVE FEEDBACK

Support:

• Skip
• Not interested
• Hide creator
• Hide sound
• Report
• Unfollow
• Block

Negative signals must influence future candidate generation or ranking according to configured policy.

────────────────────────────────────────

FOLLOWING FEED

Implement feed based on followed creators.

Support:

• Candidate retrieval
• Chronological mode where applicable
• Ranking mode where applicable
• Eligibility
• Diversity
• Pagination

Do not synchronously materialize enormous follower fan-outs.

────────────────────────────────────────

HYBRID FAN-OUT

Support both:

• Fan-out-on-write
• Fan-out-on-read

Use fan-out-on-write where appropriate for normal creators.

Use fan-out-on-read or hybrid strategies for high-fanout creators.

────────────────────────────────────────

HIGH-FANOUT CREATOR STRATEGY

For creators with extremely large audiences:

• Avoid millions of synchronous feed writes.
• Publish creator-content events.
• Make creator content an efficient candidate source.
• Merge candidate sources during read-time generation.

────────────────────────────────────────

FEED CURSORS

Use cursor-based pagination.

Cursor may contain:

• Feed type
• Generation timestamp
• Ranking version
• Candidate snapshot/version
• Page position
• Expiration

Cursor data should be opaque to clients.

────────────────────────────────────────

FEED SESSION

Optionally maintain short-lived feed sessions.

Track:

• Session ID
• User
• Feed type
• Candidate version
• Generated timestamp
• Expiration

This helps maintain stable pagination while recommendation data changes.

────────────────────────────────────────

FEED CACHE

Use Redis for:

• Feed candidate cache
• Short-lived personalized feed pages
• Following feed candidates
• Trending feed
• Creator suggestions

Keys must include:

• Environment
• Region where relevant
• User
• Feed type
• Version

Implement:

• TTL
• Stampede protection
• Refresh
• Invalidation

────────────────────────────────────────

FEED FALLBACKS

If recommendation infrastructure fails:

For You may fall back to:

• Trending
• Recent safe content
• Following content
• Regional popular content

Fallback content must still pass eligibility and safety.

────────────────────────────────────────

FEED FAILURE ISOLATION

A recommendation failure must not cause:

• Authentication failure
• Video upload failure
• Profile failure
• Comment failure
• Critical application failure

Use bounded timeouts.

────────────────────────────────────────

TRENDING

Implement:

• Trending videos
• Trending creators
• Trending sounds
• Trending hashtags

Use event-driven aggregation.

────────────────────────────────────────

TRENDING SIGNALS

Consider:

• Views
• Watch time
• Completion
• Likes
• Shares
• Saves
• Comments
• Growth rate
• Velocity
• Freshness

Use time decay.

────────────────────────────────────────

TRENDING ANTI-ABUSE

Detect:

• Bot engagement
• Burst anomalies
• Coordinated activity
• Artificial views
• Artificial likes
• Artificial shares

Do not rely on raw engagement counts alone.

────────────────────────────────────────

TRENDING WINDOWS

Support:

• Last hour
• Last few hours
• Daily
• Weekly
• Regional windows

Use configurable time windows.

────────────────────────────────────────

SEARCH ARCHITECTURE

Implement search for:

• Videos
• Creators
• Hashtags
• Sounds

Support:

• Full-text
• Prefix
• Autocomplete
• Typo tolerance
• Ranking
• Filters
• Region
• Language
• Safety
• Visibility

────────────────────────────────────────

SEARCH QUERY PROCESSING

Implement:

• Normalization
• Tokenization
• Query cleanup
• Language handling
• Typo correction
• Synonym support where appropriate
• Query classification

Do not send arbitrary user input directly into provider-specific query syntax.

────────────────────────────────────────

SEARCH RANKING

Rank using:

• Text relevance
• Engagement
• Freshness
• Creator relevance
• Popularity
• Region
• Safety
• Visibility

Keep ranking configurable.

────────────────────────────────────────

SEARCH SUGGESTIONS

Support suggestions for:

• Creators
• Videos
• Hashtags
• Sounds

Implement:

• Prefix matching
• Popularity
• Recent trends
• User context where permitted

Do not expose private search history to other users.

────────────────────────────────────────

SEARCH INDEXING

Use asynchronous event-driven indexing.

Flow:

Authoritative Data
→ Event
→ Indexing Queue
→ Search Index

Support:

• Create
• Update
• Delete
• Bulk indexing
• Reindex
• Alias switching

────────────────────────────────────────

SEARCH CONSISTENCY

Search may be eventually consistent.

Define acceptable freshness.

However:

• Deleted/private content must be removed rapidly enough for safety/privacy requirements.
• Restricted content must not remain publicly discoverable beyond approved limits.

────────────────────────────────────────

SEARCH REBUILD

Search must be rebuildable from authoritative data.

Support:

• Full reindex
• Incremental indexing
• Versioned indexes
• Alias swap
• Validation
• Rollback

────────────────────────────────────────

CREATOR DISCOVERY

Support:

• Creator recommendations
• Similar creators
• Trending creators
• New creators
• Follow suggestions

Use signals:

• Interests
• Follows
• Engagement
• Topic affinity
• Sound affinity

────────────────────────────────────────

HASHTAG DISCOVERY

Support:

• Hashtag page
• Related hashtags
• Trending hashtags
• Search
• Video counts

Respect:

• Moderation
• Visibility
• Rights
• Regional availability

────────────────────────────────────────

SOUND DISCOVERY

Support:

• Sound page
• Related sounds
• Trending sounds
• Search
• Video usage

Respect:

• Sound status
• Rights
• Region

────────────────────────────────────────

RECOMMENDATION EXPERIMENTATION

Prepare experimentation for:

• Ranking versions
• Candidate-source weighting
• Exploration rates
• Diversity rules
• UI/feed variants

Experiment assignments must be:

• Deterministic where required
• Persisted or reproducible
• Region-aware
• User-scoped

Do not use experiments as authorization.

────────────────────────────────────────

RECOMMENDATION CACHE VERSIONING

Invalidate/rekey caches when:

• Ranking version changes
• Eligibility policies change
• User blocks a creator
• Content is removed
• Feature flags change
• Major recommendation configuration changes

────────────────────────────────────────

EVENT PIPELINE

Consume signals from:

• Video impression
• Watch start
• Watch completion
• Skip
• Like
• Comment
• Share
• Save
• Follow
• Search
• Sound interaction
• Hashtag interaction
• Creator interaction
• Report
• Block
• Not interested

Produce:

• Candidate features
• Recommendation updates
• Trending updates
• Analytics events

────────────────────────────────────────

RECOMMENDATION FEATURE STORE ABSTRACTION

Create an abstraction for feature retrieval.

Initial implementation may use:

• PostgreSQL
• Redis
• Aggregated event-derived tables

Prepare for future:

• Dedicated feature store
• Online feature service
• Offline feature pipeline

Do not make a future ML platform mandatory for the initial system.

────────────────────────────────────────

RECOMMENDATION BACKFILL

When feature data is missing:

• Use safe default features
• Use regional trends
• Use new-content exploration
• Use popular content

Never fail the entire feed because one feature source is unavailable.

────────────────────────────────────────

REGIONALIZATION

Recommendation and search should support:

• Country
• Region
• Language
• Market
• Local trends

Do not expose regionally restricted content.

────────────────────────────────────────

DATABASE

Implement Prisma models and migrations for data that must be durable.

Potential entities:

• RecommendationProfile
• RecommendationFeatureAggregate
• RecommendationExperiment
• RecommendationAssignment
• FeedSession
• FeedCandidateSnapshotReference
• TrendingSnapshot
• TrendingCandidate
• SearchConfiguration
• SearchSynonym
• SearchRankingConfiguration
• CreatorDiscoveryProfile
• HashtagDiscoveryAggregate
• SoundDiscoveryAggregate
• RecommendationAuditReference

Do not store:

• Every feed impression indefinitely
• Every ranking intermediate result
• Unlimited recommendation candidate sets

in PostgreSQL.

────────────────────────────────────────

REDIS

Use Redis for:

• Personalized feed cache
• Candidate cache
• Feed sessions
• Seen-content sets
• Trending snapshots
• Search suggestion cache
• Creator suggestion cache
• Recommendation feature cache
• Experiment assignment cache where appropriate
• Rate limiting

Every key must define:

• Scope
• TTL
• Version
• Invalidation
• Memory expectations

────────────────────────────────────────

BULLMQ

Implement queues for:

• Feed refresh
• Candidate generation
• Recommendation feature refresh
• Trending aggregation
• Search indexing
• Search deletion
• Search reindex
• Creator discovery refresh
• Hashtag aggregation
• Sound aggregation
• Recommendation backfill

Every queue requires:

• Retry
• Backoff
• Timeout
• Concurrency
• Idempotency
• Dead-letter handling
• Monitoring

────────────────────────────────────────

KAFKA / REDPANDA

Consume:

• VideoPublished
• VideoRemoved
• VideoDeleted
• VideoLiked
• VideoUnliked
• CommentCreated
• VideoShared
• VideoSaved
• FollowCreated
• FollowRemoved
• UserBlocked
• UserUnblocked
• VideoViewed
• VideoCompleted
• SearchPerformed
• SoundUsed
• HashtagReferenced
• ReportCreated

Produce:

• FeedGenerated
• RecommendationServed
• RecommendationClicked
• TrendingUpdated
• SearchIndexed
• SearchRemoved
• CreatorRecommendationUpdated

All consumers must be idempotent.

────────────────────────────────────────

API

Implement production-ready REST APIs.

FEED

• Get For You feed
• Get Following feed
• Get Trending feed
• Get creator feed
• Continue feed using cursor

RECOMMENDATIONS

• Get recommended creators
• Get recommended sounds
• Get related videos

SEARCH

• Search videos
• Search creators
• Search hashtags
• Search sounds
• Suggestions/autocomplete

DISCOVERY

• Trending
• Related hashtags
• Related sounds
• Creator discovery

ADMIN / OPERATIONS

• Search configuration
• Ranking configuration
• Trending configuration
• Experiment configuration
• Reindex
• Feed/recommendation diagnostics where authorized

Every endpoint must implement:

• Authentication
• Authorization
• Validation
• Rate limiting
• Cursor pagination
• Consistent errors
• OpenAPI

────────────────────────────────────────

FEED API RESPONSE

Return only information required by clients.

Include:

• Video
• Creator
• Playback reference
• Engagement summary
• Feed metadata required by client

Do not expose:

• Internal ranking scores
• Internal candidate source
• Risk scores
• Internal user-feature vectors

────────────────────────────────────────

SECURITY

Protect against:

• Feed scraping
• Search scraping
• Recommendation scraping
• User-profile enumeration
• Private-content leakage
• Deleted-content leakage
• Block bypass
• Ranking manipulation
• Experiment manipulation
• Query injection
• Cache poisoning

Use:

• Authentication
• Authorization
• Rate limiting
• Query validation
• Cache isolation
• Content eligibility
• Secure cursors

────────────────────────────────────────

OBSERVABILITY

Instrument:

• Feed requests
• Candidate generation
• Ranking
• Re-ranking
• Recommendation
• Trending
• Search
• Indexing
• Cache hits/misses
• Feature retrieval

Track:

• Feed latency
• Candidate generation latency
• Ranking latency
• Recommendation latency
• Search latency
• Search freshness
• Feed cache hit rate
• Recommendation cache hit rate
• Consumer lag
• Queue depth
• Reindex duration
• Trending refresh latency

Track quality signals:

• Feed completion
• Skip rate
• Engagement
• Search success
• Recommendation engagement

Do not log private behavioral features unnecessarily.

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Eligibility
• Candidate deduplication
• Ranking
• Re-ranking
• Diversity
• Exploration
• Freshness
• Cursor creation
• Cursor validation
• Search normalization
• Search ranking
• Trending calculation

FEED TESTS

Test:

• For You
• Following
• Trending
• Creator feed
• Pagination
• Cache
• Fallback

RECOMMENDATION TESTS

Test:

• Candidate source failure
• Missing features
• Ranking fallback
• Experiment assignment
• Model/version changes

SEARCH TESTS

Test:

• Full text
• Prefix
• Typo
• Autocomplete
• Filters
• Deletion
• Reindex
• Restricted content

TRENDING TESTS

Test:

• Time windows
• Decay
• Velocity
• Regionalization
• Anti-abuse

CONCURRENCY TESTS

Test:

• Concurrent feed generation
• Cache stampede
• Duplicate indexing
• Concurrent deletion/indexing
• Ranking-version changes

SECURITY TESTS

Test:

• Private content leakage
• Block bypass
• Search IDOR
• Feed IDOR
• Cursor tampering
• Recommendation scraping

PERFORMANCE TESTS

Test:

• Feed throughput
• Candidate generation
• Ranking
• Search
• Trending
• Cache performance

────────────────────────────────────────

DOCUMENTATION

Generate:

• Feed architecture
• For You feed
• Following feed
• Trending
• Candidate generation
• Recommendation architecture
• Ranking architecture
• Re-ranking
• Diversity
• Exploration
• Negative signals
• Feed sessions
• Cursor architecture
• Feed caching
• Fallback strategy
• Social-graph fan-out
• High-fanout creators
• Search architecture
• Search indexing
• Search ranking
• Search freshness
• Creator discovery
• Hashtag discovery
• Sound discovery
• Experimentation
• Recommendation feature abstraction
• Event contracts
• Queue contracts
• Database schema
• Redis key catalog
• Security
• Privacy
• Observability
• Testing

────────────────────────────────────────

PROJECT INDEX

Update the backend Project Index with:

• Feed services
• For You
• Following
• Trending
• Candidate generation
• Ranking
• Re-ranking
• Diversity
• Exploration
• Recommendation profiles
• Recommendation features
• Experiments
• Feed sessions
• Cursor model
• Feed caches
• Trending caches
• Search services
• Search indexes
• Search configuration
• Creator discovery
• Hashtag discovery
• Sound discovery
• Kafka topics
• BullMQ queues
• Redis keys
• Database models
• APIs
• Events
• Tests
• Security
• Observability
• Generated files
• Remaining work
• Current milestone
• Dependencies

────────────────────────────────────────

IMPLEMENTATION MILESTONES

BACKEND MILESTONE 31

Feed foundation, feed contracts, feed sessions, cursor pagination, eligibility layer, and fallback architecture.

BACKEND MILESTONE 32

Following feed, social-graph integration, fan-out strategy, candidate retrieval, deduplication, and cache architecture.

BACKEND MILESTONE 33

For You candidate generation, recommendation context, feature retrieval, recommendation profile, and candidate-source orchestration.

BACKEND MILESTONE 34

Ranking abstraction, ranking versions, scoring pipeline, re-ranking, diversity, freshness, and exploration.

BACKEND MILESTONE 35

Recommendation feedback processing, negative signals, seen-content management, experiments, feature caching, and recommendation recovery.

BACKEND MILESTONE 36

Trending videos, trending creators, trending sounds, trending hashtags, time windows, decay, velocity, and anti-abuse.

BACKEND MILESTONE 37

Search ingestion, indexing, deletion, aliases, reindexing, full-text search, prefix search, and autocomplete.

BACKEND MILESTONE 38

Search ranking, typo tolerance, filters, creator discovery, hashtag discovery, sound discovery, regionalization, and search freshness.

BACKEND MILESTONE 39

Redis optimization, BullMQ workers, Kafka consumers, observability, cache-stampede protection, and operational diagnostics.

BACKEND MILESTONE 40

Feed, recommendation, search, trending, concurrency, security, privacy, load, performance, resilience, and production-readiness testing.

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

• For You feed
• Following feed
• Creator feed
• Trending
• Candidate generation
• Recommendation
• Ranking
• Re-ranking
• Diversity
• Freshness
• Exploration
• Negative signals
• Feed sessions
• Feed cursors
• Feed caching
• Recommendation feedback
• Experiments
• Trending aggregation
• Search
• Search indexing
• Search ranking
• Autocomplete
• Search deletion
• Search reindexing
• Creator discovery
• Hashtag discovery
• Sound discovery
• Regional discovery
• Related events
• Related queues
• Related workers

Do not implement complete:

• Messaging
• Notifications
• Moderation engine
• Safety platform
• Reporting
• Copyright workflow
• Advertising
• Creator analytics
• Platform analytics
• Administration
• Privacy export/deletion platform
• Infrastructure
• Frontend
• Mobile

Use the existing video, social graph, engagement, sound, hashtag, and identity systems.

────────────────────────────────────────

QUALITY BAR

Treat feeds, recommendations, search, and trending as mission-critical discovery infrastructure.

Assume:

• Hundreds of millions of users
• Millions of creators
• Billions of daily impressions
• Massive feed traffic
• Massive search traffic
• Massive recommendation traffic
• Multiple regions
• Strict privacy
• Strict content-safety requirements
• Very low latency requirements

Prioritize:

• Low feed latency
• Recommendation resilience
• Safe content eligibility
• High cache efficiency
• Horizontal scalability
• Rebuildability
• Eventual-consistency correctness
• Anti-abuse
• Privacy
• Observability
• Maintainability
• Production readiness
