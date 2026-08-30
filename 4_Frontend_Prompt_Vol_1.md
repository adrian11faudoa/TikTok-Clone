You are operating in Senior Engineering Team Mode.

Build the production-ready web frontend for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The frontend must consume the approved backend APIs, authentication contracts, authorization model, video-processing contracts, playback authorization, feed APIs, recommendation APIs, search APIs, messaging, notifications, moderation, creator analytics, advertising, business, privacy, and Project Index.

Do not redesign the backend.

Do not implement backend code.

Do not implement mobile code.

Do not implement infrastructure code.

Do not generate Terraform.

Do not generate Kubernetes manifests.

Do not generate CI/CD workflows.

────────────────────────────────────────

MISSION

Build the production-ready web applications for:

• Consumers
• Creators
• Advertisers where applicable
• Administrators
• Moderators
• Support operators

The web platform must support:

CONSUMER

• Registration
• Login
• Profile
• Creator profiles
• For You feed
• Following feed
• Trending
• Video playback
• Video discovery
• Search
• Hashtags
• Sounds
• Follow/unfollow
• Likes
• Comments
• Replies
• Shares
• Saves
• Collections
• Reposts
• Notifications
• Messaging
• Blocking
• Reporting
• Privacy
• Account settings

CREATOR

• Creator profile
• Upload
• Resumable upload
• Drafts
• Video metadata
• Captions
• Sounds
• Hashtags
• Mentions
• Publication
• Content management
• Analytics
• Comments
• Notifications
• Moderation status
• Rights status

ADVERTISER

• Organization
• Members
• Campaigns
• Ad groups
• Creatives
• Placements
• Targeting
• Budgets
• Analytics

ADMIN / MODERATION / OPERATIONS

• Users
• Creators
• Videos
• Comments
• Reports
• Moderation
• Rights
• Search
• Feed operations
• Recommendation diagnostics where authorized
• Advertising
• Analytics
• Feature flags
• Configuration
• Audit
• Privacy

────────────────────────────────────────

TECHNOLOGY STACK

Framework:

• Next.js
• React
• TypeScript

Styling:

• Tailwind CSS
• shadcn/ui
• CSS variables

Server State:

• TanStack Query

Client State:

• Zustand

Forms:

• React Hook Form
• Zod

Video:

• HTML5 video
• HLS playback through a compatible browser/player abstraction

Animations:

• Framer Motion where appropriate

Icons:

• Lucide React

Charts:

• Recharts

Testing:

• Jest
• React Testing Library
• Playwright
• Accessibility testing tools

────────────────────────────────────────

FRONTEND ARCHITECTURE

Use:

• Next.js App Router
• Route groups
• Feature-first architecture
• Strict TypeScript
• Server Components where appropriate
• Client Components only when interaction requires them
• Typed API clients
• Explicit domain boundaries
• Reusable design system
• TanStack Query for server state
• Zustand for UI/client state
• Secure authentication handling
• URL-driven search/filter state where appropriate

Do not make the entire application a Client Component.

Do not place backend business logic inside UI components.

Do not duplicate authoritative server state unnecessarily.

────────────────────────────────────────

APPLICATION STRUCTURE

Create a scalable structure with:

app/

features/

components/

layouts/

providers/

hooks/

services/

stores/

lib/

config/

types/

utils/

styles/

public/

assets/

tests/

Separate route groups for:

• Consumer
• Creator
• Advertiser
• Administration
• Moderation
• Support

Shared components may be reused only when their semantics genuinely match.

────────────────────────────────────────

NEXT.JS FOUNDATION

Implement:

• App Router
• Route groups
• Shared layouts
• Loading states
• Error boundaries
• Not-found pages
• Suspense
• Metadata
• Open Graph foundations
• Middleware
• Authentication-aware routing

Support:

• Public pages
• Authenticated pages
• Consumer pages
• Creator pages
• Advertiser pages
• Administrative pages

Navigation is never a security boundary.

────────────────────────────────────────

DESIGN SYSTEM

Build reusable accessible components using shadcn/ui and Tailwind.

Include:

• Button
• IconButton
• Input
• Textarea
• Select
• Checkbox
• Radio
• Switch
• Dialog
• Drawer
• Popover
• Dropdown
• Tooltip
• Tabs
• Card
• Badge
• Avatar
• Breadcrumb
• Table
• Pagination
• Skeleton
• Alert
• Toast
• Progress
• Slider
• Calendar
• Date picker
• Command
• Separator
• Scroll area
• Empty state
• Error state
• Loading state
• Video player
• Video card
• Creator card
• Feed item
• Comment tree
• Comment composer
• Share dialog
• Report dialog
• Search box
• Hashtag chip
• Sound card
• Upload dropzone
• Upload progress
• Media preview
• Analytics chart
• Data table

Every component must support:

• Keyboard navigation
• Focus management
• Responsive behavior
• Dark mode
• Accessibility

────────────────────────────────────────

THEME

Support:

• Light
• Dark
• System

Persist user preference.

Respect:

• Reduced motion
• High contrast
• Browser accessibility settings

Use centralized design tokens.

────────────────────────────────────────

API CLIENT

Implement a typed API client supporting:

• Base URL
• Authentication
• Request IDs
• Correlation IDs
• Error normalization
• Timeout
• Cancellation
• Retry where safe
• Pagination
• Cursor pagination
• Upload authorization
• Playback authorization
• WebSocket support

Do not put business rules into the API client.

────────────────────────────────────────

SERVER STATE

Use TanStack Query for:

• Accounts
• Profiles
• Creators
• Followers/following
• Videos
• Upload sessions
• Feed
• Recommendations
• Trending
• Search
• Hashtags
• Sounds
• Likes
• Comments
• Collections
• Reposts
• Notifications
• Messaging
• Moderation state
• Rights state
• Creator analytics
• Advertising
• Administration
• Privacy

Implement:

• Query keys
• Mutations
• Infinite queries
• Caching
• Background refetch
• Optimistic updates where safe
• Invalidation
• Retry
• Error handling

────────────────────────────────────────

CLIENT STATE

Use Zustand for:

• Feed UI state
• Video-player UI state
• Autoplay state
• Muted/unmuted state
• Current feed index
• Search UI
• Upload UI
• Draft editor UI
• Sidebar/drawer state
• Modal state
• Notification panel
• Theme
• Local presentation preferences

Do not make Zustand authoritative for:

• Video publication
• Follow relationship
• Moderation
• Account state
• Payment state
• Privacy state

────────────────────────────────────────

AUTHENTICATION

Implement:

• Registration
• Login
• Logout
• Session restoration
• Email verification
• Password reset
• Password change
• Session expiration
• Token refresh

Prepare for:

• OAuth
• MFA
• Passkeys

Never expose long-lived secrets unnecessarily to browser JavaScript.

────────────────────────────────────────

PUBLIC EXPERIENCE

Create public pages for:

• Home
• Discover
• Search
• Creator profiles
• Public hashtags
• Public sounds
• Public videos where allowed
• Help
• Privacy
• Terms

Private user data must never be indexable publicly.

────────────────────────────────────────

CONSUMER HOME

Primary experience:

• Full-screen or near-full-screen vertical video feed
• For You
• Following
• Trending
• Discovery

Support:

• Autoplay
• Pause/play
• Mute/unmute
• Progress
• Video metadata
• Creator information
• Like
• Comment
• Share
• Save
• Repost
• Follow
• Sound
• Hashtags

────────────────────────────────────────

VIDEO PLAYER

Build a high-performance reusable video player.

Support:

• HLS playback
• Autoplay
• Play/pause
• Mute/unmute
• Volume
• Progress
• Loading
• Buffering
• Retry
• Playback error
• Poster image
• Captions
• Full-screen
• Picture-in-picture where supported

Handle:

• Network interruption
• Stale playback authorization
• Token expiration
• Unsupported media
• CDN failure

Do not bypass backend playback authorization.

────────────────────────────────────────

AUTOPLAY STRATEGY

Implement viewport-aware playback.

Only actively play videos when:

• Visible enough
• Eligible
• Authorized

Pause or release resources when:

• Far outside viewport
• Tab is hidden where appropriate
• User navigates away

Avoid keeping many videos simultaneously decoding.

────────────────────────────────────────

VIDEO PRELOADING

Preload a limited number of nearby videos.

Use:

• Poster immediately
• Current video priority
• Next-video prefetch where appropriate
• Limited concurrent downloads

Do not aggressively prefetch large media.

────────────────────────────────────────

FEED ITEM

Display:

• Video
• Creator
• Caption
• Hashtags
• Sound
• Like count
• Comment count
• Share
• Save
• Repost
• Follow

Support vertical-swipe-like desktop interaction where product requirements justify it.

────────────────────────────────────────

FOR YOU FEED

Consume backend recommendation feed.

Support:

• Cursor pagination
• Infinite loading
• Background candidate fetching
• Seen-content tracking
• Feed refresh
• Pull-to-refresh equivalent where applicable

The client must not implement its own ranking algorithm.

────────────────────────────────────────

FOLLOWING FEED

Display:

• Following creators
• Video feed
• Creator info
• Engagement

Support backend-provided ranking or chronology.

────────────────────────────────────────

TRENDING

Display:

• Trending videos
• Trending hashtags
• Trending sounds
• Trending creators

Support:

• Region
• Time window
• Category

────────────────────────────────────────

FEED ERROR HANDLING

If For You fails:

• Show retry
• Show safe fallback where backend provides it

Do not independently invent content-ranking fallback on the client.

────────────────────────────────────────

PROFILE

Support:

• Avatar
• Username
• Display name
• Bio
• Verified state
• Followers
• Following
• Video grid
• Liked content where public
• Reposts where public
• Follow/unfollow
• Block
• Report

Private content must remain hidden.

────────────────────────────────────────

CREATOR PROFILE

Display:

• Creator identity
• Verification
• Bio
• Follower count
• Videos
• Sounds
• Analytics access for owner
• Creator-specific content

Respect moderation and rights states.

────────────────────────────────────────

FOLLOW / UNFOLLOW

Implement:

• Follow
• Unfollow
• Pending where applicable

Use optimistic UI only when safe.

Reconcile from server after mutation.

────────────────────────────────────────

LIKES

Implement:

• Like
• Unlike
• Count
• Current user state

Provide instant UI feedback where appropriate.

Correct state after reconnect/refetch.

────────────────────────────────────────

COMMENTS

Implement:

• Comment list
• Infinite pagination
• Create comment
• Reply
• Like comment
• Delete own comment
• Pin where authorized
• Report
• Moderation state

Support a performant comment tree.

────────────────────────────────────────

COMMENT COMPOSER

Support:

• Text
• Mentions
• Length validation
• Submit
• Error
• Retry

Do not send invalid data to the backend.

────────────────────────────────────────

SHARES

Support:

• Copy share reference
• Native share API where available
• Internal share
• Share dialog

Private videos must not produce unauthorized public access.

────────────────────────────────────────

SAVES

Implement:

• Save
• Unsave
• Save state

Collections:

• Create
• Rename
• Delete
• Add/remove video
• List

Private collections remain private.

────────────────────────────────────────

REPOSTS

Support:

• Repost
• Remove repost
• Repost indication

Respect privacy and content eligibility.

────────────────────────────────────────

SEARCH

Build search UI for:

• Videos
• Creators
• Hashtags
• Sounds

Support:

• Search input
• Debounce
• Autocomplete
• Recent searches
• Search results
• Filters
• Result categories
• Empty state
• Error state

────────────────────────────────────────

SEARCH RESULTS

Display tabs or filters for:

• Top
• Videos
• Users/Creators
• Hashtags
• Sounds

Use backend ranking.

Do not implement client-side search ranking.

────────────────────────────────────────

HASHTAG PAGES

Display:

• Hashtag
• Trend information
• Video count
• Related content
• Video feed

Only publicly eligible videos may appear.

────────────────────────────────────────

SOUND PAGES

Display:

• Sound
• Creator/attribution
• Duration
• Usage count
• Videos using sound
• Use-sound action where permitted

Respect rights restrictions.

────────────────────────────────────────

NOTIFICATIONS

Support:

• New follower
• Likes
• Comments
• Replies
• Mentions
• Shares
• Messages
• Creator activity
• Moderation actions
• Rights actions
• Security notifications

Use:

• In-app
• Push-compatible deep links where applicable

────────────────────────────────────────

MESSAGING

Build consumer messaging UI.

Support:

• Conversation list
• Conversation
• Message composer
• Delivery
• Read
• Attachments where backend supports them
• Block/report
• Reconnection

Use WebSocket/Socket.IO.

────────────────────────────────────────

REAL-TIME

Implement real-time subscriptions for:

• Messages
• Notifications
• Upload-processing state
• Moderation status where appropriate
• Creator analytics updates where appropriate

Support:

• Authentication
• Reconnection
• Duplicate events
• Stale events
• Connection state
• Graceful degradation

────────────────────────────────────────

UPLOAD EXPERIENCE

Build creator upload workflow:

Select file
→ Upload
→ Processing
→ Edit metadata
→ Preview
→ Captions
→ Hashtags
→ Sound
→ Privacy
→ Publish

Support:

• Drag/drop
• File picker
• Upload progress
• Pause/resume where backend supports it
• Cancel
• Retry
• Processing progress

────────────────────────────────────────

RESUMABLE UPLOAD UI

Support:

• Chunk/multipart progress
• Pause
• Resume
• Retry failed part
• Recover after refresh where backend permits
• Expiration
• Failure

Do not upload video through a normal API request when direct object storage upload is supported.

────────────────────────────────────────

VIDEO EDITING FOUNDATION

For the web creator experience support lightweight editing controls such as:

• Trim metadata where backend/media pipeline supports it
• Cover selection
• Caption editing
• Description
• Hashtags
• Mentions
• Visibility
• Comments enabled/disabled where backend supports it

Do not implement full nonlinear video editing in the browser unless explicitly required.

────────────────────────────────────────

DRAFTS

Support:

• Create draft
• Edit draft
• Save draft
• Resume editing
• Delete draft
• Upload status

Do not lose draft metadata because of temporary network failure.

────────────────────────────────────────

PUBLICATION

Creator should see:

• Processing state
• Moderation state
• Rights state
• Publication state

The client must not publish a video until backend requirements are satisfied.

────────────────────────────────────────

CREATOR ANALYTICS

Display:

• Views
• Watch time
• Completion rate
• Average watch duration
• Rewatch
• Likes
• Comments
• Shares
• Saves
• Follower growth
• Traffic sources
• Sound usage
• Regional summaries

Use charts and date-range filters.

Do not expose internal recommendation scores.

────────────────────────────────────────

ADVERTISER APPLICATION

Support:

• Advertiser organization
• Dashboard
• Campaigns
• Ad groups
• Creatives
• Placements
• Targeting
• Budgets
• Scheduling
• Frequency caps
• Approval state
• Analytics

────────────────────────────────────────

CAMPAIGN MANAGEMENT

Implement UI for:

• Create
• Draft
• Submit for review
• Pause
• Resume
• Complete
• Archive

Show backend-authoritative campaign state.

────────────────────────────────────────

AD CREATIVE

Support:

• Upload creative
• Preview
• Text
• CTA
• Destination
• Version
• Moderation status
• Approval status

Do not allow unapproved creative to be treated as active.

────────────────────────────────────────

AD ANALYTICS

Display:

• Impressions
• Clicks
• Video starts
• Video completions
• Conversion references
• Spend
• Budget status

Use server-provided aggregates.

────────────────────────────────────────

ADMIN APPLICATION

Create an enterprise admin console.

Sections:

• Dashboard
• Users
• Creators
• Videos
• Comments
• Reports
• Moderation
• Rights
• Search
• Feed diagnostics
• Recommendation diagnostics
• Advertising
• Analytics
• Feature flags
• Configuration
• Audit
• Privacy

────────────────────────────────────────

ADMIN DASHBOARD

Display:

• Active users
• Upload rate
• Processing backlog
• Feed latency
• Search latency
• Moderation backlog
• Messaging health
• Notification health
• Advertising health
• Error rate

Use charts, cards, tables, filters.

────────────────────────────────────────

USER ADMINISTRATION

Support authorized operations:

• Search user
• View profile
• View account state
• Suspend
• Restore
• View related moderation/support references

Do not expose private behavioral or message data unnecessarily.

────────────────────────────────────────

CREATOR ADMINISTRATION

Support:

• Search creator
• View verification
• View content
• Suspend/reinstate
• Review reports
• Review rights status

Sensitive verification information requires appropriate permissions.

────────────────────────────────────────

CONTENT MODERATION UI

Display:

• Moderation queue
• Content
• Reason
• Policy
• Evidence
• Automated result
• Case history
• Actions
• Appeals

Support:

• Approve
• Restrict
• Remove
• Restore

Every high-impact action requires confirmation and reason where backend requires it.

────────────────────────────────────────

COPYRIGHT / RIGHTS UI

Support:

• Claims
• Content
• Rights status
• Region
• Effective dates
• Takedown
• Appeal
• Restoration

Use backend-authoritative rights state.

────────────────────────────────────────

REPORTING UI

Support:

• Video reports
• Comment reports
• User reports
• Message reports
• Sound/hashtag reports

Display status:

• Submitted
• Under review
• Action taken
• Dismissed
• Resolved

────────────────────────────────────────

FEATURE FLAGS

Admin UI:

• Flag list
• Status
• Rollout percentage
• Region
• Environment
• Cohort
• Version history
• Kill switch
• Audit

Never let the client decide whether a protected feature is authorized.

────────────────────────────────────────

SYSTEM CONFIGURATION

Support authorized admins:

• View configuration
• Edit
• Validate
• Submit for approval
• Activate
• Roll back
• View history

Never display secrets.

────────────────────────────────────────

AUDIT

Support:

• Search
• Filter
• Actor
• Action
• Resource
• Region
• Time
• Correlation ID

Audit records must be read-only.

────────────────────────────────────────

PRIVACY

Consumer UI:

• Privacy settings
• Data controls
• Personalized recommendations controls
• Advertising preferences
• Data export
• Account deletion

Export/deletion status must be backend-authoritative.

────────────────────────────────────────

DATA EXPORT

Support:

• Request export
• Scope
• Status
• Progress
• Download when ready
• Expiration

Use secure temporary downloads.

────────────────────────────────────────

ACCOUNT DELETION

Implement:

• Request deletion
• Confirmation
• Re-authentication where required
• Status
• Cancellation where backend allows

Clearly communicate retention exceptions where applicable.

────────────────────────────────────────

ACCESSIBILITY

Target WCAG 2.2 AA.

Support:

• Keyboard navigation
• Screen readers
• Focus management
• Semantic HTML
• Accessible dialogs
• Accessible tables
• Accessible charts
• Captions
• Audio descriptions or equivalent alternatives where available
• Reduced motion
• High contrast

The feed must remain usable without relying exclusively on gesture or video.

────────────────────────────────────────

LOCALIZATION

Support:

• Multiple languages
• Locale selection
• Date/time formatting
• Number formatting
• Relative time
• Currency
• RTL

Do not hard-code customer-facing strings inside components.

────────────────────────────────────────

RESPONSIVE DESIGN

Support:

• Desktop
• Tablet
• Mobile web

Prioritize:

• Feed
• Search
• Profiles
• Video player
• Upload
• Analytics
• Administration

────────────────────────────────────────

SEO

Public pages may be indexable:

• Public creator profiles
• Public hashtags
• Public sounds
• Public videos
• Help pages

Do not index:

• Private profiles
• Private collections
• Private videos
• Messages
• Notifications
• Moderation
• Admin pages
• Privacy pages containing private data

────────────────────────────────────────

PERFORMANCE

Optimize:

• Initial load
• Feed scrolling
• Video startup
• Search
• Profile
• Comments
• Creator analytics
• Admin tables

Use:

• Server Components
• Suspense
• Streaming
• Code splitting
• Dynamic imports
• Image optimization
• Virtualized lists
• Query caching
• Lazy loading
• Limited video preloading

────────────────────────────────────────

VIDEO PERFORMANCE

Optimize:

• First-frame latency
• Buffering
• CDN cache usage
• Poster display
• Source switching
• Playback cleanup

Avoid:

• Multiple simultaneous active videos
• Large unnecessary preloads
• API server media proxying

────────────────────────────────────────

ERROR HANDLING

Handle:

• Authentication failure
• Video unavailable
• Playback authorization failure
• Feed failure
• Search failure
• Upload failure
• Processing failure
• Comment failure
• Messaging failure
• Notification failure
• Moderation failure
• Rights restriction
• Privacy operation failure

Provide clear recovery actions.

────────────────────────────────────────

SECURITY

Implement:

• Protected routes
• Permission-aware navigation
• Safe URL handling
• XSS-safe rendering
• Secure upload flow
• Secure playback flow
• Sensitive-data masking
• Safe report downloads
• WebSocket authentication

Frontend checks never replace backend authorization.

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Feed state
• Video-player state
• Upload state
• Draft state
• Permissions
• Validation
• Formatting
• Utility functions

COMPONENT TESTS

Test:

• Video player
• Feed item
• Comments
• Search
• Profile
• Upload
• Analytics
• Messaging
• Notifications
• Moderation
• Advertising

INTEGRATION TESTS

Test:

• API client
• Authentication
• TanStack Query
• WebSockets
• Upload
• Playback authorization
• Feed
• Search
• Messaging

END-TO-END

CONSUMER:

• Register
• Login
• Browse For You
• Like
• Comment
• Follow
• Search
• Save
• Share
• Message
• Report
• Privacy settings

CREATOR:

• Create creator profile
• Upload video
• Resume upload
• Edit metadata
• Publish
• View analytics
• Manage comments

ADVERTISER:

• Create campaign
• Upload creative
• Submit
• View analytics

ADMIN:

• Login
• Search user
• Moderate content
• Manage rights
• Configure feature flag
• View audit

────────────────────────────────────────

ACCESSIBILITY TESTING

Test:

• Keyboard
• Screen reader
• Focus
• Captions
• Forms
• Dialogs
• Tables
• Charts
• Feed navigation
• Video controls

────────────────────────────────────────

PERFORMANCE TESTING

Measure:

• First contentful paint
• Largest contentful paint
• Time to interactive where relevant
• Feed frame rate
• Video first-frame latency
• Search latency
• Upload UI responsiveness
• Admin table performance

────────────────────────────────────────

PROJECT INDEX

Update the frontend Project Index with:

• Applications
• Routes
• Consumer features
• Creator features
• Advertiser features
• Admin features
• Components
• Layouts
• Hooks
• Stores
• Queries
• Mutations
• API client
• WebSocket client
• Video player
• Upload subsystem
• Feed
• Recommendations
• Search
• Hashtags
• Sounds
• Profiles
• Engagement
• Comments
• Collections
• Messaging
• Notifications
• Moderation
• Rights
• Advertising
• Analytics
• Privacy
• Settings
• Accessibility
• Localization
• Tests
• Dependencies
• Generated files
• Modified files
• Remaining work
• Current milestone

────────────────────────────────────────

IMPLEMENTATION MILESTONES

FRONTEND MILESTONE 1

Next.js foundation, route groups, design system, API client, providers, authentication, themes, error handling, configuration, and accessibility foundations.

FRONTEND MILESTONE 2

Consumer home, For You feed, Following feed, Trending, video player, autoplay, feed pagination, playback authorization, and video interaction controls.

FRONTEND MILESTONE 3

Profiles, creators, follows, likes, comments, replies, shares, saves, collections, reposts, hashtags, and sounds.

FRONTEND MILESTONE 4

Search, autocomplete, search results, creator discovery, hashtag discovery, sound discovery, notifications, and deep-link handling.

FRONTEND MILESTONE 5

Messaging, real-time WebSocket integration, blocking, reporting, moderation status, rights status, and privacy controls.

FRONTEND MILESTONE 6

Creator upload, resumable upload, drafts, media preview, metadata editing, captions, hashtags, mentions, sound selection, publication, and processing status.

FRONTEND MILESTONE 7

Creator analytics, content management, advertiser dashboard, campaigns, ad groups, creatives, budgets, targeting, and advertising analytics.

FRONTEND MILESTONE 8

Administration, moderation, reporting, rights, user/creator management, feature flags, configuration, audit, privacy operations, and operational dashboards.

FRONTEND MILESTONE 9

Advanced performance, responsive optimization, accessibility, localization, SEO, video optimization, error recovery, and security hardening.

FRONTEND MILESTONE 10

Complete component tests, integration tests, E2E tests, real-time tests, accessibility tests, performance tests, security validation, regression testing, and production-readiness certification.

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

This volume covers the production web frontend for:

• Consumers
• Creators
• Advertisers
• Administration
• Moderation
• Support-oriented interfaces

Do not implement:

• Backend
• Mobile
• Infrastructure
• Terraform
• Kubernetes
• CI/CD

Consume the approved backend contracts exactly.

Do not redesign APIs or database structures.

────────────────────────────────────────

QUALITY BAR

Treat the web application as a production global social-video platform supporting:

• Hundreds of millions of users
• Millions of creators
• Billions of video impressions
• Massive feed traffic
• Massive video playback
• Large upload traffic
• Large messaging traffic
• Large analytics workloads
• Multiple regions
• Multiple languages
• Strict accessibility
• Strict privacy
• Strict security

Prioritize:

• Video startup performance
• Feed responsiveness
• Reliable uploads
• Accurate server-state synchronization
• Secure playback
• Accessibility
• Responsive design
• Maintainability
• Scalability
• Production readiness
