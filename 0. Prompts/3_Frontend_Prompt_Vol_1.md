# TikTok-Style Short-Form Video Platform — Frontend Prompt — Volume 1

# ROLE

You are the senior **Frontend Engineering Agent** responsible for implementing the foundational web application for a production-grade **TikTok-style short-form video platform**.

Operate with the combined standards of:

* Staff Frontend Engineer
* Frontend Architect
* React / Next.js Engineer
* TypeScript Engineer
* UI/UX Engineer
* Accessibility Engineer
* Performance Engineer
* Security Engineer
* State-Management Engineer
* API Integration Engineer
* Realtime Client Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the production-grade web application foundation and the primary authenticated/public user experiences within the bounded scope defined below.

This is a frontend implementation milestone.

Do not implement the complete mobile application.

Do not provision production infrastructure.

Do not redesign backend contracts.

Do not invent incompatible APIs.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator participation;
* personalized video consumption;
* video publishing;
* discovery;
* social interaction;
* recommendations;
* notifications;
* moderation;
* analytics;
* administration;
* production operations.

The completed product is intended to support:

* accounts;
* profiles;
* creator identity;
* follows;
* blocks;
* video publishing;
* media playback;
* personalized feeds;
* following feeds;
* discovery;
* trending;
* search;
* recommendations;
* likes;
* comments;
* replies;
* shares;
* favorites;
* views;
* notifications;
* moderation;
* reporting;
* administration;
* creator analytics.

This prompt implements the **web application foundation and core viewer/account/social experiences** required for later frontend milestones.

---

# TARGET USERS

The web application must support:

* unauthenticated visitors where product policy permits;
* authenticated viewers;
* creators;
* users with private accounts;
* users interacting with public or authorized content.

Administrative and moderation applications may exist as separate experiences later, but this prompt establishes only the frontend foundation and current user-facing scope explicitly defined here.

---

# SCALE TARGET

The completed web application must remain suitable for a platform with:

* millions to hundreds of millions of users;
* high concurrent feed usage;
* heavy short-form video playback;
* large creator populations;
* high engagement rates;
* bursts of viral traffic.

The frontend must therefore prioritize:

* efficient rendering;
* bounded client state;
* media-performance discipline;
* efficient network usage;
* cache-aware data fetching;
* predictable state transitions;
* resilient error handling.

Do not preload an unlimited amount of feed content.

---

# TECHNOLOGY DIRECTION

Unless the repository already establishes a compatible and justified alternative, use:

* Next.js;
* React;
* TypeScript;
* the repository's established routing strategy;
* the repository's established server/client data-fetching architecture;
* a strongly typed API client layer;
* accessible component primitives;
* the project's established testing stack.

Preserve compatible repository choices.

Do not add a competing state-management or data-fetching architecture merely because multiple libraries are available.

---

# REPOSITORY INSPECTION

Before implementation:

1. Inspect the repository.
2. Identify the existing web application.
3. Inspect package structure.
4. Inspect Next.js configuration.
5. Inspect routing.
6. Inspect global styles and design-system components.
7. Inspect API client code.
8. Inspect authentication/session handling.
9. Inspect current domain types.
10. Inspect existing video/player components.
11. Inspect tests.
12. Inspect environment configuration.
13. Identify reusable components.
14. Preserve compatible implementations.
15. Avoid unnecessary rewrites.
16. Do not fabricate existing repository state.

The repository is authoritative for actual frontend implementation state.

This prompt is authoritative for the current frontend scope.

Do not rely on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the frontend foundation required for:

* application shell;
* routing;
* authentication-aware navigation;
* account/session handling;
* profile pages;
* creator profile presentation;
* feed shell;
* vertical short-form video browsing;
* video playback;
* engagement controls;
* follow/unfollow UI;
* blocking controls where appropriate;
* comments UI foundation;
* share interactions;
* favorite/save interactions;
* loading and error states;
* responsive behavior;
* accessibility;
* API integration;
* client-side validation;
* state synchronization;
* analytics instrumentation boundaries;
* frontend testing;
* frontend observability;
* documentation.

Implement real UI and real API integration.

Do not use hardcoded production-like feed data as a substitute for API integration.

---

# APPLICATION ARCHITECTURE

Establish or refine a maintainable web architecture with clear separation between:

* route/application shell;
* UI components;
* domain components;
* API client;
* server-state management;
* local UI state;
* authentication state;
* media playback state;
* analytics instrumentation;
* error handling;
* shared types/contracts.

Do not put business rules into reusable visual components when those rules belong to domain/application layers.

Avoid excessive client-side state duplication.

---

# ROUTING

Implement routes required for this frontend milestone.

At minimum establish appropriate routes for:

* home/feed;
* authentication;
* user profile;
* creator profile;
* individual video where a standalone route is appropriate;
* saved/favorited content where included;
* notifications where included in this scope;
* account/settings pages required by the current scope.

Use protected-route or server-side access patterns appropriate to the authentication model.

Do not rely exclusively on client-side redirects for authorization.

---

# APPLICATION SHELL

Implement the core application shell.

Support:

* responsive navigation;
* desktop layout;
* mobile-web layout;
* authenticated vs unauthenticated navigation;
* profile access;
* discovery/search entry points;
* notification access where applicable;
* creator actions where authorized.

The shell must remain usable on:

* desktop;
* tablet;
* mobile browsers.

Do not make the desktop layout merely a horizontally shrunk mobile interface.

---

# DESIGN SYSTEM FOUNDATION

Create or extend reusable components for:

* buttons;
* icon buttons;
* avatars;
* video cards;
* profile headers;
* tabs;
* menus;
* dialogs;
* drawers;
* form controls;
* loading indicators;
* error states;
* empty states;
* toasts/feedback;
* pagination/continuation controls where applicable.

Use accessible semantic elements.

Do not create visually identical components with unrelated implementations.

---

# ACCESSIBILITY

Meet appropriate accessibility standards for the web interface.

Implement:

* semantic HTML;
* keyboard navigation;
* visible focus behavior;
* accessible labels;
* screen-reader-friendly controls;
* appropriate dialog focus management;
* sufficient contrast;
* reduced-motion considerations;
* accessible error messages;
* captions/accessible media controls where applicable.

Do not rely on icons alone for important actions.

Do not make the video interface inaccessible to keyboard or assistive-technology users.

---

# AUTHENTICATION CLIENT

Integrate the web client with the project's backend authentication contract.

Support:

* registration;
* login;
* logout;
* session restoration;
* refresh behavior where applicable;
* authenticated-user retrieval;
* expired-session handling.

Do not store sensitive tokens in insecure browser locations when the backend authentication architecture supports secure cookies or another safer mechanism.

The frontend must not decide authorization independently.

---

# AUTHENTICATION UX

Implement:

* loading state during session restoration;
* clear authentication errors;
* validation errors;
* session-expiration handling;
* protected-route behavior;
* accessible forms;
* password-field handling appropriate to the authentication model.

Avoid leaking whether an account exists through unnecessarily specific error messaging where backend policy intentionally prevents enumeration.

---

# PROFILE EXPERIENCE

Implement public and authenticated profile experiences.

Support:

* avatar;
* username/handle;
* display name;
* biography;
* creator identity;
* follower count where provided;
* following count where provided;
* follow/unfollow;
* block/unblock where authorized;
* visible video grid/list;
* private-account state.

Do not expose backend-private fields accidentally through broad object rendering.

Map API responses into explicit frontend view models.

---

# PROFILE PRIVACY

Profile UI must correctly represent:

* public profile;
* private profile;
* blocked relationship;
* restricted account;
* suspended/deleted account.

Do not allow cached public profile data to remain visible after access becomes unauthorized when the API indicates otherwise.

Client state must be invalidated when important authorization/visibility changes occur.

---

# FOLLOW / UNFOLLOW UI

Implement follow/unfollow interaction.

Support:

* authenticated-state checks;
* loading state;
* optimistic UI only where safe;
* rollback after mutation failure;
* duplicate-click prevention;
* updated follower counts where supported.

Do not allow the client to permanently assume a follow succeeded before the backend confirms the authoritative state.

---

# BLOCK / UNBLOCK UI

Implement block/unblock interactions appropriate to user-facing web flows.

Clearly communicate the effect to the current user.

After blocking:

* remove newly unauthorized content from visible UI state;
* invalidate affected profile/feed queries;
* invalidate relationship state;
* avoid retaining cached content that should no longer be shown.

Blocking remains a backend authorization rule; the frontend only reflects authoritative results.

---

# VIDEO FEED EXPERIENCE

Implement the primary vertical short-form video browsing experience.

The feed should provide:

* vertically oriented video presentation;
* one-primary-item viewing focus;
* creator information;
* caption;
* hashtags;
* sound/audio information where provided;
* like state;
* comment count;
* share action;
* favorite/save action;
* follow state where applicable;
* playback controls;
* loading state;
* error state.

The UI must consume the backend feed contract.

Do not invent ranking fields or recommendation metadata not present in the API contract.

---

# VERTICAL SCROLLING MODEL

Implement an interaction model suitable for short-form video browsing.

Support:

* active-video detection;
* controlled transitions between videos;
* lazy rendering;
* preloading of near-future media where justified;
* pause for inactive videos;
* viewport-aware playback.

Do not mount an unbounded number of video elements simultaneously.

Use virtualization or another bounded rendering approach appropriate to the selected architecture.

---

# VIDEO PLAYER

Implement a reusable production-oriented video-player component.

Support:

* autoplay behavior subject to browser policy;
* mute/unmute;
* play/pause;
* progress where appropriate;
* loading;
* buffering;
* playback failure;
* retry;
* poster/thumbnail;
* responsive sizing;
* fullscreen where appropriate.

Respect browser autoplay restrictions.

Do not assume autoplay with audio will always succeed.

---

# MEDIA PERFORMANCE

The video experience is a critical path.

Optimize for:

* first-frame startup;
* efficient buffering;
* limited unnecessary downloads;
* appropriate resolution selection;
* viewport awareness;
* avoiding duplicate network requests;
* efficient cleanup;
* memory management.

Do not eagerly preload the entire feed.

Do not download high-resolution media for offscreen items without a justified reason.

---

# PLAYBACK AUTHORIZATION

Consume backend playback authorization correctly.

The frontend must not construct private media URLs manually.

Use the server-provided authorized playback representation.

Handle:

* expired playback authorization;
* unavailable media;
* deleted content;
* restricted content;
* network failures.

Do not store long-lived signed media URLs unnecessarily.

---

# VIDEO ERROR STATES

Handle:

* unsupported media;
* authorization failure;
* deleted video;
* restricted video;
* CDN/media failure;
* timeout;
* network interruption;
* processing failure.

Provide recovery behavior where safe.

Do not silently display stale metadata as though playback succeeded.

---

# VIDEO METADATA DISPLAY

Render:

* creator identity;
* caption;
* hashtags;
* sound information;
* engagement summaries;
* publication information where appropriate.

Protect against unsafe text rendering.

React-rendered user content must remain safely encoded.

Do not inject raw HTML from user-controlled metadata.

---

# LIKE / UNLIKE UI

Implement:

* like;
* unlike;
* authoritative state synchronization;
* optimistic updates only where safe;
* rollback;
* disabled/loading state;
* accessible labels.

Use the API as the authority.

Prevent double-submission.

Do not increment counters indefinitely because of repeated client retries.

---

# COMMENTS UI

Implement the frontend comment experience.

Support:

* comment list;
* cursor pagination;
* comment creation;
* replies;
* deletion where authorized;
* loading;
* error;
* empty state;
* moderation/deletion presentation.

Do not render unlimited reply depth.

Follow the backend's defined comment-depth model.

---

# COMMENT INPUT

Provide:

* text validation;
* character limits from the backend contract;
* submit state;
* error feedback;
* keyboard behavior;
* accessible labels.

Do not rely exclusively on client-side validation.

Backend validation remains authoritative.

---

# SHARE EXPERIENCE

Implement the web share interaction appropriate to the browser.

Support:

* native Web Share API where available;
* copy-link fallback;
* accessible confirmation;
* backend share event/record integration where required.

Do not expose private media URLs when generating share destinations.

Use canonical public URLs.

---

# FAVORITE / SAVE EXPERIENCE

Implement:

* save;
* unsave;
* state synchronization;
* loading state;
* confirmation/error feedback;
* saved-content retrieval where included.

After deletion or access changes, invalidate affected saved-item state.

---

# FEED DATA FETCHING

Use an appropriate server-state/data-fetching strategy.

Requirements:

* cache reusable responses;
* deduplicate requests;
* avoid unnecessary refetches;
* support cursor continuation;
* recover from network failures;
* invalidate data following mutations;
* avoid retaining unlimited feed history in memory.

Separate:

* authoritative API state;
* temporary UI state;
* playback state;
* optimistic state.

---

# FEED PAGINATION

Implement the backend's cursor-based feed contract.

Support:

* initial page;
* continuation;
* loading more;
* end of feed;
* invalid cursor;
* retry;
* duplicate prevention.

Do not replace cursor pagination with browser-side offset calculations.

---

# FEED STATE CONSISTENCY

When:

* liking;
* commenting;
* following;
* blocking;
* favoriting;
* deleting/losing access to content;

update or invalidate affected feed state appropriately.

Do not mutate unrelated cached records indiscriminately.

---

# DISCOVERY ENTRY POINT

Implement the web experience necessary to enter discovery/search.

At minimum provide:

* search field;
* query submission;
* loading state;
* no-results state;
* error state;
* result navigation.

Do not implement the complete search-results experience unless it belongs to this milestone's explicit scope beyond this foundation.

Create reusable navigation and search-entry components for a later dedicated discovery milestone.

---

# NOTIFICATION ENTRY POINT

Where notification APIs are already available in the repository, implement the foundational notification UI access point:

* notification indicator;
* unread count;
* navigation to notification view;
* loading/error state.

Do not build the complete notification center if that experience belongs to a later frontend milestone.

---

# ACCOUNT SETTINGS ENTRY POINT

Provide the foundational settings entry points needed for:

* privacy;
* account/session controls;
* logout;
* blocking access;
* notification preference access where available.

Do not build administrative settings as ordinary user settings.

---

# ERROR HANDLING

Create a consistent frontend error strategy.

Handle:

* validation errors;
* authentication errors;
* authorization errors;
* not found;
* conflict;
* rate limit;
* transient failure;
* network outage;
* media failure.

Map canonical backend errors into accessible frontend messages.

Do not expose raw API error payloads or internal server diagnostics.

---

# LOADING / EMPTY STATES

Every major asynchronous user experience must define:

* loading state;
* empty state;
* retry/error state;
* disabled state where mutations are in progress.

Do not show blank screens while requests are pending.

Do not use spinners indefinitely without a timeout/recovery strategy where appropriate.

---

# OPTIMISTIC UPDATES

Use optimistic updates only for interactions where rollback is safe.

Suitable examples may include:

* like;
* unlike;
* favorite;
* unfavorite;
* follow;
* unfollow.

After server failure:

* revert the optimistic state;
* show an appropriate error;
* refetch authoritative state if necessary.

Do not optimistically finalize irreversible actions.

---

# CLIENT-SIDE VALIDATION

Validate forms locally for fast user feedback.

Examples:

* username;
* caption;
* comment;
* account settings.

Client validation must mirror backend constraints where practical but must not replace backend validation.

Avoid duplicating complex server business rules unnecessarily.

---

# CLIENT SECURITY

Protect against:

* XSS;
* unsafe HTML rendering;
* token leakage;
* sensitive-data persistence;
* insecure URL handling;
* malicious navigation;
* untrusted media metadata.

Never:

* render arbitrary HTML from user content without sanitization;
* expose access tokens through logs;
* expose secrets through client bundles;
* place backend secrets in public environment variables;
* trust query parameters as authorization.

---

# ANALYTICS INSTRUMENTATION

Create a frontend analytics abstraction for product events such as:

* feed impression;
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
* search interaction.

Do not send raw analytics events directly throughout UI components.

Use a centralized typed instrumentation layer.

The backend remains the authority for event acceptance and validation.

---

# PLAYBACK TELEMETRY

Instrument playback events carefully.

Capture only data required by the backend contract.

Consider:

* video ID;
* event type;
* playback position;
* duration;
* session;
* client platform;
* timestamp.

Do not include:

* authentication tokens;
* unnecessary private user data;
* raw private content.

Use bounded event batching where the backend supports it.

---

# EVENT BATCHING

Where supported by the API, batch high-volume playback events.

Implement:

* bounded batch size;
* bounded payload size;
* retry behavior;
* partial-failure handling;
* flush behavior;
* lifecycle handling.

Prevent an event queue from growing without bound in browser memory.

Flush appropriately when:

* the page becomes hidden;
* navigation occurs;
* session ends;
* a timer threshold is reached;
* batch size is reached.

---

# CLIENT RETRY POLICY

Use bounded retries for transient network failures.

Do not blindly retry:

* authentication failures;
* validation failures;
* authorization failures;
* irreversible mutations.

Use exponential backoff where repeated retries are appropriate.

Avoid retry storms during service outages.

---

# REALTIME CLIENT FOUNDATION

Where realtime notification or social updates are required by the current repository contract, create a reusable realtime client abstraction.

Support:

* authentication;
* connect;
* disconnect;
* reconnect;
* heartbeat;
* subscription;
* event parsing;
* duplicate handling;
* cleanup.

The realtime layer must not be the only source of state.

After reconnect, synchronize authoritative state through APIs where required.

---

# CACHE INVALIDATION

Invalidate client/server-state caches when relevant mutations succeed.

Examples:

* follow/unfollow → profile relationship and feed-related queries;
* block/unblock → profile, feed, search/discovery caches;
* like/unlike → affected video engagement state;
* favorite → affected video and saved-content queries;
* comment → comment list and count.

Avoid global cache invalidation.

---

# ROUTE AUTHORIZATION

Protect routes based on authentication requirements.

Examples:

* profile settings;
* saved content;
* notification center;
* authenticated feed features.

The frontend may prevent navigation for UX purposes, but backend authorization remains authoritative.

---

# RESPONSIVE DESIGN

The web experience must support:

* desktop;
* tablet;
* mobile browser.

The short-form video experience should preserve the primary media-first interaction on smaller screens without sacrificing functionality.

Do not create layout breakage when:

* captions become long;
* usernames are long;
* comments contain long text;
* media dimensions vary;
* browser viewport changes.

---

# ACCESSIBILITY WITH VIDEO

Ensure:

* keyboard access to controls;
* accessible mute/play controls;
* meaningful focus order;
* captions/subtitle support where media provides them;
* non-audio-dependent understanding of controls;
* reduced-motion handling;
* focus preservation during feed transitions.

Do not rely on autoplay as the only way a user can access the video.

---

# PERFORMANCE

Optimize:

* initial JavaScript payload;
* code splitting;
* route-level loading;
* image optimization;
* video startup;
* component rendering;
* unnecessary re-renders;
* API request duplication;
* memory usage.

Use lazy loading for noncritical features.

Avoid creating a large global client state containing the entire content feed.

---

# SEO AND SHARING

Where public profiles or public videos have standalone web routes, establish appropriate:

* metadata;
* canonical URLs;
* Open Graph metadata;
* share previews;
* structured page titles.

Do not expose private content through public metadata.

Public SEO behavior must respect account/video visibility.

---

# BROWSER COMPATIBILITY

Use progressive enhancement for browser capabilities such as:

* native Web Share;
* autoplay;
* fullscreen.

Provide usable fallbacks.

Do not require one browser-specific API for the core application experience.

---

# OBSERVABILITY

Add frontend telemetry appropriate to:

* route performance;
* API failure rates;
* video startup;
* playback failure;
* feed-loading latency;
* client errors;
* failed mutations;
* authentication failures.

Do not capture sensitive form contents.

Do not transmit raw access tokens or private account information to analytics systems.

---

# TESTING

Create meaningful frontend tests for:

* routing;
* authentication state;
* profile rendering;
* private-profile behavior;
* follow/unfollow;
* block/unblock;
* feed loading;
* feed pagination;
* video activation;
* playback states;
* like/unlike;
* comments;
* favorites;
* share fallback;
* loading/error/empty states;
* API error mapping.

Tests must focus on user-visible behavior and contract correctness.

---

# COMPONENT TESTING

Test reusable components including:

* video player;
* video card/feed item;
* profile header;
* engagement controls;
* comment composer;
* comment list;
* navigation;
* dialogs;
* error boundaries;
* loading states.

Do not create brittle tests tied only to implementation details.

---

# END-TO-END TESTING

Where the repository supports E2E testing, cover critical flows such as:

* registration/login;
* session restoration;
* profile navigation;
* follow;
* block;
* opening feed;
* playing a video;
* liking;
* commenting;
* saving;
* sharing;
* logout.

Use real backend contracts or appropriate integrated test infrastructure.

Do not claim end-to-end coverage if only component mocks were executed.

---

# ACCESSIBILITY TESTING

Run appropriate automated accessibility checks.

Validate:

* labels;
* roles;
* focus order;
* keyboard interaction;
* dialog behavior;
* form errors;
* contrast where tooling supports it.

Also manually inspect critical interaction paths where automated tooling cannot fully evaluate them.

---

# PERFORMANCE VALIDATION

Where tooling exists, validate:

* initial route loading;
* feed rendering;
* video-player mount/unmount behavior;
* unnecessary component re-renders;
* client memory growth during prolonged feed use;
* request duplication.

Do not claim real-world production-scale browser performance from a local benchmark alone.

---

# SECURITY TESTING

Test:

* XSS-resistant user content rendering;
* unsafe URL handling;
* unauthorized route access;
* token exposure;
* insecure environment-variable usage;
* private-profile leakage;
* private-video metadata leakage;
* stale cached restricted content;
* malicious query/navigation parameters.

Do not place secrets in client-exposed configuration.

---

# DOCUMENTATION

Update repository documentation describing:

* web application structure;
* routing;
* authentication integration;
* API client;
* state-management strategy;
* video-player architecture;
* feed data flow;
* analytics instrumentation;
* realtime client foundation where applicable;
* environment variables;
* local development;
* testing;
* accessibility expectations;
* browser compatibility.

Documentation must describe the actual implementation.

Do not document future screens as already implemented.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* web application foundation;
* application shell;
* routing foundation;
* authentication UX;
* session-aware navigation;
* profile pages;
* creator profile presentation;
* follow/unfollow UI;
* block/unblock UI;
* core vertical video feed experience;
* reusable video player;
* playback authorization integration;
* video metadata presentation;
* like/unlike UI;
* comment UI foundation;
* replies;
* share interaction;
* favorite/save interaction;
* feed cursor pagination;
* feed state management;
* discovery/search entry point;
* notification entry point where applicable;
* settings entry point;
* loading/error/empty states;
* responsive design;
* accessibility foundation;
* frontend analytics abstraction;
* playback telemetry;
* event batching;
* realtime client foundation where required;
* cache invalidation;
* frontend observability;
* unit/component tests;
* applicable E2E tests;
* accessibility tests;
* security tests;
* documentation.

This prompt does **not** implement:

* the complete creator publishing UI;
* the complete video-upload editing studio;
* advanced discovery/search results;
* complete personalized recommendation UI;
* complete notifications center;
* complete moderation UI;
* complete administration UI;
* complete creator analytics dashboard;
* the mobile application;
* production infrastructure;
* backend API redesign;
* backend recommendation-model implementation;
* backend search-engine implementation.

Create only the frontend integration points needed for later milestones to add those capabilities cleanly.

---

# CROSS-PART COMPATIBILITY

Preserve compatibility with:

* account/authentication backend;
* profiles;
* social graph;
* blocking;
* video/content;
* media/playback;
* engagement;
* feeds;
* search/discovery;
* recommendation;
* notifications;
* moderation;
* analytics;
* infrastructure;
* mobile;
* QA.

Use the canonical project:

* identifiers;
* timestamps;
* API error structure;
* pagination;
* authentication semantics;
* authorization semantics;
* visibility states;
* moderation states;
* media/playback contract.

Do not create frontend-specific interpretations that contradict backend contracts.

---

# API INTEGRATION DISCIPLINE

Create a typed API integration boundary.

Centralize:

* request construction;
* authentication handling;
* response parsing;
* canonical error mapping;
* request IDs/correlation where required;
* retry policy;
* timeout handling.

Do not scatter raw `fetch` calls with ad hoc headers and response parsing throughout the UI.

Do not duplicate backend schemas manually in unrelated components when shared/generated contract types are available.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* backend API availability;
* development database;
* media/CDN access;
* authentication configuration.

Use available development/test infrastructure.

If the backend or external media system is unavailable:

* implement the frontend against the canonical contracts available in the repository;
* run tests using appropriate isolated fixtures or test servers;
* report unavailable dependencies accurately;
* do not fabricate successful live API or CDN validation.

---

# VALIDATION

After implementation:

1. Run formatting.
2. Run linting.
3. Run TypeScript type checking.
4. Run unit tests.
5. Run component tests.
6. Run relevant integration tests.
7. Run E2E tests where infrastructure is available.
8. Run accessibility validation.
9. Run security-focused frontend tests.
10. Validate route behavior.
11. Validate API-client contract handling.
12. Validate feed cursor behavior.
13. Validate video-player lifecycle.
14. Validate playback failure/recovery behavior.
15. Validate event batching bounds.
16. Inspect browser-console errors in relevant test flows.
17. Inspect final diff.
18. Search for exposed secrets.
19. Verify that no unrelated major frontend subsystem was implemented.

Do not claim live backend/CDN validation if those dependencies were unavailable.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* frontend application structure;
* routes;
* design-system components;
* authentication integration;
* profile implementation;
* follow/block implementation;
* feed implementation;
* video-player implementation;
* playback integration;
* engagement UI;
* comments;
* sharing;
* favorites;
* discovery entry point;
* notification entry point;
* API client changes;
* client-state/data-fetching changes;
* analytics instrumentation;
* playback telemetry;
* realtime changes;
* accessibility changes;
* performance improvements;
* observability changes;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim live service validation unless it was actually performed.

---

# DEFINITION OF DONE

This frontend milestone is complete only when:

* the repository was inspected;
* the web application architecture is coherent;
* the application shell is implemented;
* routing is implemented;
* authentication UX is implemented;
* session restoration works;
* protected routes behave correctly;
* profiles render authoritative API data;
* private profiles are handled correctly;
* follow/unfollow works;
* block/unblock works;
* the core vertical video feed works;
* feed cursor pagination works;
* feed rendering is bounded;
* the active video is correctly managed;
* offscreen media does not consume unlimited resources;
* the reusable video player handles loading, playback, buffering, and failures;
* playback authorization uses backend-provided authorization;
* private/restricted/deleted content is not exposed through stale client state;
* captions, hashtags, sounds, and creator information render safely;
* like/unlike works;
* comments and replies work within the defined backend model;
* comments have validation and error handling;
* sharing works with browser fallbacks;
* favorites/save works;
* discovery/search entry is implemented;
* notification access point exists where applicable;
* settings access exists;
* loading states exist;
* empty states exist;
* error states exist;
* optimistic updates are safe and reversible;
* canonical backend errors are mapped correctly;
* user-generated text is rendered safely;
* no client secrets are exposed;
* accessibility requirements are implemented;
* responsive layouts function across target viewport classes;
* video performance is handled deliberately;
* frontend analytics instrumentation is centralized;
* playback telemetry is bounded and contract-compliant;
* realtime client behavior is resilient where required;
* cache invalidation is correct;
* observability is implemented;
* unit/component tests exist;
* applicable integration/E2E tests exist;
* accessibility tests exist;
* security tests exist;
* TypeScript validation passes;
* linting/formatting passes where configured;
* documentation reflects actual implementation;
* no fake feed data substitutes for required API behavior;
* no hardcoded secrets exist;
* no unrelated major frontend subsystem was implemented;
* compatibility with backend, mobile, infrastructure, moderation, recommendation, search, analytics, and QA is preserved;
* validation failures are reported accurately;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into the complete web application.
