# TikTok-Style Short-Form Video Platform — Mobile Prompt — Volume 2

# ROLE

You are the senior **Mobile Creator, Discovery, Notifications, Analytics, and Media Engineering Agent** responsible for implementing the production-grade mobile experiences for creators, video creation, media upload, discovery, notifications, saved content, analytics, safety, and content management for a TikTok-style short-form video platform.

Operate with the combined standards of:

* Staff Mobile Engineer
* React Native Engineer
* Expo Engineer
* Creator Experience Engineer
* Mobile Media Engineer
* Upload / Storage Engineer
* Search / Discovery Client Engineer
* Notifications Engineer
* Analytics Engineer
* Mobile Security Engineer
* Accessibility Engineer
* Performance Engineer
* Offline / Synchronization Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the next major mobile product surface beyond the foundational consumer experience.

This is a bounded mobile implementation milestone.

Do not implement the complete mobile product.

Do not provision production infrastructure.

Do not redesign backend contracts.

Do not invent API behavior that is not supported by the repository's authoritative contracts.

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

This prompt implements the **mobile creator workflow, media upload and publishing experience, richer discovery, notifications, saved content, creator analytics, reporting, and safety-related mobile experiences**.

---

# TARGET USERS

The mobile experiences implemented in this milestone must support:

* creators;
* viewers;
* authenticated users;
* users managing notifications;
* users managing saved content;
* creators reviewing their content and analytics;
* users submitting safety reports;
* users managing privacy and account controls.

All backend authorization, privacy, moderation, and ownership decisions remain authoritative.

---

# SCALE TARGET

The completed mobile application must remain suitable for:

* millions to hundreds of millions of users;
* large creator populations;
* high video-upload activity;
* large notification volumes;
* high search traffic;
* large analytics datasets;
* frequent network interruptions;
* devices with constrained memory, storage, CPU, and bandwidth.

Do not build client behavior that assumes unlimited:

* local storage;
* memory;
* network throughput;
* upload concurrency;
* notification history;
* analytics history.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible and justified alternative, use:

* React Native;
* Expo where compatible with the required functionality;
* TypeScript;
* the repository's established navigation architecture;
* the repository's established API client;
* the repository's established server-state/data-fetching mechanism;
* secure native storage;
* native device media/camera capabilities through the repository's selected abstractions;
* the repository's established testing infrastructure.

Preserve compatible choices.

Do not introduce competing upload, navigation, state-management, or networking frameworks without a concrete repository-level reason.

---

# REPOSITORY INSPECTION

Before implementation:

1. Inspect the repository.
2. Identify the current mobile application.
3. Inspect navigation and route structure.
4. Inspect existing authentication and secure storage.
5. Inspect video playback and feed components.
6. Inspect the backend API client and contract types.
7. Inspect upload/media abstractions.
8. Inspect platform permissions.
9. Inspect push-notification registration.
10. Inspect deep-link configuration.
11. Inspect search/discovery integration.
12. Inspect notification APIs.
13. Inspect analytics APIs.
14. Inspect report/safety APIs.
15. Inspect existing tests.
16. Identify reusable components and services.
17. Preserve compatible existing behavior.
18. Avoid unnecessary rewrites.
19. Do not fabricate repository state.

The repository is authoritative for current implementation state.

This prompt is authoritative for the current mobile milestone.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the mobile experiences required for:

* camera/media acquisition;
* short-form video draft creation;
* local media preview;
* upload authorization;
* resilient media upload;
* upload progress;
* retry/resume behavior where supported;
* processing-state display;
* caption editing;
* hashtag entry;
* mention selection;
* sound/audio selection;
* visibility selection;
* publishing;
* creator content management;
* discovery/search results;
* trending;
* recommendation controls;
* notifications center;
* notification preferences;
* push notification handling;
* saved/favorite content;
* creator analytics;
* video analytics;
* reporting;
* privacy/safety controls;
* block-state propagation;
* telemetry;
* offline-aware behavior;
* accessibility;
* performance;
* testing;
* documentation.

Implement actual mobile functionality against backend contracts.

Do not use mock data as a substitute for unavailable backend behavior in production code.

---

# CREATOR NAVIGATION

Extend the mobile navigation to include creator-oriented destinations such as:

* Create;
* drafts;
* creator content;
* analytics;
* saved content;
* notifications;
* settings.

Use route guards appropriate to authentication and ownership.

Do not expose creator-management actions to unauthorized accounts.

---

# MOBILE CREATOR HOME

Implement an authenticated creator-oriented entry experience where appropriate.

Show:

* creator identity;
* recent content;
* draft status;
* processing status;
* publish shortcuts;
* analytics summary;
* content-management access.

Do not turn this into a privileged administration panel.

---

# VIDEO CREATION ENTRY

Implement a mobile entry flow for creating a short-form video.

Support selecting:

* camera capture;
* device media;
* supported existing video files.

The exact acquisition mechanism must follow the repository's selected native/Expo APIs.

Request only the permissions required for the selected action.

Do not request camera/microphone/media-library permissions unnecessarily at app startup.

---

# CAMERA PERMISSIONS

When camera creation is supported:

* request camera permission at the point of use;
* request microphone permission only when audio capture requires it;
* explain unavailable permissions clearly;
* provide a route to system settings when appropriate;
* handle denial without crashing;
* handle revoked permissions after initial grant.

Do not assume permission remains granted indefinitely.

---

# MEDIA LIBRARY PERMISSIONS

When selecting existing media:

* request media-library permission only when needed;
* handle limited-access selections where the platform supports them;
* handle permission denial;
* allow retry;
* avoid scanning unnecessary portions of the user's media library.

Do not persist media-library contents unnecessarily.

---

# VIDEO RECORDING

Implement short-form video recording where required by the repository and current product scope.

Support appropriate:

* portrait-oriented capture;
* duration limits;
* start/stop;
* recording state;
* cancel;
* discard;
* preview;
* camera errors;
* microphone behavior.

Do not expose a recording UI that claims unsupported camera capabilities.

---

# RECORDING PERFORMANCE

The recording experience must:

* avoid unnecessary frame copying;
* avoid holding large uncompressed media buffers in application state;
* release camera resources when leaving the screen;
* stop recording cleanly on interruption;
* handle app backgrounding safely.

Do not keep the camera active while navigating elsewhere.

---

# LOCAL MEDIA PREVIEW

Before upload, provide a creator preview.

Support:

* playback;
* duration;
* basic media metadata;
* discard;
* continue to editing/publishing.

Use temporary local references appropriately.

Release temporary resources when the draft is deleted or abandoned.

---

# DRAFT CREATION

Create a backend-backed draft before initiating a durable upload where the API contract requires it.

Maintain explicit local states:

* local_media_selected;
* draft_creating;
* draft_created;
* upload_pending;
* uploading;
* uploaded;
* processing;
* ready;
* publishable;
* failed.

Do not collapse these into a single generic "uploading" state.

---

# UPLOAD AUTHORIZATION

Integrate with the backend upload-intent contract.

The mobile client must:

1. authenticate the creator;
2. create or load the draft;
3. request upload authorization;
4. receive a scoped, time-limited upload target;
5. upload media;
6. report completion;
7. observe processing;
8. continue to metadata/publish state.

Never embed storage credentials.

Never construct unrestricted object-storage requests.

---

# MOBILE UPLOAD IMPLEMENTATION

Implement efficient file upload suitable for large video files.

Where supported, use:

* streaming;
* multipart/chunked uploads;
* progress callbacks;
* resumable upload mechanisms;
* background-capable upload facilities.

Do not load an entire large video into JavaScript memory unnecessarily.

Choose the repository-supported upload mechanism that best preserves reliability on mobile networks.

---

# UPLOAD PROGRESS

Display accurate:

* percentage;
* bytes transferred where appropriate;
* upload state;
* retry state.

Clearly distinguish:

* local preparation;
* uploading;
* uploaded;
* processing;
* ready.

Do not display publication success merely because the bytes finished transferring.

---

# NETWORK INTERRUPTIONS DURING UPLOAD

Handle:

* Wi-Fi to cellular transition;
* temporary offline state;
* app backgrounding;
* timeout;
* connection reset;
* upload authorization expiration.

Where the backend/storage contract supports resumable uploads:

* persist sufficient non-sensitive upload state;
* resume safely;
* reauthorize when necessary.

Where resumability is not supported, fail safely and provide a controlled restart path.

Do not loop endlessly on failed uploads.

---

# UPLOAD RETRIES

Retry only failures that are reasonably transient.

Do not blindly retry:

* invalid media;
* permission denial;
* authorization failure;
* permanent provider errors.

Use bounded retries and backoff.

Avoid duplicating uploads because of ambiguous client state.

---

# DRAFT PERSISTENCE

Persist only the minimum local state needed to recover an interrupted creator workflow.

Appropriate local state may include:

* draft identifier;
* local media reference;
* upload state;
* retry state;
* minimal metadata.

Do not store:

* access tokens in ordinary storage;
* full sensitive backend responses;
* unnecessary private media copies.

Clean stale local drafts according to a bounded retention policy.

---

# MEDIA VALIDATION

Validate locally:

* file type;
* duration;
* approximate file size;
* dimensions;
* obvious codec incompatibility where detectable.

Client validation is for user experience only.

The backend remains authoritative.

Do not claim media eligibility based only on local metadata.

---

# MEDIA PREPROCESSING

Where the mobile architecture supports lightweight client-side preparation, implement only justified operations such as:

* orientation normalization;
* metadata inspection;
* preview generation;
* safe thumbnail preview.

Do not perform expensive production-grade transcoding on-device merely to imitate backend media processing.

The server-side media pipeline remains authoritative for final playback assets.

---

# METADATA EDITOR

Implement creator metadata editing for:

* caption;
* hashtags;
* mentions;
* sound/audio;
* visibility.

Support:

* validation;
* character counts;
* loading states;
* unsaved-change handling;
* save;
* cancel;
* error recovery.

---

# CAPTION EDITOR

Support:

* multiline input;
* character limit;
* character counter;
* validation;
* keyboard-aware layout;
* safe preview.

Do not render caption text as arbitrary HTML.

---

# HASHTAG EXPERIENCE

Implement hashtag entry.

Support:

* normalized hashtag input;
* duplicate detection;
* deletion;
* suggestions where backend support exists;
* bounded search;
* keyboard/mobile interaction appropriate to the platform.

Avoid firing an unrestricted network request for every keystroke.

Debounce and cancel obsolete requests.

---

# MENTION EXPERIENCE

Implement mention selection.

Support:

* handle search;
* suggestions;
* keyboard/touch navigation;
* insertion;
* removal;
* invalid-account handling.

Resolve actual account identity through backend data.

Do not let a client-supplied user ID become a trusted mention solely because it was included in a local object.

---

# SOUND / AUDIO EXPERIENCE

Implement sound/audio selection where supported.

Support:

* sound search;
* selection;
* preview where the API provides playable media;
* unavailable sound handling;
* replacement;
* removal.

Do not download large audio catalogs into local storage.

Do not expose internal rights-management metadata unnecessarily.

---

# VISIBILITY

Implement content visibility controls for appropriate backend-defined values.

Support:

* public;
* private;
* other explicitly supported visibility states.

Clearly describe consequences.

Do not permit creators to manipulate moderation state, processing state, or publication state directly.

---

# PUBLISH PREVIEW

Provide a final preview screen before publication.

Display:

* video preview;
* caption;
* hashtags;
* mentions;
* sound;
* visibility;
* processing status;
* publication readiness.

Prevent publication until backend-required prerequisites are satisfied.

---

# PUBLISHING

Implement the mobile publish operation.

Before submitting:

* verify current authenticated identity;
* verify current draft/video state;
* verify required processing readiness;
* verify metadata;
* prevent duplicate submission.

After submission:

* show authoritative result;
* handle conflict;
* handle expired session;
* handle moderation restriction;
* handle transient failure;
* update creator content state.

---

# PUBLISH FAILURE RECOVERY

Support safe recovery for:

* validation error;
* upload not complete;
* media processing failure;
* authorization failure;
* network failure;
* moderation restriction;
* duplicate request;
* server error.

Preserve the draft when recovery is possible.

Do not force creators to restart from scratch after every transient network failure.

---

# CREATOR CONTENT LIBRARY

Implement a mobile creator content-management experience.

Support:

* drafts;
* processing content;
* published videos;
* restricted/removed videos where creator access permits;
* bounded pagination;
* status filtering.

Do not load the entire creator library into memory.

---

# CONTENT MANAGEMENT ACTIONS

Support where authorized:

* edit metadata;
* change visibility;
* delete;
* view;
* inspect processing state.

Use confirmation for destructive actions.

Do not expose moderator-only enforcement controls.

---

# CONTENT DELETION

Implement a destructive-action confirmation.

After successful deletion:

* invalidate affected cached data;
* remove the content from creator lists;
* remove it from saved local state where relevant;
* prevent subsequent playback through the normal mobile client.

Do not assume object-storage cleanup has completed instantly.

---

# PROCESSING STATUS

Render:

* upload pending;
* uploading;
* processing;
* ready;
* failed;
* restricted;
* removed.

Refresh state using:

* bounded polling where necessary;
* realtime updates if available;
* explicit user refresh.

Do not create an infinite polling loop.

Stop polling when:

* the screen is not relevant;
* the app is backgrounded;
* the terminal state is reached.

---

# DISCOVERY

Implement the mobile discovery experience.

Support:

* search entry;
* result tabs;
* creator results;
* video results;
* hashtag results;
* sound results where available;
* trending content;
* bounded pagination;
* loading;
* empty;
* error;
* retry.

Use backend relevance and ranking.

Do not rank results in the mobile application.

---

# SEARCH INPUT

Implement:

* debounced query;
* request cancellation;
* query history where appropriate and privacy-safe;
* keyboard behavior;
* clear button;
* empty-query behavior.

Do not store unlimited search history.

---

# SEARCH RESULT PRESENTATION

Create explicit mobile result components for:

* creators;
* videos;
* hashtags;
* sounds.

Handle:

* private accounts;
* deleted content;
* restricted content;
* blocked entities;
* unavailable sounds.

Do not show cached restricted results after the server says they are inaccessible.

---

# TRENDING

Implement mobile trending/discovery surfaces.

Support:

* trending videos;
* hashtags;
* creators;
* sounds where available.

Use bounded lists and efficient image/video loading.

Do not preload all trending media.

---

# RECOMMENDATION EXPERIENCE

Extend the personalized feed controls with:

* refresh;
* not-interested actions;
* hide creator/content where supported;
* report;
* save;
* follow.

The client must submit backend feedback events.

Do not implement ranking models locally.

---

# NOTIFICATION CENTER

Implement the complete mobile notification center supported by the backend.

Support:

* notification list;
* unread indicator;
* unread count;
* mark read;
* mark all read where supported;
* grouped notifications where provided;
* navigation to content/profile;
* unavailable/deleted target handling;
* cursor pagination.

---

# NOTIFICATION NAVIGATION

When a notification references a target:

* verify the route is valid;
* navigate only if the target remains accessible;
* handle deleted/private/restricted targets gracefully;
* avoid exposing restricted data from cached notification payloads.

Do not assume a previously valid target remains accessible.

---

# NOTIFICATION PREFERENCES

Implement:

* likes;
* comments;
* replies;
* follows;
* mentions;
* creator activity;
* push;
* in-app

where supported.

Provide:

* current values;
* loading;
* save state;
* error;
* retry.

---

# PUSH NOTIFICATIONS

Complete the mobile push-notification experience.

Support:

* permission request;
* token registration;
* token refresh;
* token removal;
* logout cleanup;
* foreground notification handling;
* background notification handling;
* notification tap handling.

Do not request notification permission immediately without an appropriate product context.

---

# PUSH DEEP LINKS

Notification taps must navigate through the same canonical deep-link/router model.

Support targets such as:

* video;
* creator profile;
* comment;
* notification center;
* other explicitly supported entities.

Handle:

* logged-out user;
* expired session;
* deleted target;
* inaccessible target.

Never put authentication credentials inside notification payloads.

---

# SAVED CONTENT

Implement the mobile saved/favorite content experience.

Support:

* saved-video list;
* cursor pagination;
* open video;
* remove saved state;
* unavailable/deleted content;
* refresh.

Keep the local list bounded.

---

# CREATOR ANALYTICS

Implement the mobile creator analytics experience.

Support metrics returned by the backend such as:

* views;
* watch time;
* completion;
* likes;
* comments;
* shares;
* favorites;
* follower growth;
* engagement rates;
* content-performance trends.

Do not invent metrics unavailable from the backend.

---

# ANALYTICS TIME RANGES

Support bounded backend-supported ranges such as:

* recent;
* week;
* month;
* custom range where available.

Do not request unlimited historical datasets.

---

# ANALYTICS VISUALIZATION

Use mobile-appropriate:

* metric cards;
* compact charts;
* tables/lists where useful;
* drill-down views.

Charts must provide:

* accessible textual summaries;
* clear labels;
* empty states;
* loading state;
* error state.

Do not make chart interaction the only way to understand important information.

---

# VIDEO ANALYTICS

Provide a creator-facing video detail analytics view where backend support exists.

Support:

* selected video;
* views;
* watch time;
* completion;
* engagement;
* time-series metrics.

Do not load every video's detailed analytics simultaneously.

---

# REPORTING

Implement reusable user reporting flows for:

* video;
* comment;
* creator/account;
* other explicitly supported targets.

Provide:

* category;
* optional description;
* validation;
* submission state;
* success;
* failure.

Do not expose internal moderation decisions.

---

# REPORT SECURITY

Prevent:

* duplicate rapid submissions;
* report flooding;
* sensitive report data exposure;
* unauthorized target references.

Do not store report descriptions in general-purpose local analytics or logs.

---

# BLOCKING

Extend blocking behavior throughout:

* profiles;
* feeds;
* search;
* discovery;
* comments;
* notifications;
* saved content.

After a block:

* remove newly unauthorized content;
* invalidate affected cached state;
* update relationship state;
* prevent navigation into restricted targets.

---

# PRIVACY

Respect:

* private profiles;
* private videos;
* account restrictions;
* moderation;
* deletion;
* blocking.

Never present cached data simply because it was previously authorized.

---

# LOCAL CACHE SECURITY

Define cache categories for:

* public content;
* authenticated content;
* private user-specific state;
* sensitive session state.

Sensitive content should not remain in shared/unprotected caches.

When authorization context changes, invalidate data whose visibility may have changed.

---

# OFFLINE BEHAVIOR

Provide bounded offline support for:

* previously loaded non-sensitive UI state;
* creator draft metadata where safe;
* pending upload recovery where supported;
* pending telemetry.

Do not claim general offline video playback unless the media architecture explicitly supports it.

Do not allow offline cached state to bypass current server authorization once connectivity returns.

---

# APP BACKGROUNDING

Handle creator flows during backgrounding.

When the app moves to the background:

* pause unnecessary work;
* use native/background upload facilities where supported;
* preserve recoverable draft state;
* stop unnecessary polling;
* flush bounded telemetry;
* release resources that cannot remain active.

When returning to foreground:

* reconcile state with the backend;
* refresh expired authorization;
* resume appropriate upload/processing status monitoring.

---

# UPLOAD BACKGROUNDING

Where the platform and selected upload implementation support background uploads, use them appropriately.

The implementation must:

* observe background progress;
* recover from cancellation;
* update draft state;
* reconcile uncertain upload completion.

Do not claim background uploading on platforms where the chosen implementation does not support it.

---

# MOBILE STORAGE MANAGEMENT

Large media workflows must avoid uncontrolled storage growth.

Clean:

* abandoned local media;
* temporary previews;
* obsolete upload fragments;
* stale draft assets;
* expired telemetry batches

according to bounded policies.

Never delete a local media file still required for an active recoverable upload without first determining its dependency state.

---

# PERMISSION LIFECYCLE

Handle permission changes after installation.

Users may revoke:

* camera;
* microphone;
* media library;
* notifications

outside the app.

Recheck permissions at the point of use where required.

Do not assume first-launch permission state is permanent.

---

# PERFORMANCE

Optimize:

* creator screen startup;
* camera initialization;
* local preview;
* upload;
* search;
* notifications;
* analytics rendering;
* list virtualization;
* media memory;
* navigation.

Use lazy loading for noncritical creator screens.

Avoid retaining large media buffers after upload.

---

# MEMORY MANAGEMENT

Monitor long-lived mobile sessions for:

* unbounded feed cache;
* media references;
* image memory;
* analytics data;
* notification lists;
* upload buffers.

Release:

* player instances;
* camera resources;
* object references;
* temporary media;
* offscreen content

when no longer required.

---

# BATTERY

Avoid unnecessary:

* polling;
* GPS or unrelated device services;
* background networking;
* upload retries;
* analytics flushes;
* timers.

Use event-driven updates where possible.

---

# ACCESSIBILITY

Implement accessibility across creator and discovery workflows.

Support:

* screen readers;
* accessible form labels;
* logical focus;
* large text where practical;
* accessible upload progress;
* accessible processing status;
* accessible charts;
* accessible search results;
* accessible notification controls;
* accessible dialogs/bottom sheets;
* meaningful error announcements.

Do not rely on color alone.

---

# MOBILE SECURITY

Protect against:

* insecure credential storage;
* sensitive data leakage through local storage;
* deep-link manipulation;
* unsafe URLs;
* debug logs;
* push-payload leakage;
* screenshot/private-content exposure where relevant to the platform;
* malicious file references;
* unauthorized cached content.

Do not place backend secrets in mobile configuration.

Do not trust local state as an authorization boundary.

---

# PUSH PAYLOAD PRIVACY

Push payloads should contain only the minimum information required to route and present the notification.

Do not place:

* authentication credentials;
* private report descriptions;
* sensitive account data;
* private media;
* secrets

into push payloads.

Where sensitive content is involved, fetch the authoritative data after the user opens the notification.

---

# DEEP LINKS

Extend the deep-link system to cover:

* videos;
* creators;
* hashtags;
* sounds where supported;
* search;
* notification targets;
* creator-management routes where safe.

Validate incoming links.

Do not trust deep-link parameters as authorization.

---

# ANALYTICS INSTRUMENTATION

Extend the centralized mobile analytics layer for:

* creator screen viewed;
* video capture started;
* video capture completed;
* upload started;
* upload completed;
* upload failed;
* publish started;
* publish completed;
* search submitted;
* search result opened;
* trending item opened;
* notification opened;
* notification marked read;
* saved content opened;
* analytics screen opened;
* report submitted.

Do not send:

* passwords;
* access tokens;
* refresh credentials;
* push tokens;
* private report text;
* private content;
* unnecessary personal data.

---

# PLAYBACK TELEMETRY INTEGRATION

Ensure creator/discovery flows remain compatible with the existing playback telemetry model.

Do not create a second incompatible event schema.

Use the canonical:

* event ID;
* event type;
* video ID;
* user/session;
* timestamp;
* playback position;
* duration;
* platform.

---

# EVENT BATCHING

Use bounded telemetry batching.

Support:

* count limit;
* payload limit;
* time limit;
* background/termination flush;
* retry;
* expiration.

Do not retain telemetry indefinitely when offline.

Discard or aggregate according to the defined retention policy when safe.

---

# OBSERVABILITY

Add mobile telemetry for:

* upload duration;
* upload failure rate;
* processing wait;
* publish failure;
* search latency;
* notification loading;
* push-registration failures;
* creator analytics loading;
* report submission failure;
* deep-link failure.

Do not send sensitive request headers or credentials into telemetry.

---

# ERROR HANDLING

Provide consistent handling for:

* upload failure;
* expired upload authorization;
* processing failure;
* publish conflict;
* search error;
* notification error;
* analytics error;
* report error;
* permission denial;
* offline state;
* authentication expiration.

Every major asynchronous flow must have:

* loading;
* success;
* empty;
* retry/error;
* unavailable states where applicable.

---

# NETWORK RESILIENCE

Use bounded retries for transient failures.

Support:

* cancellation;
* stale-request prevention;
* reconnect;
* request deduplication.

Do not allow a stale search response to overwrite a newer query.

Do not retry destructive actions blindly.

---

# STATE CONSISTENCY

After:

* publish;
* edit metadata;
* delete;
* visibility change;
* save/unsave;
* notification read;
* preference update;
* block/unblock;

update or invalidate affected local state.

Do not let optimistic updates remain after a confirmed server rejection.

---

# TESTING

Create meaningful mobile tests for:

* media permissions;
* camera entry;
* media selection;
* draft creation;
* upload authorization;
* upload progress;
* upload failure;
* retry/resume;
* processing state;
* metadata editing;
* hashtags;
* mentions;
* sounds;
* visibility;
* publish gating;
* publish failure;
* creator content management;
* search;
* trending;
* recommendation controls;
* notifications;
* notification preferences;
* push notification handling;
* saved content;
* analytics;
* reporting;
* block/privacy behavior;
* offline/reconnect;
* deep links.

---

# COMPONENT TESTING

Test reusable components such as:

* creator dashboard;
* capture screen;
* upload progress;
* media preview;
* metadata editor;
* hashtag field;
* mention picker;
* sound picker;
* publish screen;
* content-management item;
* search result;
* notification item;
* analytics card/chart;
* report dialog.

Focus on user-visible behavior.

Avoid brittle implementation-specific assertions.

---

# INTEGRATION TESTING

Test integrated flows covering:

* create draft;
* authorize upload;
* upload;
* complete upload;
* processing-state retrieval;
* publish;
* search;
* notification navigation;
* saved content;
* creator analytics;
* report submission;
* block propagation.

Use actual backend contracts or appropriate integrated test infrastructure where available.

---

# END-TO-END TESTING

Where mobile E2E infrastructure exists, validate representative flows on supported iOS/Android targets:

* create;
* select/capture media;
* upload;
* publish;
* discover;
* search;
* receive/open notification;
* save;
* creator analytics;
* report.

Do not claim device-level E2E validation unless it actually ran.

---

# ACCESSIBILITY TESTING

Run automated accessibility checks where supported.

Validate:

* creator forms;
* upload progress;
* dialogs;
* search;
* analytics;
* notifications;
* reporting.

Manually inspect critical screen-reader flows.

---

# SECURITY TESTING

Test:

* secure local credential storage;
* sensitive cache invalidation;
* deep-link authorization;
* private-content leakage;
* report-data leakage;
* push payload privacy;
* unauthorized creator analytics;
* unauthorized creator actions;
* unsafe URL/media handling;
* debug-log leakage.

---

# PERFORMANCE VALIDATION

Where tooling permits, validate:

* camera startup;
* local preview;
* upload memory;
* prolonged creator workflow;
* search request volume;
* notification list rendering;
* analytics rendering;
* background/resume behavior;
* memory cleanup.

Do not claim production-device performance from a single test device.

---

# DOCUMENTATION

Update repository documentation describing:

* creator mobile flow;
* camera/media permissions;
* upload architecture;
* background upload behavior;
* draft recovery;
* publishing;
* search/discovery;
* notifications;
* push handling;
* saved content;
* creator analytics;
* reporting;
* offline behavior;
* telemetry;
* testing;
* platform-specific requirements;
* local development configuration.

Documentation must accurately describe actual capabilities.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* creator navigation;
* creator home/dashboard;
* camera/media entry;
* video recording where supported;
* media-library selection;
* local media preview;
* draft creation;
* draft persistence;
* upload authorization integration;
* large-file upload;
* upload progress;
* upload retry/resume where supported;
* upload interruption recovery;
* media validation;
* metadata editing;
* caption;
* hashtags;
* mentions;
* sound/audio selection;
* visibility;
* publish preview;
* publishing;
* publish failure recovery;
* creator content library;
* content-management actions;
* content deletion;
* processing-state UI;
* discovery/search;
* search results;
* trending;
* recommendation controls;
* notification center;
* notification preferences;
* push-notification handling;
* push deep links;
* saved content;
* creator analytics;
* video analytics;
* reporting;
* safety/blocking extensions;
* privacy handling;
* bounded offline behavior;
* app-background handling;
* background upload where supported;
* local storage management;
* accessibility;
* performance;
* mobile security;
* telemetry;
* observability;
* unit/component tests;
* integration tests;
* applicable E2E tests;
* accessibility tests;
* security tests;
* documentation.

This prompt does **not** implement:

* the remaining web application;
* production cloud infrastructure;
* backend APIs;
* backend media processing;
* backend search;
* backend recommendations;
* backend notifications;
* backend moderation;
* a full creator monetization system;
* live streaming;
* direct messaging;
* advertising;
* advanced video editing effects/AR systems unless already explicitly established by the repository and current scope;
* unrestricted offline video downloading.

Create only mobile integration points required for the planned project parts.

---

# CROSS-PART COMPATIBILITY

Preserve compatibility with:

* backend authentication;
* profiles;
* social graph;
* videos;
* media;
* feeds;
* engagement;
* search;
* recommendations;
* notifications;
* moderation;
* analytics;
* web;
* infrastructure;
* QA.

Preserve canonical:

* identifiers;
* timestamps;
* API errors;
* pagination;
* authentication;
* authorization;
* video lifecycle;
* visibility;
* moderation state;
* playback authorization;
* behavioral-event schema;
* notification/deep-link targets.

Do not create mobile-specific contract variants.

---

# API INTEGRATION DISCIPLINE

Use the centralized mobile API client for:

* upload authorization;
* draft APIs;
* content management;
* publishing;
* search;
* notifications;
* analytics;
* reporting.

Centralize:

* authentication;
* refresh;
* error mapping;
* request cancellation;
* retry;
* correlation IDs where applicable.

Do not scatter raw network requests throughout creator screens.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* backend APIs;
* object storage;
* media processing;
* search;
* notifications;
* analytics APIs;
* physical devices/simulators.

Use available development/test infrastructure.

When an external dependency is unavailable:

* implement against canonical contracts;
* test through appropriate isolated mechanisms;
* report the limitation accurately;
* do not fabricate upload completion;
* do not fabricate processing completion;
* do not fabricate push delivery;
* do not fabricate analytics results.

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
9. Run security tests.
10. Validate camera/media permission flows.
11. Validate draft state transitions.
12. Validate upload progress and retry behavior.
13. Validate publish gating.
14. Validate search cancellation and pagination.
15. Validate notification handling.
16. Validate push/deep-link behavior where testable.
17. Validate analytics authorization.
18. Validate report submission.
19. Validate block/privacy propagation.
20. Validate offline/reconnect behavior.
21. Inspect runtime errors.
22. Inspect final diff.
23. Search for secrets and credentials.
24. Verify no unrelated mobile product category was implemented.

Do not claim physical-device or external-provider validation unless it actually occurred.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* creator dashboard;
* camera/media acquisition;
* recording;
* local preview;
* drafts;
* upload flow;
* upload recovery;
* metadata editing;
* hashtags;
* mentions;
* sounds;
* visibility;
* publishing;
* creator content management;
* processing-state UI;
* search;
* discovery/trending;
* recommendation controls;
* notification center;
* push handling;
* deep links;
* saved content;
* creator analytics;
* video analytics;
* reporting;
* privacy/blocking;
* offline behavior;
* background processing;
* storage management;
* API-client changes;
* telemetry;
* observability;
* accessibility changes;
* performance work;
* security changes;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim live service behavior was verified unless it was actually tested.

---

# DEFINITION OF DONE

This mobile creator/discovery/notification/analytics milestone is complete only when:

* the repository was inspected;
* creator navigation is implemented;
* creator dashboard is implemented;
* camera/media entry is implemented;
* required permissions are requested at appropriate times;
* video capture works where supported;
* media-library selection works;
* local preview works;
* camera/media resources are released correctly;
* drafts are backend-backed where required;
* local draft recovery state is bounded;
* upload authorization is integrated;
* large-file upload is implemented;
* upload progress is accurate;
* interrupted uploads have safe recovery;
* upload retry is bounded;
* media is validated locally without replacing backend validation;
* metadata editing works;
* captions are validated;
* hashtags work;
* mentions resolve through authoritative backend data;
* sound/audio selection works where supported;
* visibility controls work;
* publish preview is implemented;
* publication is gated on authoritative readiness;
* duplicate publication is prevented;
* publish failures can be recovered safely;
* creator content management is implemented;
* content lists are bounded and paginated;
* destructive deletion is confirmed;
* processing states are displayed correctly;
* discovery/search is implemented;
* search requests are debounced and cancellable;
* search results are privacy-aware;
* trending is implemented;
* recommendation feedback controls work;
* notification center is implemented;
* notification preferences work;
* push registration/handling works where supported;
* notification deep links work;
* saved content works;
* creator analytics work;
* video analytics work;
* analytics are authorized and bounded;
* reporting works;
* block/privacy behavior is reflected across mobile experiences;
* offline behavior is bounded and safe;
* background/resume behavior is correct;
* background uploads work where the platform supports them;
* local storage growth is bounded;
* accessibility requirements are implemented;
* memory usage is controlled;
* battery-intensive behavior is minimized;
* security requirements are implemented;
* telemetry is centralized;
* observability is implemented;
* unit/component tests exist;
* integration tests exist;
* applicable E2E tests exist;
* accessibility tests exist;
* security tests exist;
* TypeScript validation passes;
* linting/formatting passes where configured;
* documentation reflects actual behavior;
* no fake upload success exists;
* no fake processing result exists;
* no fake analytics exists;
* no hardcoded secrets exist;
* no unsupported offline capabilities are claimed;
* no unrelated mobile product category was implemented;
* compatibility with backend, web, infrastructure, search, recommendation, notifications, moderation, analytics, and QA is preserved;
* external validation limitations are reported accurately;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into production infrastructure or unrelated product functionality.
