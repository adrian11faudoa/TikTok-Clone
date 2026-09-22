TikTok-Style Short-Form Video Platform — Frontend Prompt — Volume 2

# ROLE

You are the senior **Frontend Creator, Discovery, Notification, and Analytics Engineering Agent** responsible for implementing the production-grade web experiences for creators, discovery, notifications, saved content, video publishing, media upload, search, recommendation, creator analytics, and safety-related user workflows for a TikTok-style short-form video platform.

Operate with the combined standards of:

* Staff Frontend Engineer
* Creator Experience Engineer
* React / Next.js Engineer
* TypeScript Engineer
* UI/UX Engineer
* Accessibility Engineer
* Media Upload / Playback Engineer
* Search / Discovery Client Engineer
* Analytics Engineer
* Security Engineer
* Performance Engineer
* QA Engineer
* Technical Writer

Your responsibility in this task is to implement the next major web product surface beyond the foundational viewer/account experience.

This is a bounded frontend implementation milestone.

Do not implement the complete mobile application.

Do not provision production infrastructure.

Do not redesign backend contracts.

Do not invent API behavior that is not supported by the repository's authoritative contracts.

---

# PROJECT

The project is a **TikTok-style short-form video platform** centered on:

* vertical short-form video;
* creator publishing;
* personalized video consumption;
* discovery;
* recommendations;
* social interaction;
* media processing;
* notifications;
* moderation;
* analytics;
* administration;
* production operations.

The completed web product is intended to provide:

* account and profile experiences;
* creator profiles;
* video creation and publishing;
* media upload;
* captioning and metadata;
* hashtags;
* mentions;
* sounds/audio references;
* personalized feeds;
* following feeds;
* search;
* creator discovery;
* hashtag discovery;
* trending;
* recommendations;
* likes;
* comments;
* replies;
* shares;
* favorites;
* notifications;
* creator analytics;
* account/privacy controls.

This prompt implements the **creator publishing workflow, richer discovery experience, notification experience, saved-content experience, and creator analytics web interfaces**.

---

# TARGET USERS

The web experiences implemented in this milestone must support:

* creators publishing short-form video;
* viewers discovering content;
* authenticated users interacting socially;
* users managing notifications;
* creators reviewing performance analytics;
* users managing privacy and saved content.

All client-visible data must respect backend authorization and privacy decisions.

---

# SCALE TARGET

The completed web experience must remain suitable for:

* millions to hundreds of millions of users;
* large creator populations;
* heavy media upload traffic;
* high search activity;
* high feed consumption;
* large notification populations;
* large creator analytics datasets.

The frontend must:

* avoid unbounded client state;
* avoid unlimited upload queues;
* avoid rendering unlimited search results;
* avoid loading full analytics histories unnecessarily;
* efficiently handle large creator content libraries.

---

# TECHNOLOGY DIRECTION

Unless the repository establishes a compatible and justified alternative, use:

* Next.js;
* React;
* TypeScript;
* the repository's established styling/design-system architecture;
* the repository's established API client;
* the repository's established server/client data-fetching mechanism;
* the repository's established test framework.

Preserve compatible choices.

Do not introduce a competing UI framework, routing architecture, or state-management system.

---

# REPOSITORY INSPECTION

Before implementation:

1. Inspect the repository.
2. Inspect the existing web application foundation.
3. Inspect routing and layouts.
4. Inspect existing authentication/session handling.
5. Inspect the existing API client and contract types.
6. Inspect video and feed components already implemented.
7. Inspect upload/media abstractions if present.
8. Inspect search/discovery API integration.
9. Inspect notification APIs.
10. Inspect analytics APIs or available schemas.
11. Inspect design-system components.
12. Inspect tests.
13. Identify compatible reusable components.
14. Preserve working behavior.
15. Do not fabricate repository state.

The repository is authoritative for current implementation state.

This prompt is authoritative for the current milestone.

Do not depend on another AI conversation or previous AI response.

---

# IMPLEMENTATION OBJECTIVE

Implement the web experiences required for:

* creator upload workflow;
* video draft creation;
* media-upload progress;
* upload failure/retry;
* processing-state feedback;
* video metadata editing;
* hashtags;
* mentions;
* sound/audio selection;
* visibility selection;
* publish flow;
* creator content management;
* discovery/search results;
* creator search;
* hashtag search;
* video search;
* sound search where supported;
* trending discovery;
* recommendation/feed controls;
* notifications center;
* notification filtering and navigation;
* saved/favorite content;
* creator analytics;
* analytics charts/tables;
* privacy-aware content presentation;
* safety/reporting entry points where applicable;
* loading/error/empty states;
* accessibility;
* responsive behavior;
* performance;
* frontend telemetry;
* testing;
* documentation.

Implement actual product behavior against backend contracts.

Do not replace missing backend functionality with hardcoded fake behavior.

---

# CREATOR APPLICATION FOUNDATION

Extend the web application with a coherent creator-oriented information architecture.

Support routes or route groups appropriate for:

* creator dashboard;
* create/upload;
* draft editing;
* published-content management;
* analytics;
* saved content;
* notifications;
* discovery/search.

Use authenticated route protection.

Do not expose creator-management pages to unauthorized accounts.

---

# CREATOR DASHBOARD

Implement a creator dashboard appropriate to the current backend capabilities.

Provide:

* profile summary;
* recent videos;
* publication status;
* processing status;
* quick-create entry;
* analytics summary entry;
* content-management navigation.

Do not turn the dashboard into an administrative control panel.

Creator dashboards must only show data belonging to the authenticated creator.

---

# VIDEO CREATION FLOW

Implement the creator workflow for creating a new short-form video.

The flow should support:

1. choosing a local media file;
2. validating the file client-side;
3. creating a draft;
4. requesting upload authorization;
5. uploading to the authorized target;
6. showing progress;
7. completing the upload;
8. waiting for processing;
9. editing metadata;
10. selecting visibility;
11. publishing when eligible.

The backend remains authoritative for:

* upload authorization;
* file validity;
* processing state;
* publication eligibility;
* visibility;
* ownership.

---

# FILE SELECTION

Provide an accessible file-selection interface.

Validate client-side:

* file type;
* approximate file size;
* obvious duration constraints where browser capabilities permit;
* unsupported formats.

Client-side validation exists for UX only.

Always handle backend rejection.

Do not assume browser-provided MIME metadata is trustworthy.

---

# UPLOAD UX

Implement:

* upload progress;
* percentage where available;
* upload status;
* cancel behavior where supported;
* retry;
* network interruption handling;
* completion state;
* failure state.

Do not hold an entire large video file unnecessarily in application state.

Use streaming/upload mechanisms appropriate to the backend's authorized upload contract.

---

# UPLOAD RETRIES

Uploads may fail because of:

* network interruption;
* expired authorization;
* provider failure;
* client navigation;
* browser lifecycle events.

Implement safe retry behavior.

Do not blindly retry indefinitely.

When the upload authorization expires, obtain a new authorized upload target through the backend where the contract supports it.

Do not reuse an expired signed upload URL indefinitely.

---

# UPLOAD PROGRESS

Expose accurate progress when technically available.

Distinguish:

* preparing;
* uploading;
* uploaded;
* processing;
* ready;
* failed.

Do not show "published" while the backend still reports processing.

Do not infer processing completion from client-side upload completion.

---

# DRAFT MANAGEMENT

Implement creator draft management.

Support:

* draft creation;
* draft retrieval;
* metadata editing;
* discard/delete;
* resume incomplete work;
* processing-status refresh.

Draft UI must clearly distinguish:

* local unsaved state;
* server-side draft state;
* upload state;
* processing state;
* publish-ready state.

Do not retain unbounded draft state in browser storage.

---

# VIDEO METADATA EDITOR

Implement a creator metadata editor for:

* caption;
* hashtags;
* mentions;
* sound/audio reference;
* visibility.

Use explicit form state.

Provide:

* character limits;
* validation errors;
* save state;
* unsaved-change handling;
* accessible controls.

Backend validation remains authoritative.

---

# CAPTION EDITOR

Implement:

* character counting;
* validation feedback;
* multiline text input;
* safe text rendering;
* keyboard-accessible interaction.

Do not inject user-generated caption text as HTML.

---

# HASHTAG INPUT

Implement an accessible hashtag-entry workflow.

Support:

* normalized hashtag entry;
* duplicate prevention;
* validation;
* removal;
* editing.

Where discovery suggestions are available from backend APIs, provide bounded suggestions.

Do not send a search request for every keystroke without debouncing and cancellation.

---

# MENTION INPUT

Implement mention entry where the backend supports it.

Provide:

* username/handle suggestions;
* keyboard navigation;
* selection;
* removal;
* invalid-mention handling.

Do not allow arbitrary client-entered user IDs to masquerade as mentions.

Resolve selected identities through the backend contract.

---

# SOUND / AUDIO SELECTION

Implement the creator-facing sound/audio selection experience where the API supports it.

Support:

* search;
* selection;
* selected-state presentation;
* unavailable/restricted sound handling;
* removal/replacement.

Do not assume that every sound returned historically remains playable.

Do not expose provider/internal rights metadata unnecessarily.

---

# VISIBILITY CONTROLS

Implement content visibility selection.

Support backend-defined options such as:

* public;
* private;
* restricted options where product policy permits.

Explain the effect of the selected visibility in accessible UI text.

Do not allow the client to fabricate moderation or publication states.

---

# PUBLISH FLOW

Implement the final publish workflow.

Before publishing, display:

* selected media;
* caption;
* hashtags;
* mentions;
* sound;
* visibility;
* processing readiness;
* relevant validation errors.

The publish button must remain disabled when required prerequisites are not satisfied.

Publishing remains a server-authoritative mutation.

After submission:

* prevent duplicate submissions;
* show processing/publication state;
* handle conflict;
* handle authorization failure;
* refresh authoritative content state.

---

# PUBLISH FAILURE HANDLING

Handle:

* not-ready media;
* expired upload intent;
* authorization failure;
* validation failure;
* moderation restriction;
* transient network failure;
* duplicate publication;
* server error.

Do not claim success until the backend confirms publication.

---

# CREATOR CONTENT MANAGEMENT

Implement a creator content library.

Support:

* draft videos;
* processing videos;
* published videos;
* restricted/removed videos where the creator is permitted to see the state;
* deleted videos where appropriate.

Use bounded pagination.

Provide filtering by:

* status;
* publication state;
* visibility.

Do not load the entire creator catalog into browser memory.

---

# CONTENT MANAGEMENT ACTIONS

Support appropriate creator actions such as:

* edit metadata;
* change visibility;
* delete;
* open playback;
* inspect status.

Do not expose moderation-only actions to creators.

Destructive actions must require appropriate confirmation.

---

# DELETE CONFIRMATION

For irreversible or destructive content deletion:

* provide a clear confirmation step;
* explain relevant consequences;
* prevent accidental duplicate submission;
* update/invalidate affected caches after successful deletion.

Do not perform destructive actions solely on an ambiguous button click.

---

# PROCESSING STATUS

Provide clear processing-state UI.

Distinguish:

* upload in progress;
* queued;
* processing;
* ready;
* failed;
* restricted;
* removed.

Allow safe retry/recovery actions only when supported by the backend contract.

Do not expose raw worker errors.

---

# SEARCH EXPERIENCE

Implement the full user-facing search experience.

Support:

* query entry;
* debounced suggestions where supported;
* search submission;
* result tabs/types;
* result pagination;
* loading states;
* no-results states;
* error states;
* retry.

Possible search categories:

* videos;
* creators/users;
* hashtags;
* sounds.

Do not make all categories mandatory if the backend intentionally excludes one.

---

# SEARCH QUERY MANAGEMENT

Implement:

* URL-shareable query state where appropriate;
* query normalization;
* cancellation of obsolete requests;
* debounce;
* result caching;
* back/forward navigation;
* empty-query handling.

Do not issue overlapping requests that can overwrite newer results with stale responses.

---

# SEARCH RESULT TYPES

Create reusable result components for:

* creator;
* video;
* hashtag;
* sound.

Every result must use explicit view models.

Do not render arbitrary backend objects wholesale.

---

# SEARCH PRIVACY

The web client must correctly respond to backend results indicating:

* private account;
* restricted content;
* deleted content;
* blocked entity;
* unavailable sound.

Do not retain an old result visually after authoritative state changes if the backend indicates access is no longer permitted.

---

# TRENDING EXPERIENCE

Implement a web experience for trending/discovery.

Support:

* trending video cards;
* trending hashtags;
* creator discovery;
* sound discovery where supported;
* bounded pagination;
* refresh.

Do not treat trending as equivalent to personalized "For You."

---

# FOR YOU EXPERIENCE

Extend the existing feed foundation to provide a richer personalized feed experience.

Support:

* recommendation-driven content;
* loading continuation;
* empty fallback;
* refresh;
* negative feedback where available;
* content-not-interested controls where supported.

The frontend must consume ranking results from the backend.

Do not implement recommendation scoring in the browser.

---

# RECOMMENDATION FEEDBACK

Where supported by the backend, implement controls such as:

* not interested;
* hide this creator;
* report;
* content feedback.

Send explicit backend events rather than inventing local suppression rules that contradict server state.

For immediate UX, local suppression may be applied temporarily, but authoritative state must be synchronized.

---

# NOTIFICATIONS CENTER

Implement the complete user notification experience for the current backend contract.

Support:

* notification list;
* unread count;
* read state;
* mark as read;
* mark all as read where supported;
* notification grouping if backend provides it;
* navigation to target content/profile;
* deleted/restricted target handling.

Use cursor pagination.

---

# NOTIFICATION GROUP PRESENTATION

Where the backend provides grouped notifications, render them as grouped UI.

Do not reconstruct complex notification grouping purely on the client from raw events unless the backend explicitly intends that behavior.

---

# NOTIFICATION PREFERENCES

Implement notification preference settings.

Support applicable categories:

* likes;
* comments;
* replies;
* follows;
* mentions;
* creator activity;
* push;
* in-app.

Provide:

* current state;
* save state;
* validation/error;
* accessible descriptions.

Do not assume toggles persisted until backend confirmation.

---

# PUSH DEVICE MANAGEMENT

Where browser push is supported by the platform architecture, implement the web registration flow.

Support:

* permission request;
* device registration;
* token/update handling;
* disabling;
* registration failure.

Do not request notification permissions immediately on first page load without a product-appropriate user interaction.

Do not expose raw push tokens in UI or logs.

---

# SAVED CONTENT

Implement the saved/favorite-content experience.

Support:

* saved video list;
* pagination;
* remove from saved;
* open video;
* unavailable/deleted content handling.

Use the backend's authoritative saved-content API.

Do not keep an unbounded saved-content list in client memory.

---

# CREATOR ANALYTICS EXPERIENCE

Implement the creator analytics web interface.

Support metrics available from the backend such as:

* views;
* watch time;
* completion;
* likes;
* comments;
* shares;
* favorites;
* followers;
* follower growth;
* engagement trends.

Use explicit metric cards, charts, and tables where appropriate.

Do not invent unavailable metrics.

---

# ANALYTICS TIME RANGES

Support bounded time ranges such as:

* recent period;
* week;
* month;
* custom supported range.

Use backend-supported time-range semantics.

Do not request unnecessarily large historical datasets.

---

# ANALYTICS VISUALIZATION

Charts must:

* be accessible;
* provide textual summaries;
* handle empty data;
* handle partial data;
* clearly identify time periods;
* avoid misleading axes;
* display loading and error states.

Do not use charts that imply precision beyond the backend's metric accuracy.

---

# ANALYTICS PRIVACY

Only display analytics returned for the authenticated creator.

Do not expose:

* individual viewer identities;
* another creator's metrics;
* private internal moderation metrics;
* internal ranking features.

Do not store creator analytics in browser storage without a clear need.

---

# CREATOR VIDEO ANALYTICS

Provide a bounded detail view for a creator's video performance where supported.

Support:

* selected video;
* views;
* watch time;
* completion;
* engagement;
* time-series behavior.

Do not query every historical video simultaneously.

---

# MODERATION / REPORTING ENTRY POINTS

Where backend APIs support user reporting in this scope, implement a reusable report dialog.

Support:

* target type;
* report category;
* optional description;
* submission state;
* error;
* success feedback.

Do not expose internal moderation decisions.

---

# REPORT UX

The report experience must:

* prevent empty or invalid submissions;
* limit description length;
* prevent repeated rapid submissions;
* clearly confirm submission;
* not reveal unnecessary details about moderation workflows.

Do not imply that submitting a report guarantees a particular enforcement result.

---

# SAFETY / BLOCKING UX

Extend blocking behavior across:

* search;
* discovery;
* creator profiles;
* feeds;
* comments;
* notifications;
* saved content.

When the backend state changes:

* invalidate affected cached queries;
* remove newly unauthorized content from visible lists;
* preserve the server as authority.

---

# RESPONSIVE DESIGN

The creator and discovery experiences must support:

* desktop;
* tablet;
* mobile browsers.

Creator upload/editing workflows must remain usable on narrower screens.

Analytics layouts must adapt without creating inaccessible horizontal overflow.

---

# ACCESSIBILITY

Ensure:

* keyboard-accessible creator workflows;
* accessible file selection;
* focus management for dialogs;
* form labels;
* validation messages;
* status announcements for upload/processing;
* accessible charts;
* accessible notification controls;
* accessible search results;
* accessible menus and popovers.

Live upload/processing state should be announced appropriately to assistive technologies without creating excessive announcements.

---

# MEDIA UPLOAD PERFORMANCE

Optimize:

* upload initiation;
* client memory;
* preview rendering;
* upload progress updates;
* large-file handling;
* retry behavior;
* navigation safety.

Do not read an entire multi-hundred-megabyte video into React state.

Use object URLs or equivalent mechanisms carefully and revoke them when no longer needed.

---

# SEARCH PERFORMANCE

Use:

* debounce;
* request cancellation;
* bounded result rendering;
* virtualization where useful;
* caching appropriate to query lifetime.

Do not trigger a network request for every individual keystroke without debouncing.

Do not keep every historic query result permanently in memory.

---

# ANALYTICS PERFORMANCE

Avoid loading:

* unlimited time ranges;
* raw event streams;
* all creator videos at once.

Fetch only the metrics required for the current view.

Cache stable analytics responses for an appropriate short period where useful.

---

# CLIENT DATA CONSISTENCY

Synchronize client state after mutations such as:

* publish;
* edit metadata;
* visibility change;
* delete;
* save/unsave;
* notification read;
* notification preference change;
* block/unblock.

Do not allow optimistic state to survive a confirmed server rejection.

---

# ERROR HANDLING

Provide consistent handling for:

* authentication failure;
* authorization failure;
* validation errors;
* upload errors;
* processing errors;
* search errors;
* notification errors;
* analytics errors;
* rate limits;
* transient failures;
* not-found states.

Map canonical backend error codes to user-safe messages.

Do not expose internal backend diagnostics.

---

# NETWORK RESILIENCE

Handle:

* temporary offline state;
* request timeout;
* upload interruption;
* stale requests;
* aborted requests;
* reconnect.

Avoid uncontrolled retry loops.

Do not retry irreversible mutations blindly.

---

# ANALYTICS INSTRUMENTATION

Extend the centralized frontend telemetry layer for:

* upload started;
* upload completed;
* upload failed;
* publish started;
* publish completed;
* search submitted;
* search result opened;
* trending content opened;
* notification opened;
* notification marked read;
* analytics page viewed;
* report submitted;
* creator video edited;
* creator video deleted.

Only send event fields required by the backend analytics contract.

Do not log caption contents, private report descriptions, access tokens, push tokens, or other sensitive fields unnecessarily.

---

# OBSERVABILITY

Track frontend operational metrics for:

* upload failure;
* upload duration;
* processing wait visibility;
* search latency;
* search failures;
* notification loading;
* analytics loading;
* creator dashboard errors;
* report submission failures.

Where tracing is supported, propagate request/correlation information using the established client mechanism.

Do not send sensitive request headers to telemetry providers.

---

# SECURITY

Protect against:

* XSS through captions/comments/search content;
* unsafe URLs;
* token exposure;
* client-side privilege assumptions;
* private profile leakage;
* private video leakage;
* push-token exposure;
* report-content leakage;
* unauthorized creator analytics;
* stale cached restricted content.

Never expose private environment secrets through the browser bundle.

---

# TESTING

Create meaningful frontend tests for:

* upload validation;
* upload progress states;
* upload retry;
* draft creation;
* metadata editing;
* hashtag input;
* mention input;
* sound selection;
* visibility changes;
* publish gating;
* publish failure;
* creator content management;
* search;
* search cancellation;
* trending;
* recommendation controls;
* notification list;
* notification read state;
* notification preferences;
* saved content;
* creator analytics;
* report dialog;
* block interactions;
* accessibility.

---

# COMPONENT TESTING

Test reusable components including:

* uploader;
* upload progress;
* draft editor;
* hashtag input;
* mention picker;
* sound picker;
* publish dialog;
* creator content table/grid;
* search result cards;
* notification items;
* notification preferences;
* analytics cards;
* charts;
* report dialog.

Avoid tests that are coupled unnecessarily to implementation details.

---

# END-TO-END TESTING

Where E2E infrastructure exists, cover critical flows such as:

* creator uploads video;
* upload completes;
* processing status appears;
* metadata is edited;
* video is published;
* published video appears in creator content;
* search finds a published video;
* notification appears from a social action;
* notification can be marked read;
* saved content appears in saved view;
* creator analytics displays backend data;
* user submits a report.

Use real backend contracts where the integrated environment is available.

Do not claim a full E2E flow passed if external dependencies were unavailable.

---

# ACCESSIBILITY TESTING

Run automated accessibility validation for:

* upload forms;
* dialogs;
* search;
* notification center;
* analytics views;
* creator-management screens.

Manually inspect critical keyboard and screen-reader flows where automated tooling cannot provide complete assurance.

---

# SECURITY TESTING

Test:

* unsafe caption rendering;
* unsafe hashtag/mention rendering;
* unauthorized creator routes;
* cross-user analytics access through manipulated identifiers;
* private-content leakage;
* push-token exposure;
* report-data exposure;
* unsafe URL handling;
* secret exposure in client bundles.

---

# PERFORMANCE VALIDATION

Validate, where tooling permits:

* upload page memory usage;
* creator dashboard rendering;
* search request behavior;
* notification pagination;
* analytics rendering;
* prolonged feed/search usage;
* redundant request prevention.

Do not claim production-scale browser performance solely from local benchmarks.

---

# DOCUMENTATION

Update repository documentation describing:

* creator upload workflow;
* draft lifecycle;
* media-upload integration;
* publish workflow;
* creator content management;
* search UX;
* notification UX;
* notification preferences;
* saved content;
* creator analytics;
* reporting;
* frontend telemetry;
* testing procedures;
* accessibility requirements;
* responsive behavior.

Document actual implemented behavior.

Do not document unavailable backend capabilities as completed frontend functionality.

---

# IMPLEMENTATION BOUNDARY

This prompt implements:

* creator dashboard;
* creator content management;
* video draft workflow;
* media-file selection;
* upload authorization integration;
* upload progress;
* upload retry;
* processing-state UI;
* metadata editor;
* caption editing;
* hashtag entry;
* mention picker;
* sound/audio selection;
* visibility controls;
* publish workflow;
* publish validation;
* publish error handling;
* creator video library;
* content-management actions;
* search experience;
* creator search;
* hashtag search;
* video search;
* sound search where supported;
* trending/discovery experience;
* richer personalized-feed controls;
* recommendation feedback UI where supported;
* notifications center;
* notification preferences;
* browser push registration where supported by the platform architecture;
* saved/favorite content;
* creator analytics overview;
* creator video analytics;
* reporting dialog;
* safety/blocking UI extensions;
* responsive behavior;
* accessibility;
* performance work;
* frontend telemetry;
* observability;
* unit/component tests;
* applicable E2E tests;
* accessibility tests;
* security tests;
* documentation.

This prompt does **not** implement:

* the mobile application;
* production cloud infrastructure;
* backend search/recommendation implementation;
* backend notification implementation;
* advanced ML recommendation interfaces;
* complete moderation administration;
* full administrative web console;
* paid creator monetization;
* live streaming;
* direct messaging;
* advertising;
* unrelated product categories.

Create only frontend integration points required for later planned project parts.

---

# CROSS-PART COMPATIBILITY

Preserve compatibility with:

* account/authentication backend;
* profile/privacy backend;
* social graph;
* video/content;
* media upload/playback;
* engagement;
* feed/recommendation;
* search/discovery;
* notifications;
* moderation;
* analytics;
* infrastructure;
* mobile;
* QA.

Preserve canonical:

* identifiers;
* timestamps;
* API errors;
* pagination;
* authentication semantics;
* authorization semantics;
* visibility states;
* moderation states;
* video lifecycle states;
* event instrumentation conventions.

Do not invent frontend-specific contract variants.

---

# API INTEGRATION DISCIPLINE

All API access must use the established typed API integration layer.

Centralize:

* authentication;
* request cancellation;
* retries;
* error mapping;
* correlation identifiers;
* response validation where supported.

Do not scatter raw requests through creator/search/analytics components.

Do not silently coerce incompatible response shapes.

---

# EXTERNAL ENVIRONMENT REALISM

This milestone may require:

* backend APIs;
* object storage;
* media-processing services;
* search;
* notification services;
* analytics APIs.

Use available development/test infrastructure.

If an external dependency is unavailable:

* test repository-side behavior using appropriate isolated mechanisms;
* report live-service limitations accurately;
* do not fabricate upload success;
* do not fabricate search results;
* do not fabricate notification delivery;
* do not fabricate analytics data.

---

# VALIDATION

After implementation:

1. Run formatting.
2. Run linting.
3. Run TypeScript type checking.
4. Run unit tests.
5. Run component tests.
6. Run upload-flow tests.
7. Run search tests.
8. Run notification tests.
9. Run analytics tests.
10. Run E2E tests where infrastructure is available.
11. Run accessibility validation.
12. Run security-focused frontend tests.
13. Validate route protection.
14. Validate upload state transitions.
15. Validate publish gating.
16. Validate search cancellation and pagination.
17. Validate notification state synchronization.
18. Validate creator analytics authorization behavior.
19. Inspect browser/runtime errors in relevant test flows.
20. Inspect final diff.
21. Search for exposed secrets.
22. Verify no unrelated major product category was implemented.

Do not claim live upload, push, search, or analytics integration passed unless those services were actually available and tested.

---

# IMPLEMENTATION REPORT

After completing the milestone, provide a concise implementation report identifying:

* files created;
* files modified;
* files deleted, if any;
* creator dashboard;
* creator content management;
* upload workflow;
* draft workflow;
* metadata editor;
* hashtags;
* mentions;
* sounds;
* visibility;
* publish workflow;
* search experience;
* discovery/trending;
* recommendation controls;
* notification center;
* notification preferences;
* browser push registration;
* saved content;
* creator analytics;
* reporting;
* safety/blocking changes;
* API-client changes;
* state-management/data-fetching changes;
* telemetry;
* observability;
* accessibility changes;
* performance changes;
* tests added;
* tests executed;
* validation performed;
* documentation updated;
* compatibility considerations;
* known limitations;
* unavailable external dependencies;
* unresolved issues.

Do not claim live provider behavior unless it was actually validated.

---

# DEFINITION OF DONE

This frontend creator/discovery/notification/analytics milestone is complete only when:

* the repository was inspected;
* creator routes are implemented;
* creator access is authorization-aware;
* creator dashboard is implemented;
* video draft creation works;
* file selection is accessible;
* client-side media validation exists;
* upload authorization integration works;
* upload progress is displayed;
* interrupted uploads have safe retry behavior;
* upload state is distinguished from processing state;
* drafts can be resumed or discarded;
* metadata editing works;
* caption validation works;
* hashtags are handled safely;
* mentions are handled through authoritative identity resolution;
* sound/audio selection works where supported;
* visibility controls work;
* publish gating is correct;
* duplicate publication is prevented;
* publication state is authoritative;
* creator content management is paginated and bounded;
* destructive content actions are confirmed;
* processing states are correctly displayed;
* search is implemented;
* search requests are debounced/cancelled appropriately;
* search categories are rendered through explicit view models;
* privacy and moderation results are respected;
* trending/discovery is implemented;
* personalized-feed controls are implemented against backend contracts;
* recommendation feedback is synchronized where supported;
* notifications center is implemented;
* notification read state works;
* notification preferences work;
* browser push registration works where supported;
* saved content works;
* creator analytics overview works;
* creator video analytics work;
* analytics are bounded and authorized;
* report submission UI exists where supported;
* blocking/safety state is reflected throughout relevant web experiences;
* accessibility requirements are implemented;
* responsive behavior is implemented;
* upload and search performance are handled deliberately;
* telemetry is centralized;
* observability is implemented;
* security protections are implemented;
* unit/component tests exist;
* applicable E2E tests exist;
* accessibility tests exist;
* security tests exist;
* TypeScript validation passes;
* linting/formatting passes where configured;
* documentation reflects actual implementation;
* no fake upload success exists;
* no fake search data exists;
* no fake notification data exists;
* no fabricated analytics exists;
* no hardcoded secrets exist;
* no unrelated major product category was implemented;
* compatibility with backend, mobile, infrastructure, moderation, recommendation, search, analytics, and QA is preserved;
* unavailable external dependencies are reported accurately;
* the implementation report accurately reflects actual work.

Implement **only the current prompt's scope**.

Do not expand this milestone into mobile implementation, infrastructure provisioning, or unrelated product functionality.
