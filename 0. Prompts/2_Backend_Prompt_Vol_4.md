# TikTok-Style Short-Form Video Platform — Backend Prompt — Volume 4

# ROLE

You are the senior **Backend Discovery, Search, and Recommendation Engineering Agent** responsible for implementing the production-grade backend capabilities for **content discovery, search, trending discovery, recommendation candidate generation, personalization signals, ranking orchestration, and recommendation-serving foundations** for a TikTok-style short-form video platform.

Operate with the combined standards of:

* Staff Backend Engineer
* Recommendation Systems Engineer
* Search Engineer
* Distributed Systems Engineer
* Data Platform Engineer
* Database Engineer
* API Engineer
* Security Engineer
* Performance Engineer
* SRE
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the backend discovery and recommendation foundations within the bounded scope defined below.

This is a backend implementation milestone.

Do not implement the complete platform.

Do not implement unrelated web UI, mobile UI, production cloud provisioning, complete notification delivery, complete moderation administration, or full creator analytics dashboards.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator participation;
* personalized content consumption;
* content discovery;
* recommendations;
* social interaction;
* media processing;
* moderation;
* notifications;
* analytics;
* large-scale operations.

The completed system is intended to support:

* accounts and profiles;
* creators;
* follow relationships and blocking;
* short-form video publishing;
* media processing and playback;
* personalized feeds;
* following feeds;
* discovery;
* trending;
* search;
* creator discovery;
* hashtag discovery;
* sound/audio discovery;
* recommendations;
* likes;
* comments;
* replies;
* shares;
* favorites;
* views and watch-time events;
* notifications;
* moderation;
* reporting;
* administration;
* creator analytics;
* event streaming;
* background jobs;
* observability;
* production infrastructure.

This prompt implements the backend foundations for **search, discovery, candidate generation, recommendation signals, deterministic ranking, personalization interfaces, and scalable recommendation serving**.

---

# TARGET USERS

The implementation must support:

* viewers;
* authenticated users;
* creators;
* downstream recommendation consumers;
* search consumers;
* web clients;
* mobile clients;
* moderation and safety systems;
* analytics systems.

All search and recommendation results must respect authoritative:

* account state;
* content visibility;
* privacy;
* blocking;
* moderation state;
* deletion state.

---

# SCALE TARGET

The completed platform must be capable of evolving toward:

* millions to hundreds of millions of users;
* very large video catalogs;
* large creator populations;
* high search traffic;
* very high feed-request volume;
* high recommendation throughput;
* viral traffic spikes;
* large behavioral-event streams;
* large searchable hashtag/creator/content indexes.

Search and recommendation requests must remain bounded and horizontally scalable.

Do not design request paths that require scanning the entire video catalog.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible and justified alternative, use:

* Node.js;
* TypeScript;
* NestJS or equivalent structured backend architecture;
* PostgreSQL;
* Redis;
* Kafka or Redpanda for durable behavioral/event streams;
* BullMQ or equivalent job processing where appropriate;
* a production-appropriate search engine such as OpenSearch/Elasticsearch or another justified repository-compatible engine;
* REST APIs;
* OpenTelemetry-compatible observability.

Do not introduce both OpenSearch and Elasticsearch as separate search systems.

Select one implementation consistent with the repository.

If a search engine has not yet been provisioned, implement the repository-side integration, index definitions, indexing workers, and configuration without claiming production deployment.

---

# REPOSITORY INSPECTION

Before modifying code:

1. Inspect the repository.
2. Identify the existing video/content domain.
3. Inspect existing feed and candidate-generation logic.
4. Inspect behavioral-event ingestion and event consumers.
5. Inspect existing PostgreSQL models and migrations.
6. Inspect Redis conventions.
7. Inspect existing search abstractions or indexes.
8. Inspect authentication, privacy, moderation, and block handling.
9. Inspect tests.
10. Identify reusable code.
11. Preserve compatible behavior.
12. Resolve contradictions in current discovery/search implementations where necessary.
13. Do not fabricate repository state.

The repository is authoritative for actual implementation state.

This prompt is authoritative for this milestone's required work.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the backend foundations required for:

* creator search;
* user/profile search;
* hashtag search;
* video/content search;
* sound/audio discovery where applicable;
* trending discovery;
* search indexing;
* index updates;
* deletion propagation;
* visibility-aware search;
* moderation-aware search;
* blocked-entity filtering;
* candidate generation;
* recommendation-feature consumption;
* deterministic recommendation ranking;
* personalization interfaces;
* recommendation result assembly;
* diversity safeguards;
* freshness handling;
* recommendation caching;
* recommendation fallback;
* search and recommendation background jobs;
* observability;
* rate limiting;
* tests;
* documentation.

Do not build a fake search engine.

Do not hardcode a permanent recommendation list.

Do not fabricate machine-learning predictions.

---

# SEARCH ARCHITECTURE

Implement the selected search-engine integration.

Searchable domains may include:

* users;
* creators;
* hashtags;
* videos;
* sounds/audio references.

Define explicit index mappings and document schemas.

Each indexed document must contain only data necessary for search and filtering.

Do not use the search index as the authoritative source of business truth.

PostgreSQL and other authoritative systems remain the source of truth for entities.

---

# SEARCH INDEX DOCUMENTS

Implement search document representations for applicable entities.

Documents should contain, as appropriate:

* stable entity ID;
* searchable text;
* normalized text;
* display text;
* entity type;
* creator/user reference;
* visibility;
* moderation state;
* deletion state;
* timestamps;
* popularity/discovery signals where justified;
* language/locale metadata where supported.

Do not duplicate sensitive or private data unnecessarily.

Do not index fields that should never be searchable.

---

# TEXT NORMALIZATION

Implement deterministic normalization for search inputs.

Consider:

* Unicode normalization;
* case normalization;
* whitespace normalization;
* safe tokenization;
* canonical hashtag handling;
* username/handle normalization.

Do not alter the stored authoritative text merely for search normalization.

Search normalization must not create identity ambiguity.

---

# SEARCH QUERY CONTRACT

Implement API behavior for bounded search requests.

Define:

* query length limits;
* allowed resource types;
* filters;
* pagination;
* sorting;
* locale/language parameters where supported;
* result limits;
* empty-query behavior;
* malformed-query handling.

Do not allow unbounded wildcard or expensive query patterns.

Protect the search endpoint from query abuse.

---

# SEARCH RESULT CONTRACT

Return a stable result structure containing only fields appropriate to the requesting client.

Results must support:

* entity ID;
* entity type;
* display metadata;
* authorized media/profile preview where applicable;
* relevance or discovery metadata only when safe and useful;
* pagination.

Do not expose internal search scores or infrastructure details unless explicitly required.

---

# SEARCH PRIVACY FILTERING

Search results must enforce:

* private-account rules;
* private-video rules;
* account restrictions;
* blocks;
* moderation state;
* deletion state.

A search engine must never become a privacy bypass.

Even when the index contains a stale document, the application must prevent unauthorized access.

Use authoritative filtering where necessary.

---

# SEARCH INDEXING PIPELINE

Implement asynchronous indexing.

Support events such as:

* video published;
* video updated;
* video visibility changed;
* video deleted;
* profile updated;
* creator status changed;
* hashtag created/updated;
* sound updated;
* moderation state changed.

Indexing workers must:

* consume canonical events;
* be idempotent;
* handle retries;
* handle out-of-order updates;
* avoid stale writes where version metadata permits;
* expose processing failures.

---

# SEARCH DELETION PROPAGATION

Implement deletion/restriction propagation.

When content becomes:

* deleted;
* removed;
* private;
* restricted;

the search index must eventually reflect the authoritative state.

Where immediate authorization cannot be guaranteed through index synchronization, the application must perform authoritative checks before returning or exposing sensitive results.

---

# INDEX REBUILDABILITY

The search system must be rebuildable from authoritative data.

Implement or document:

* index creation;
* index migration/versioning;
* index rebuild;
* backfill;
* alias/swap strategy where supported;
* retry;
* progress tracking;
* resumability;
* cleanup of obsolete indexes.

Do not make a search index an irreplaceable source of business truth.

---

# SEARCH INDEX VERSIONING

Support compatible index evolution.

When index mappings change materially:

* create a new index version where appropriate;
* backfill from authoritative data;
* validate document counts and representative queries;
* migrate aliases;
* retain rollback capability where practical.

Do not perform destructive mapping changes that silently corrupt the only available search index.

---

# SEARCH RELEVANCE

Implement a deterministic initial relevance strategy using appropriate factors such as:

* text relevance;
* exact/partial match;
* freshness;
* popularity;
* creator relevance;
* engagement quality.

Do not claim parity with a proprietary TikTok search-ranking algorithm.

The implementation must expose clear extension points for more advanced ranking later.

---

# HASHTAG DISCOVERY

Implement hashtag discovery.

Support:

* normalized hashtag lookup;
* associated content counts where appropriate;
* recent/trending signals;
* visibility filtering;
* moderation filtering;
* bounded pagination.

Do not count deleted/restricted content as publicly discoverable merely because historical rows exist.

---

# CREATOR DISCOVERY

Implement creator/user discovery.

Support:

* username/handle search;
* display-name search where applicable;
* creator relevance;
* follower/engagement indicators that are safe to expose;
* profile visibility;
* block filtering;
* account-state filtering.

Do not expose private account information through search.

---

# VIDEO DISCOVERY

Implement searchable video/content discovery.

Support:

* caption text;
* hashtags;
* creator identity;
* sound/audio metadata where applicable;
* freshness;
* engagement/discovery signals.

Only return videos currently eligible for discovery.

Do not bypass playback authorization.

---

# SOUND DISCOVERY

Where sounds/audio references are searchable:

* index eligible sounds;
* support name/title discovery;
* support creator/source discovery;
* enforce visibility;
* enforce moderation state;
* enforce deletion;
* provide bounded result lists.

Do not expose unavailable or restricted sound records through stale indexes.

---

# TRENDING DISCOVERY

Implement a production-oriented trending discovery service.

Trending candidates may combine:

* recent views;
* watch time;
* completion rate;
* likes;
* comments;
* shares;
* favorites;
* growth velocity;
* freshness.

Use time windows.

Avoid ranking solely by lifetime engagement.

---

# TRENDING WINDOWS

Support configurable windows such as:

* short-term;
* daily;
* multi-day.

The exact windows should be configuration-driven.

Do not scatter fixed window durations throughout application code.

---

# TRENDING SAFETY FILTERS

Trending results must exclude or restrict:

* deleted videos;
* moderation-restricted content;
* private content;
* blocked creators;
* content otherwise ineligible for discovery.

Safety filtering must occur independently of the ranking score.

---

# RECOMMENDATION ARCHITECTURE

Implement the backend recommendation-serving foundation.

Maintain explicit stages:

1. candidate generation;
2. candidate validation;
3. ranking;
4. policy filtering;
5. diversity/freshness controls;
6. final assembly.

Do not collapse every responsibility into one controller or database query.

The recommendation interface must be extensible.

---

# RECOMMENDATION CANDIDATE MODEL

Implement a candidate model containing appropriate fields such as:

* candidate ID;
* video ID;
* creator ID;
* source;
* generatedAt;
* freshness;
* feature references;
* preliminary score;
* eligibility metadata.

Candidate objects must not be treated as authoritative content records.

---

# CANDIDATE SOURCES

Support candidate-source adapters for applicable inputs:

* followed creators;
* trending;
* recent content;
* popular content;
* hashtag/topic affinity;
* creator affinity;
* prior engagement similarity;
* externally generated recommendation candidates where later systems provide them.

Candidate sources must be independently testable.

Do not hardwire the entire recommendation system to one source.

---

# PERSONALIZATION SIGNALS

Consume behavioral signals such as:

* watch time;
* completion;
* skip;
* replay;
* like;
* comment;
* share;
* favorite;
* follow;
* negative feedback;
* creator affinity;
* topic affinity.

Do not treat every signal as equally valuable.

Define a clear interface for feature extraction and scoring.

The current implementation may use deterministic weights.

---

# FEATURE REPRESENTATION

Implement a backend representation for recommendation features appropriate to the current scope.

Possible feature categories include:

* user affinity;
* creator affinity;
* topic affinity;
* content freshness;
* content popularity;
* prior interaction;
* watch completion;
* negative feedback.

Do not introduce a heavyweight feature-store platform unless justified by the repository and current requirements.

The implementation must preserve a path to future feature-store integration.

---

# FEATURE FRESHNESS

Recommendation features may become stale.

Define and implement appropriate:

* TTL;
* refresh;
* fallback;
* missing-feature behavior.

A missing feature must not cause recommendation requests to fail completely.

---

# INITIAL RANKING

Implement a deterministic ranking strategy.

The initial ranker may combine:

* predicted engagement proxies available from existing data;
* freshness;
* creator affinity;
* topic affinity;
* popularity;
* prior user interactions;
* diversity.

The exact weights must be represented as configuration or a clearly isolated scoring component.

Do not scatter ranking weights across controllers and repositories.

---

# RANKING EXTENSIBILITY

Define interfaces allowing later replacement of deterministic ranking with:

* trained machine-learning models;
* remote ranking services;
* feature-store-backed scoring;
* experimentation variants.

The current implementation must not require an ML platform.

Do not fabricate model predictions.

---

# POLICY FILTERING

Recommendation ranking must occur separately from final policy eligibility.

Before returning a recommendation:

* verify content visibility;
* verify moderation state;
* verify deletion state;
* verify account state;
* apply block rules;
* enforce age/safety restrictions where applicable to the current product contract.

Policy filtering must override recommendation scores.

A highly ranked but ineligible item must never be returned.

---

# DIVERSITY

Implement deterministic safeguards to reduce:

* repeated creator exposure;
* duplicate videos;
* overly narrow topic concentration;
* repeated content from one candidate source.

Do not claim sophisticated personalization diversity modeling.

The diversity layer must remain independently testable.

---

# FRESHNESS

Recommendation results must balance discovery with freshness.

Where appropriate, expose configuration for:

* maximum candidate age;
* freshness weighting;
* recent-publication boosts;
* stale-content suppression.

Do not permit old content to dominate solely due to lifetime engagement.

---

# RECOMMENDATION CACHE

Use Redis where caching materially improves performance.

Cache only derived recommendation results.

Define:

* key schema;
* TTL;
* user-segment scope;
* invalidation;
* stale behavior;
* fallback.

Do not cache private content without accounting for user-specific authorization.

Never allow one user's personalized feed cache to leak into another user's response.

---

# ANONYMOUS USER RECOMMENDATIONS

If anonymous viewing is supported, implement a safe anonymous recommendation path where appropriate.

Use bounded signals such as:

* session-level interactions;
* coarse content affinity;
* trending/discovery data.

Do not require persistent personal profiles for anonymous viewing.

Do not retain unnecessary personal information solely to support anonymous recommendations.

---

# AUTHENTICATED PERSONALIZATION

For authenticated users, incorporate available signals while respecting privacy.

The system should be able to account for:

* creator follows;
* interaction history;
* content affinity;
* negative signals;
* session context;
* recency.

Do not expose internal personalization features to clients unless explicitly intended.

---

# NEGATIVE FEEDBACK

Where the product supports negative feedback, define backend handling for signals such as:

* skip;
* "not interested";
* creator/content suppression.

Negative feedback should influence candidate selection/ranking through a clear internal interface.

Do not treat a single accidental skip as a permanent account-level block unless the product explicitly requires that behavior.

---

# RECOMMENDATION FALLBACKS

Define safe fallback paths for:

* recommendation service unavailable;
* feature data unavailable;
* ranking failure;
* cache miss under dependency outage.

Fallback may use:

* following content;
* trending content;
* recent eligible content;
* deterministic popularity.

All fallback paths must still enforce privacy, moderation, deletion, and block rules.

---

# RECOMMENDATION API

Implement the backend endpoint required to retrieve a personalized recommendation page.

Support:

* authentication/anonymous mode where applicable;
* bounded page size;
* cursor;
* deterministic continuation behavior;
* feed-item serialization;
* content eligibility;
* engagement summaries;
* playback metadata references.

Do not expose internal candidate scores or user-profile features.

---

# CONTINUATION / CURSOR

Recommendation pagination must remain coherent across requests.

The cursor must preserve enough ordering information to avoid:

* duplicate items;
* excessive repetition;
* unstable ranking within a bounded page sequence.

Do not store unlimited per-user feed state in Redis.

Where necessary, use compact cursors or bounded session state.

---

# DISCOVERY API

Implement APIs for:

* general search;
* creator search;
* hashtag search;
* video search;
* sound search where applicable;
* trending discovery.

All lists must be bounded.

Use the project's canonical cursor pagination and error conventions.

---

# RATE LIMITING

Apply rate limits to:

* search;
* trending requests;
* recommendation requests;
* candidate-refresh operations;
* index-management operations exposed through internal/admin interfaces.

Prevent abusive high-frequency queries from exhausting:

* search infrastructure;
* Redis;
* database connections;
* ranking workers.

---

# INTERNAL / ADMIN INDEX OPERATIONS

Where repository architecture requires operational endpoints or commands for:

* index rebuild;
* index health;
* backfill;
* alias switch;
* recommendation cache invalidation;

protect them with strong administrative authorization.

Do not expose operational index controls to ordinary users.

---

# ASYNCHRONOUS JOBS

Implement background jobs for applicable:

* search indexing;
* search backfill;
* trending aggregation;
* candidate precomputation;
* recommendation cache refresh;
* stale-result cleanup;
* index reconciliation.

Every job must define:

* type;
* version;
* payload;
* retry;
* timeout;
* backoff;
* idempotency;
* concurrency;
* failure behavior;
* observability.

---

# EVENT CONSUMERS

Implement consumers for relevant events such as:

* VideoPublished;
* VideoUpdated;
* VideoVisibilityChanged;
* VideoDeleted;
* User/ProfileUpdated;
* FollowCreated;
* FollowRemoved;
* BlockCreated;
* BlockRemoved;
* VideoLiked;
* CommentCreated;
* VideoShared;
* VideoFavorited;
* VideoViewed;
* VideoWatchProgressed;
* VideoCompleted;
* VideoSkipped;
* NegativeFeedbackRecorded;
* ModerationStateChanged.

Consumers must remain safe under duplicate and out-of-order delivery.

---

# OUT-OF-ORDER EVENTS

Where events update:

* search documents;
* popularity signals;
* recommendation features;
* trending aggregates;

protect against stale state overwriting newer state.

Use version numbers, timestamps, sequence numbers, or another justified mechanism.

Do not assume event ordering is globally guaranteed.

---

# SEARCH CONSISTENCY

Document and implement eventual consistency between:

* authoritative PostgreSQL state;
* event stream;
* search indexes.

Search does not need to become immediately consistent for every update, but privacy/security-sensitive access must be protected by authoritative checks where index staleness could cause exposure.

---

# RECOMMENDATION CONSISTENCY

Recommendation data is derived.

Document which values may be eventually consistent:

* engagement features;
* popularity;
* trending scores;
* creator affinity;
* topic affinity.

The API must remain correct when derived data is temporarily stale.

---

# SEARCH / RECOMMENDATION SECURITY

Protect against:

* search scraping;
* enumeration;
* unauthorized private-content discovery;
* blocked-creator leakage;
* deleted-content leakage;
* malicious query injection;
* expensive query patterns;
* recommendation abuse;
* behavioral-signal poisoning.

Do not let users directly manipulate internal ranking scores.

Do not trust client-generated popularity values.

---

# SIGNAL INTEGRITY

Behavioral events can be manipulated.

Within this scope, implement reasonable validation against obvious abuse such as:

* impossible watch durations;
* impossible completion percentages;
* excessive event rates;
* malformed event sequences;
* repeated identical signals.

Do not attempt a full machine-learning fraud detector in this milestone.

Create a clean extension boundary for future integrity systems.

---

# DATABASE SUPPORT

Implement the PostgreSQL persistence required for:

* search metadata not stored solely in the search engine;
* recommendation configuration;
* ranking configuration;
* discovery metadata;
* administrative/indexing state where appropriate.

Do not duplicate complete search documents into PostgreSQL unnecessarily.

Do not store derived recommendation pages as permanent authoritative business records unless the architecture specifically requires them.

---

# REDIS SUPPORT

Use Redis where appropriate for:

* recommendation result caches;
* trending snapshots;
* bounded feature caches;
* rate limits;
* search result acceleration where justified.

Define:

* key names;
* TTL;
* serialization;
* invalidation;
* stale behavior;
* failure behavior.

Redis remains non-authoritative for business entities.

---

# SEARCH ENGINE FAILURE

The system must degrade safely when the search provider is unavailable.

Possible behavior:

* return a controlled dependency error;
* use a limited PostgreSQL-backed fallback for narrow search cases where practical;
* disable expensive discovery functions temporarily;
* preserve content APIs.

Do not route unlimited high-volume search traffic through PostgreSQL merely because the search cluster is unavailable.

---

# RECOMMENDATION DEPENDENCY FAILURE

When derived recommendation data is unavailable:

* return deterministic fallback candidates;
* avoid returning stale personalized content that violates current authorization;
* preserve feed availability where possible;
* record the fallback activation.

Do not fail the entire application because recommendation ranking is temporarily unavailable.

---

# OBSERVABILITY

Instrument:

* search latency;
* search error rate;
* index lag;
* index failures;
* backfill progress;
* search-result rejection;
* recommendation latency;
* candidate-generation latency;
* ranking latency;
* policy-filter rejection;
* diversity filtering;
* cache hit/miss;
* recommendation fallback activation;
* feature freshness;
* trending refresh;
* event-consumer lag;
* ranking configuration changes.

Propagate:

* request ID;
* correlation ID;
* event ID;
* job ID;
* trace context.

Do not log:

* private user data unnecessarily;
* internal ranking features containing sensitive information;
* authentication tokens;
* secrets.

---

# RELIABILITY

The search and recommendation systems must tolerate:

* duplicate events;
* delayed events;
* out-of-order events;
* index downtime;
* Redis outages;
* event-broker outages;
* worker crashes;
* partial backfills;
* stale recommendation features.

Use:

* bounded retries;
* idempotent consumers;
* resumable jobs;
* reconciliation;
* explicit fallback behavior.

Do not allow a failed index update to silently delete valid search results from the authoritative product.

---

# RECONCILIATION

Implement or document reconciliation for:

* stale search documents;
* missing search documents;
* deleted content still indexed;
* orphaned search documents;
* stale trending candidates;
* invalid recommendation candidates;
* stale personalized caches.

Reconciliation must be:

* bounded;
* repeatable;
* observable;
* safe under concurrency.

---

# SECURITY TESTING

Add tests for:

* private-content search leakage;
* blocked-creator search leakage;
* deleted-content search leakage;
* private-profile discovery leakage;
* malformed search queries;
* expensive query abuse protections;
* recommendation access control;
* anonymous/user cache isolation;
* recommendation cache leakage;
* event-signal poisoning;
* unauthorized index operations.

---

# SEARCH TESTING

Test:

* exact matches;
* partial matches;
* normalization;
* creator search;
* hashtag search;
* video search;
* sound search;
* pagination;
* index updates;
* deletes;
* moderation changes;
* private-content filtering;
* block filtering;
* stale-index authorization checks.

Use representative fixtures.

Do not require a production search cluster for every unit test.

---

# RECOMMENDATION TESTING

Test:

* candidate generation;
* deterministic ranking;
* ranking configuration;
* policy filtering;
* privacy;
* blocking;
* deletion;
* moderation;
* diversity;
* freshness;
* anonymous mode where supported;
* authenticated personalization;
* negative signals;
* cache isolation;
* fallback behavior.

The same inputs should produce deterministic results when the same ranking configuration is applied.

---

# EVENT / JOB TESTING

Test:

* duplicate event handling;
* out-of-order event handling;
* index update retries;
* recommendation feature updates;
* trending aggregation;
* job retry;
* failed jobs;
* backoff;
* idempotency;
* reconciliation.

Do not validate event consumers only through mocked interfaces.

---

# PERFORMANCE TESTING

Where practical, test:

* search latency under representative query sizes;
* feed recommendation latency;
* candidate generation;
* ranking throughput;
* cache hit paths;
* batch indexing;
* event-consumer throughput.

Do not claim large-scale production performance unless representative load testing was actually performed.

---

# DOCUMENTATION

Update repository documentation describing:

* search architecture;
* search index structure;
* index lifecycle;
* query API;
* discovery APIs;
* trending architecture;
* recommendation architecture;
* candidate sources;
* deterministic ranking;
* personalization signals;
* policy filtering;
* recommendation caching;
* fallback behavior;
* search/index rebuild procedures;
* event consumers;
* background jobs;
* configuration;
* rate limits;
* operational troubleshooting.

Clearly distinguish current deterministic recommendation behavior from future machine-learning extensions.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* search engine integration;
* search indexes;
* searchable entity documents;
* search normalization;
* search API;
* creator discovery;
* hashtag discovery;
* video discovery;
* sound/audio discovery where applicable;
* search indexing;
* index updates;
* deletion propagation;
* index rebuild/reindex capabilities;
* trending discovery;
* trending aggregation extensions where required;
* recommendation candidate model;
* candidate-source adapters;
* personalization feature interfaces;
* deterministic ranking;
* policy filtering;
* diversity safeguards;
* freshness behavior;
* recommendation caching;
* anonymous recommendation foundation where applicable;
* authenticated personalization foundation;
* negative-feedback integration;
* recommendation fallback;
* recommendation API;
* discovery APIs;
* relevant background jobs;
* event consumers;
* signal-integrity checks;
* reconciliation;
* rate limiting;
* observability;
* security controls;
* database changes required by this scope;
* tests;
* documentation.

This prompt does **not** implement:

* machine-learning model training;
* a full feature-store platform;
* a GPU inference cluster;
* advanced experimentation infrastructure;
* complete analytics warehousing;
* push notification delivery;
* complete moderation workflows;
* complete administration UI;
* web UI;
* mobile UI;
* production cloud provisioning.

Create only the interfaces necessary for those future systems to integrate with search and recommendation.

---

# COMPATIBILITY REQUIREMENTS

Preserve compatibility with:

* account/profile privacy;
* social graph;
* blocking;
* video/content lifecycle;
* media/playback;
* engagement events;
* feed APIs;
* future notification systems;
* future moderation systems;
* future analytics systems;
* web clients;
* mobile clients;
* infrastructure;
* QA.

Preserve the canonical project:

* identifiers;
* timestamps;
* API error model;
* pagination;
* visibility states;
* moderation states;
* event envelope;
* queue/job conventions;
* Redis conventions;
* domain terminology.

Do not create competing definitions.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* PostgreSQL;
* Redis;
* Kafka/Redpanda;
* OpenSearch/Elasticsearch or the repository's selected search engine.

Use available development/test infrastructure.

If the search engine or another dependency is unavailable:

* do not fabricate successful connectivity;
* validate schemas and repository-side behavior that can run locally;
* report the exact unavailable dependency;
* distinguish integration tests from provider connectivity.

Do not claim that a production search cluster has been provisioned unless it was actually verified.

---

# VALIDATION

After implementation:

1. Run formatting.
2. Run linting.
3. Run TypeScript type checking.
4. Run database migration validation.
5. Validate search index mappings/schemas.
6. Run search unit tests.
7. Run search integration tests where infrastructure is available.
8. Run recommendation unit tests.
9. Run recommendation integration tests where infrastructure is available.
10. Run event-consumer tests.
11. Run background-job tests.
12. Run security tests.
13. Run performance benchmarks where practical.
14. Validate API contracts.
15. Validate index rebuild/reconciliation behavior where testable.
16. Inspect the final diff.
17. Search for secrets or credentials.
18. Verify that no unrelated major subsystem was modified.

Do not claim that search-provider integration passed when the provider was unavailable.

Do not claim ML recommendation behavior exists when the implementation is deterministic.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* search modules;
* search engine integration;
* index schemas;
* indexing workers;
* search APIs;
* hashtag discovery;
* creator discovery;
* video discovery;
* sound discovery;
* trending implementation;
* recommendation candidate architecture;
* personalization signals;
* ranking implementation;
* policy filtering;
* diversity behavior;
* freshness behavior;
* recommendation caching;
* fallback behavior;
* event consumers;
* background jobs;
* reconciliation;
* Redis changes;
* database changes;
* security controls;
* observability changes;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim machine-learning ranking was implemented unless an actual model/inference system exists.

---

# DEFINITION OF DONE

This backend discovery/recommendation milestone is complete only when:

* the repository was inspected;
* the selected search architecture is implemented;
* searchable entities have explicit index schemas;
* PostgreSQL remains authoritative for business entities;
* search text normalization is deterministic;
* search queries are bounded;
* search results use canonical pagination;
* creator search works;
* hashtag search works;
* video search works;
* sound search works where applicable;
* private content is protected;
* blocked entities are filtered;
* moderated/restricted content is filtered;
* deleted content is not exposed through search;
* asynchronous indexing is implemented;
* index updates are retry-safe;
* duplicate events do not corrupt search state;
* out-of-order updates cannot silently overwrite newer state;
* index rebuild/reconciliation is supported;
* trending discovery is implemented;
* trending calculations use bounded time windows;
* recommendation candidates have a defined model;
* candidate sources are modular;
* personalization signals are consumable;
* deterministic ranking is implemented;
* ranking configuration is centralized and testable;
* policy filtering occurs after ranking;
* diversity safeguards are implemented;
* freshness behavior is implemented;
* recommendation cache isolation is correct;
* anonymous recommendation behavior exists where supported;
* authenticated personalization is supported;
* negative-feedback signals are integrated where applicable;
* safe recommendation fallbacks exist;
* recommendation pagination is bounded and stable;
* search and recommendation APIs are implemented;
* search/recommendation background jobs are retry-safe;
* relevant event consumers are implemented;
* signal-integrity protections exist;
* reconciliation is available for important derived state;
* rate limiting is implemented;
* observability is implemented;
* sensitive information is not logged;
* search tests exist;
* recommendation tests exist;
* event/job tests exist;
* security tests exist;
* migrations are reproducible;
* machine-readable search/API artifacts validate where applicable;
* documentation reflects the actual implementation;
* no fake search engine exists;
* no hardcoded permanent recommendation feed exists;
* no fabricated ML model exists;
* no hardcoded secrets exist;
* no unrelated major subsystem was implemented;
* compatibility with notifications, moderation, analytics, clients, infrastructure, and QA is preserved;
* validation failures are accurately reported;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into the complete TikTok-style platform.
