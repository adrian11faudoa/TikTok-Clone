# TikTok-Style Short-Form Video Platform — Mobile Prompt — Volume 1

# ROLE

You are the senior **Mobile Engineering Agent** responsible for implementing the foundational production-grade mobile application for a **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Staff Mobile Engineer
* React Native Engineer
* Expo Engineer
* TypeScript Engineer
* Mobile Architect
* Mobile UI/UX Engineer
* Accessibility Engineer
* Media / Video Playback Engineer
* Networking Engineer
* Offline / Synchronization Engineer
* Mobile Security Engineer
* Performance Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the **mobile application foundation and core consumer experience** required for a production-grade iOS and Android short-form video application.

This is a bounded mobile implementation milestone.

Do not implement the complete mobile product.

Do not implement production cloud infrastructure.

Do not redesign backend contracts.

Do not invent APIs that are not supported by the repository's authoritative contracts.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator publishing;
* personalized content consumption;
* discovery;
* recommendations;
* social interaction;
* media processing;
* notifications;
* moderation;
* analytics;
* administration;
* production operations.

The completed mobile product is intended to support:

* accounts;
* profiles;
* creator identity;
* follows;
* blocks;
* video playback;
* video creation;
* media upload;
* captions;
* hashtags;
* mentions;
* sounds/audio;
* personalized feeds;
* following feeds;
* discovery;
* search;
* trending;
* recommendations;
* likes;
* comments;
* replies;
* shares;
* favorites;
* notifications;
* creator analytics;
* moderation/reporting;
* privacy controls.

This prompt implements the **mobile application foundation, authentication, core short-form video consumption, profile/social interactions, and resilient API/media foundations**.

---

# TARGET USERS

The mobile application must support:

* unauthenticated viewers where product policy permits;
* authenticated viewers;
* creators;
* users with private accounts;
* users interacting with public or authorized content.

All client-visible state must respect backend authorization.

All media and server-provided metadata must be treated as untrusted input.

---

# SCALE TARGET

The completed mobile application must remain suitable for:

* millions to hundreds of millions of users;
* high feed consumption;
* large video catalogs;
* substantial mobile playback traffic;
* frequent network interruptions;
* mobile devices ranging from lower-end to high-end hardware.

The implementation must prioritize:

* bounded memory;
* efficient media playback;
* efficient network usage;
* graceful degradation;
* offline-aware behavior where required;
* efficient rendering;
* predictable app lifecycle behavior.

Do not retain an unlimited feed or media cache in local application memory.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible and justified alternative, use:

* React Native;
* Expo where compatible with required native capabilities;
* TypeScript;
* the repository's established navigation architecture;
* the repository's established data-fetching/state-management architecture;
* secure native storage mechanisms for sensitive credentials;
* the repository's established testing stack.

Preserve compatible project choices.

Do not introduce a competing state-management, navigation, or networking architecture unnecessarily.

---

# REPOSITORY INSPECTION

Before implementation:

1. Inspect the repository.
2. Identify the mobile application package or application entry point.
3. Inspect React Native/Expo configuration.
4. Inspect navigation.
5. Inspect existing API clients and contract types.
6. Inspect authentication/session logic.
7. Inspect video/playback components.
8. Inspect shared domain models.
9. Inspect frontend/web shared packages where applicable.
10. Inspect notification configuration.
11. Inspect permissions handling.
12. Inspect tests.
13. Inspect environment configuration.
14. Identify reusable abstractions.
15. Preserve compatible implementation.
16. Avoid unnecessary rewrites.
17. Do not fabricate repository state.

The repository is authoritative for actual mobile implementation state.

This prompt is authoritative for the current mobile scope.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the mobile application foundation required for:

* application bootstrap;
* navigation;
* authentication;
* secure session persistence;
* account/profile experience;
* follow/unfollow;
* block/unblock;
* vertical short-form video feed;
* efficient playback;
* feed pagination;
* loading/error/empty states;
* like/unlike;
* comment interface foundation;
* reply interface;
* share;
* favorite/save;
* playback telemetry;
* behavioral-event batching;
* network resilience;
* app lifecycle handling;
* secure configuration;
* accessibility;
* responsive device adaptation;
* mobile performance;
* push-notification registration foundation;
* deep-link foundation;
* telemetry;
* testing;
* documentation.

Implement real mobile behavior against backend contracts.

Do not use permanently hardcoded video data as a substitute for backend integration.

---

# MOBILE APPLICATION ARCHITECTURE

Establish a maintainable mobile architecture separating:

* navigation;
* screens;
* reusable components;
* domain/application logic;
* API client;
* server state;
* local UI state;
* authentication/session state;
* media playback;
* analytics;
* device capabilities;
* error handling.

Avoid putting business rules directly inside visual components.

Avoid a single global store containing all application data.

---

# APPLICATION BOOTSTRAP

Implement application initialization.

Handle:

* configuration loading;
* secure session restoration;
* initial authentication state;
* app-level error boundaries;
* navigation readiness;
* telemetry initialization where appropriate;
* device capability detection required by this scope.

The application must distinguish:

* bootstrapping;
* authenticated;
* unauthenticated;
* session-expired;
* unrecoverable startup failure.

Do not flash authenticated screens before session restoration completes.

---

# NAVIGATION

Establish navigation suitable for:

* home/feed;
* authentication;
* profile;
* video/detail;
* comments;
* notifications entry point where applicable;
* search/discovery entry point;
* saved content entry point where applicable;
* settings.

Use route guards or navigation gating consistent with the authentication architecture.

Navigation behavior must remain safe when:

* a session expires;
* a deep link references deleted content;
* a blocked user/content becomes inaccessible;
* the network is unavailable.

---

# AUTHENTICATION

Integrate the mobile client with the backend authentication contract.

Support:

* registration;
* login;
* logout;
* session restoration;
* token/session refresh where applicable;
* authenticated-user retrieval;
* session-expiration handling.

Store sensitive credentials using secure platform facilities rather than ordinary unencrypted storage.

Do not place access tokens or refresh credentials into:

* logs;
* analytics;
* navigation parameters;
* ordinary persistent key-value storage when a secure facility is available.

---

# SECURE SESSION STORAGE

Use secure storage appropriate to iOS and Android for:

* refresh credentials;
* session secrets;
* other sensitive authentication material.

Support:

* save;
* retrieval;
* update;
* revocation;
* clearing on logout.

Do not persist credentials longer than necessary.

When the account is suspended/deleted or session renewal fails authoritatively, clear sensitive session material and route the user appropriately.

---

# AUTHENTICATION UX

Implement:

* registration screen;
* login screen;
* validation;
* loading state;
* error state;
* keyboard-safe layouts;
* password-entry behavior;
* session-expiration UX.

Use accessible labels and predictable focus behavior.

Do not expose overly specific authentication failure details when backend policy intentionally prevents account enumeration.

---

# PROFILE EXPERIENCE

Implement the mobile profile experience.

Support:

* avatar;
* username;
* display name;
* biography;
* creator identity;
* follower/following counts where provided;
* follow/unfollow;
* block/unblock;
* visible video content;
* private-profile state.

Do not render entire backend profile objects directly.

Map API responses into explicit mobile presentation models.

---

# PROFILE PRIVACY

Support correct presentation of:

* public profiles;
* private profiles;
* blocked relationships;
* restricted accounts;
* suspended accounts;
* deleted accounts.

When the backend reports that previously visible content is no longer accessible:

* remove or invalidate stale local data;
* prevent navigation into unauthorized content;
* preserve the server as authority.

---

# FOLLOW / UNFOLLOW

Implement mobile follow/unfollow behavior.

Support:

* authentication checks;
* loading state;
* safe optimistic update where appropriate;
* rollback;
* duplicate-tap prevention;
* authoritative state refresh.

Do not assume the follow succeeded permanently before backend confirmation.

---

# BLOCK / UNBLOCK

Implement mobile block/unblock controls.

After blocking:

* remove newly unauthorized content from relevant screens;
* invalidate profile/feed relationship state;
* remove blocked entities from visible lists where appropriate;
* prevent navigation to now-inaccessible content.

Blocking is enforced by the backend; the mobile client must reflect authoritative responses.

---

# SHORT-FORM VIDEO FEED

Implement the primary vertical mobile video experience.

Each active item should provide:

* video playback;
* creator identity;
* caption;
* hashtags;
* sound/audio information where available;
* like state;
* comment count;
* share;
* favorite/save;
* follow state where relevant.

The feed must consume the canonical backend feed contract.

Do not implement recommendation scoring in the mobile client.

---

# VERTICAL PAGED EXPERIENCE

Use a mobile-appropriate vertical paging model.

Support:

* one-primary-video focus;
* gesture-driven navigation;
* active-item detection;
* lifecycle-aware playback;
* lazy mounting;
* controlled preloading;
* cleanup of distant players.

Do not mount dozens of full-resolution video players simultaneously.

Use a virtualized/paginated strategy appropriate to the selected React Native implementation.

---

# VIDEO PLAYER

Implement a reusable mobile video-player component.

Support:

* autoplay for the active video;
* muted autoplay where required by platform behavior;
* play/pause;
* mute/unmute;
* buffering;
* progress;
* retry;
* poster/thumbnail;
* playback failure;
* fullscreen where appropriate;
* orientation handling where required.

The player must correctly respond to:

* screen focus;
* navigation changes;
* app backgrounding;
* incoming interruptions;
* network changes.

---

# MOBILE MEDIA PERFORMANCE

Optimize:

* first-frame startup;
* buffering;
* video-memory usage;
* player reuse;
* preloading;
* decoder pressure;
* CPU usage;
* network bandwidth;
* object lifecycle.

Avoid:

* retaining every previously played video;
* downloading unnecessarily high-quality variants;
* decoding offscreen videos;
* repeated player initialization for the same item when reuse is practical.

---

# NETWORK QUALITY ADAPTATION

Where playback APIs provide multiple media variants, select appropriate playback quality based on:

* network conditions;
* device capability;
* available bandwidth;
* current buffering state.

Do not create a complicated custom adaptive-bitrate system inside the client when the media/CDN architecture already provides one.

---

# PLAYBACK AUTHORIZATION

Consume the backend playback authorization contract.

The mobile app must not construct private media URLs manually.

Support:

* authorized playback;
* expired playback authorization;
* inaccessible video;
* deleted video;
* restricted video;
* network failure.

Do not persist long-lived signed media URLs unnecessarily.

---

# APP LIFECYCLE

Handle:

* foreground;
* background;
* inactive;
* resume;
* app termination where possible.

When the application moves to the background:

* pause unnecessary playback;
* stop unnecessary telemetry;
* flush bounded analytics events where appropriate;
* release resources.

When returning:

* restore the active state safely;
* refresh stale authorization when necessary;
* avoid blindly replaying obsolete network requests.

---

# AUDIO / INTERRUPTIONS

Handle mobile audio interruptions appropriately where supported.

Consider:

* incoming calls;
* other audio apps;
* notification sounds;
* system interruptions;
* Bluetooth/headphone state where relevant.

Do not assume continuous playback across all mobile lifecycle conditions.

---

# FEED DATA FETCHING

Use the repository's server-state architecture to implement:

* initial feed loading;
* cursor pagination;
* refresh;
* retry;
* cache;
* invalidation.

Keep feed state bounded.

Do not retain the entire user's browsing history indefinitely.

---

# FEED PAGINATION

Implement cursor-based continuation.

Support:

* initial page;
* fetching next page;
* loading indicator;
* end-of-feed;
* invalid cursor;
* retry;
* duplicate prevention.

Do not convert server cursors into offset-based client pagination.

---

# FEED CACHE

Maintain a bounded cache.

Cache policies must distinguish:

* currently visible content;
* near-future feed content;
* stale content;
* expired content.

Do not cache restricted/private content in a way that later surfaces it to unauthorized users.

Invalidate cache after important mutations such as:

* block;
* follow;
* moderation changes;
* deletion;
* visibility changes.

---

# FEED OFFLINE BEHAVIOR

Where appropriate, provide limited offline behavior such as:

* preserving the currently loaded feed state;
* showing cached content when safely authorized;
* clear offline indication.

Do not claim that arbitrary offline playback is supported unless media is explicitly available offline.

Do not allow stale cached private/restricted content to bypass current authorization.

---

# LIKE / UNLIKE

Implement:

* like;
* unlike;
* current state;
* safe optimistic update;
* rollback;
* retry behavior;
* accessibility feedback.

Prevent rapid repeated mutations from generating unnecessary requests.

---

# COMMENT UI

Implement the mobile comment interface foundation.

Support:

* comment list;
* cursor pagination;
* comment creation;
* replies;
* deletion where authorized;
* loading;
* empty state;
* failure state;
* moderation/deletion presentation.

Use bounded comment rendering.

Do not recursively render unlimited nesting.

---

# COMMENT COMPOSER

Support:

* text input;
* character limits;
* validation;
* keyboard handling;
* submit state;
* error feedback.

The backend remains authoritative for validation.

Do not retain sensitive or unsent comment content longer than necessary.

---

# SHARE

Implement mobile sharing.

Support:

* native share sheet;
* canonical public URL generation;
* fallback where the platform does not provide a share mechanism;
* backend share integration where required.

Do not include private or unauthorized media URLs in shared content.

---

# FAVORITE / SAVE

Implement:

* save;
* unsave;
* state synchronization;
* error handling;
* saved-content navigation where included.

Invalidate saved-content state when content is deleted or access changes.

---

# SEARCH ENTRY POINT

Implement the mobile entry point for search/discovery.

Support:

* query entry;
* search submission;
* loading;
* error;
* no-results;
* navigation to results where the corresponding screen is available.

Do not implement advanced search ranking in the client.

---

# NOTIFICATION ENTRY POINT

Implement the mobile notification entry point where backend support exists.

Support:

* unread indicator;
* navigation to notifications;
* loading/error states.

Do not duplicate notification business logic in the client.

---

# PUSH NOTIFICATION FOUNDATION

Implement the mobile push-notification registration foundation.

Support:

* permission flow;
* token acquisition;
* registration with backend;
* token refresh;
* logout-related deregistration where required;
* permission-denied behavior.

Request notification permission at an appropriate user-driven moment rather than blindly at application startup.

---

# DEEP LINKS

Implement a stable deep-link foundation for:

* public videos;
* creator profiles;
* hashtags/search where supported;
* notification targets.

Handle:

* authenticated routes;
* unauthenticated routes;
* deleted content;
* inaccessible content;
* malformed deep links.

Do not put sensitive authentication data into deep-link parameters.

---

# NETWORK ERROR HANDLING

Handle:

* timeout;
* no connectivity;
* server error;
* authentication expiration;
* forbidden;
* not found;
* rate limit;
* temporary dependency failure.

Provide clear recovery UX.

Do not expose raw backend diagnostics.

---

# MOBILE RETRY POLICY

Use bounded retries for transient network failures.

Do not retry:

* invalid credentials;
* validation errors;
* authorization failures;
* destructive actions indiscriminately.

Use exponential backoff where repeated attempts are appropriate.

Avoid retry storms during outages.

---

# CONNECTION STATE

Provide a centralized network/connectivity signal where supported.

Use it to:

* inform the user when offline;
* defer low-priority telemetry;
* avoid unnecessary request attempts;
* refresh stale data when connectivity returns.

Do not make connectivity state the authority for server availability.

---

# PLAYBACK TELEMETRY

Instrument:

* impression;
* playback start;
* watch progress;
* completion;
* skip;
* replay;
* like;
* comment;
* share;
* favorite;
* follow;
* negative feedback where supported.

Send only fields defined by the backend behavioral-event contract.

---

# EVENT BATCHING

Implement bounded client-side batching for high-volume playback telemetry.

Support:

* maximum event count;
* maximum payload size;
* time-based flush;
* lifecycle flush;
* bounded retry queue;
* partial failure handling.

Do not allow the analytics queue to grow without bound during prolonged offline periods.

Persist only the minimum necessary event information for retry.

---

# EVENT PRIVACY

Do not include:

* access tokens;
* refresh credentials;
* passwords;
* push tokens;
* private comments;
* private media data;
* unnecessary personal information.

Do not log complete behavioral payloads during normal application operation.

---

# LOCAL STORAGE

Use local persistence only for explicit purposes such as:

* secure credentials;
* bounded cached state;
* user preferences;
* limited pending telemetry.

Document:

* data category;
* retention;
* sensitivity;
* invalidation;
* migration.

Do not use local storage as a substitute for the backend source of truth.

---

# MOBILE SECURITY

Protect against:

* insecure credential storage;
* deep-link injection;
* unsafe URL handling;
* XSS within embedded web content where applicable;
* sensitive data exposure;
* debug logging in production;
* insecure environment configuration;
* unauthorized cached data;
* manipulated local state.

Do not assume a compromised client can enforce server-side authorization.

---

# APP CONFIGURATION

Separate:

* development;
* test;
* staging;
* production.

Do not ship secrets in the mobile bundle.

Public configuration may be bundled only when it is genuinely non-secret.

Never embed:

* backend private keys;
* database passwords;
* cloud credentials;
* provider secrets;
* administrative tokens.

---

# DEVICE PERMISSIONS

Request only permissions required by the current functionality.

Where applicable handle:

* camera;
* microphone;
* media library;
* notifications.

Permission requests must provide appropriate user-facing context.

Do not assume a permission is permanently granted.

Handle denial gracefully.

---

# ACCESSIBILITY

Implement mobile accessibility for:

* screen readers;
* accessible labels;
* logical focus order;
* adjustable text sizes where practical;
* touch-target sizing;
* dynamic content updates;
* accessible loading/error states;
* video controls;
* forms;
* dialogs;
* bottom sheets.

Do not rely on color alone to communicate state.

---

# DEVICE / SCREEN ADAPTATION

Support:

* different screen sizes;
* safe-area insets;
* orientation constraints;
* notches/cutouts;
* varying text sizes;
* different pixel densities.

Do not place critical controls beneath system UI.

---

# PERFORMANCE

Optimize:

* startup time;
* navigation;
* feed rendering;
* image decoding;
* video playback;
* memory;
* battery usage;
* network requests;
* background activity.

Avoid unnecessary React re-renders.

Use memoization only where it provides measurable benefit or prevents known rendering pressure.

---

# MEMORY MANAGEMENT

Particularly for long feed sessions:

* release offscreen media resources;
* revoke temporary object references when appropriate;
* bound cached lists;
* avoid retaining full response histories;
* remove abandoned upload/event buffers.

Monitor for memory growth during prolonged manual or automated sessions.

---

# BATTERY EFFICIENCY

Avoid:

* unnecessary background polling;
* continuous telemetry flushes;
* high-frequency timers;
* repeated network refreshes;
* unnecessary media prefetching.

Prefer event-driven or bounded periodic behavior.

---

# ERROR / EMPTY / LOADING STATES

Every major mobile flow must define:

* loading;
* empty;
* error;
* retry;
* unavailable;
* offline where applicable.

Important background state changes should be communicated accessibly.

---

# CLIENT STATE CONSISTENCY

After mutations:

* follow;
* block;
* like;
* comment;
* favorite;
* notification registration;

update or invalidate affected local state appropriately.

Do not let optimistic state survive confirmed server rejection.

---

# ANALYTICS INSTRUMENTATION ABSTRACTION

Use a centralized typed mobile analytics layer.

Do not send analytics events directly from dozens of unrelated screens/components.

The abstraction must support:

* event validation;
* batching;
* retry;
* privacy filtering;
* environment-specific enable/disable behavior.

---

# OBSERVABILITY

Track mobile operational signals such as:

* startup failure;
* route failure;
* API failure;
* authentication failure;
* feed-loading failure;
* playback failure;
* playback startup latency;
* memory pressure where available;
* push-registration failures;
* deep-link failures.

Never transmit:

* tokens;
* passwords;
* push tokens;
* private content;
* unnecessary personal data.

---

# TESTING

Create meaningful mobile tests for:

* application bootstrap;
* authentication;
* secure session restoration;
* logout;
* navigation;
* profiles;
* private-profile behavior;
* follow/unfollow;
* block/unblock;
* feed loading;
* pagination;
* video activation;
* playback states;
* like/unlike;
* comments;
* replies;
* save;
* share;
* network failures;
* offline behavior;
* push registration;
* deep links.

Tests must focus on actual user-visible behavior and contract compliance.

---

# COMPONENT TESTING

Test reusable components such as:

* video player;
* feed item;
* profile header;
* engagement controls;
* comments sheet;
* comment item;
* authentication forms;
* navigation;
* loading/error states;
* report/share controls where applicable.

Avoid brittle implementation-detail assertions.

---

# INTEGRATION TESTING

Test integrated flows for:

* authentication/session restoration;
* feed retrieval;
* authorized playback;
* follow/unfollow;
* block/unblock;
* liking;
* commenting;
* saving;
* push registration;
* deep-link routing;
* network-recovery behavior.

Use real backend contracts or controlled integrated test infrastructure where available.

---

# END-TO-END TESTING

Where mobile E2E infrastructure exists, validate critical user flows on representative iOS/Android targets.

At minimum consider:

* launch;
* login;
* feed;
* vertical navigation;
* video playback;
* like;
* comment;
* profile;
* follow;
* block;
* share;
* save;
* logout.

Do not claim device-level E2E validation unless the tests actually ran.

---

# ACCESSIBILITY TESTING

Run appropriate accessibility validation for:

* authentication;
* feed controls;
* video controls;
* profile;
* comments;
* dialogs;
* bottom sheets;
* settings.

Manually inspect important screen-reader and dynamic-content flows where automated tooling cannot provide complete assurance.

---

# SECURITY TESTING

Test:

* secure credential storage boundaries;
* logout clearing;
* token leakage prevention;
* deep-link injection;
* unauthorized route behavior;
* private profile leakage;
* restricted video leakage;
* stale cache leakage;
* push-token exposure;
* unsafe URL handling.

Do not rely on client-side permission checks as proof of authorization security.

---

# PERFORMANCE VALIDATION

Where tooling permits, validate:

* app startup;
* navigation performance;
* prolonged feed scrolling;
* active-player switching;
* memory usage;
* media startup;
* network request volume;
* event batching.

Test long-session behavior rather than only first-launch behavior.

Do not claim production-device performance from a single development machine.

---

# DOCUMENTATION

Update repository documentation describing:

* mobile application structure;
* navigation;
* authentication/session storage;
* API integration;
* feed architecture;
* playback architecture;
* offline/network behavior;
* telemetry;
* push notification registration;
* deep links;
* required permissions;
* environment configuration;
* testing;
* accessibility;
* release/build assumptions where relevant.

Documentation must reflect actual implementation.

Do not document unsupported offline playback or device capabilities as completed functionality.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* mobile application bootstrap;
* navigation foundation;
* authentication;
* secure session storage;
* registration/login/logout UX;
* profile experience;
* creator profile presentation;
* follow/unfollow;
* block/unblock;
* vertical short-form feed;
* feed pagination;
* video playback;
* playback authorization integration;
* playback lifecycle management;
* network-quality-aware playback behavior where supported;
* like/unlike;
* comment UI foundation;
* replies;
* share;
* favorite/save;
* search entry point;
* notification entry point;
* push-notification registration foundation;
* deep-link foundation;
* connectivity handling;
* bounded offline behavior;
* playback telemetry;
* analytics batching;
* local-state management;
* device-permission handling;
* mobile accessibility;
* responsive device adaptation;
* performance and memory management;
* mobile observability;
* unit/component tests;
* integration tests;
* applicable E2E tests;
* accessibility tests;
* security tests;
* documentation.

This prompt does **not** implement:

* the complete creator publishing studio;
* camera/video recording;
* advanced video editing;
* complete media upload workflow;
* full search/discovery results;
* complete recommendation UI;
* complete notifications center;
* complete creator analytics;
* complete moderation/reporting UI;
* administration;
* production cloud infrastructure;
* backend implementation;
* advanced offline media downloading;
* live streaming;
* direct messaging;
* advertising;
* monetization;
* unrelated product categories.

Create only the mobile integration points required for later planned mobile implementation work.

---

# CROSS-PART COMPATIBILITY

Preserve compatibility with:

* account/authentication backend;
* profiles;
* privacy;
* social graph;
* blocking;
* videos;
* media/playback;
* engagement;
* feeds;
* search/discovery;
* recommendations;
* notifications;
* moderation;
* analytics;
* infrastructure;
* web;
* QA.

Use the canonical project:

* identifiers;
* timestamps;
* API error contract;
* pagination;
* authentication semantics;
* authorization semantics;
* video lifecycle;
* visibility states;
* moderation states;
* playback authorization;
* behavioral-event schema.

Do not create mobile-specific interpretations that contradict backend contracts.

---

# API INTEGRATION DISCIPLINE

Use a centralized typed mobile API client.

Centralize:

* authentication;
* session refresh;
* request cancellation;
* timeout behavior;
* canonical error mapping;
* request/correlation identifiers where applicable;
* response parsing;
* bounded retry policies.

Do not scatter raw network calls throughout screens and components.

Do not treat locally cached data as more authoritative than server responses.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* backend APIs;
* media/CDN access;
* push-notification configuration;
* device permissions;
* development/test services.

Use available development/test infrastructure.

If a service is unavailable:

* implement against the canonical repository contracts;
* use appropriate isolated tests;
* report unavailable live dependencies;
* do not fabricate successful playback, API calls, push delivery, or deep-link verification.

---

# VALIDATION

After implementation:

1. Run formatting.
2. Run linting.
3. Run TypeScript type checking.
4. Run unit tests.
5. Run component tests.
6. Run integration tests.
7. Run mobile E2E tests where infrastructure is available.
8. Run accessibility validation.
9. Run security-focused tests.
10. Validate authentication/session persistence.
11. Validate navigation and protected routes.
12. Validate feed cursor behavior.
13. Validate active-player lifecycle.
14. Validate playback failure/recovery.
15. Validate offline/reconnect behavior.
16. Validate analytics batching bounds.
17. Validate push registration behavior where testable.
18. Validate deep-link handling where testable.
19. Inspect runtime errors in representative flows.
20. Inspect the final diff.
21. Search for secrets or credentials.
22. Verify no unrelated mobile subsystem was implemented.

Do not claim physical-device or provider validation unless it actually occurred.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* mobile application structure;
* navigation;
* authentication;
* secure storage;
* profile experience;
* follow/unfollow;
* block/unblock;
* feed;
* video playback;
* playback authorization;
* comments/replies;
* likes;
* shares;
* favorites;
* API client;
* connectivity handling;
* offline behavior;
* playback telemetry;
* analytics batching;
* push registration;
* deep links;
* device permissions;
* accessibility changes;
* performance changes;
* memory/battery work;
* observability;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim device/provider behavior was validated unless it was actually tested.

---

# DEFINITION OF DONE

This mobile foundation milestone is complete only when:

* the repository was inspected;
* the mobile application bootstrap is implemented;
* navigation is implemented;
* authentication UX is implemented;
* secure session storage is implemented;
* logout clears sensitive credentials appropriately;
* session restoration works;
* protected navigation behaves correctly;
* profiles render authoritative data;
* private profiles are handled correctly;
* follow/unfollow works;
* block/unblock works;
* blocked content is removed from relevant client state;
* the vertical short-form feed works;
* cursor pagination works;
* feed state remains bounded;
* the active video is correctly managed;
* inactive players are paused or released appropriately;
* video playback handles loading, buffering, failure, and retry;
* playback authorization uses the backend contract;
* deleted/restricted content is not exposed through stale local state;
* like/unlike works;
* comments and replies work within the defined backend model;
* share works through the native platform sharing mechanism where supported;
* save/favorite works;
* search entry exists;
* notification entry exists;
* push registration foundation exists;
* deep-link handling exists;
* connectivity state is handled;
* bounded offline behavior exists where appropriate;
* playback telemetry is implemented;
* telemetry batching is bounded;
* sensitive telemetry fields are excluded;
* device permissions are handled safely;
* accessibility requirements are implemented;
* screen-size/safe-area handling works;
* memory usage is bounded during prolonged feed sessions;
* battery-intensive behavior is controlled;
* API errors are handled consistently;
* client state synchronizes after mutations;
* observability is implemented;
* security protections are implemented;
* unit/component tests exist;
* integration tests exist;
* applicable E2E tests exist;
* accessibility tests exist;
* security tests exist;
* TypeScript validation passes;
* linting/formatting passes where configured;
* documentation reflects the actual implementation;
* no fake feed data substitutes for backend behavior;
* no hardcoded secrets exist;
* no unsupported offline-media behavior is claimed;
* no unrelated mobile subsystem was implemented;
* compatibility with backend, web, infrastructure, search, recommendation, notifications, moderation, analytics, and QA is preserved;
* unavailable external dependencies are reported accurately;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into the complete mobile creator application or unrelated product functionality.
