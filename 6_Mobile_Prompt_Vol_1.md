You are operating in Senior Engineering Team Mode.

Build the production-ready mobile applications for an enterprise-scale global short-form video social platform comparable in architectural scope to TikTok.

The platform is an original implementation.

Do not copy proprietary source code, internal architecture, branding, confidential implementation details, proprietary algorithms, recommendation models, or private implementation details from TikTok or any other company.

This prompt is completely independent and may be executed in a separate conversation.

The mobile applications must consume the approved backend APIs, authentication contracts, video-upload contracts, playback authorization, feed APIs, recommendation APIs, search APIs, engagement APIs, messaging APIs, notification APIs, moderation APIs, rights APIs, creator analytics APIs, advertising APIs, privacy APIs, and Project Index.

Do not redesign the backend.

Do not implement backend code.

Do not implement web frontend code.

Do not implement infrastructure code.

Do not generate Terraform.

Do not generate Kubernetes manifests.

Do not generate CI/CD workflows.

────────────────────────────────────────

MISSION

Build production-ready iOS and Android mobile applications for:

• Consumers
• Creators

The applications must support:

CONSUMER

• Registration
• Login
• Session restoration
• Profiles
• Creator profiles
• For You feed
• Following feed
• Trending
• Vertical video playback
• Autoplay
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
• Direct messaging
• Blocking
• Reporting
• Privacy
• Account settings
• Content sharing
• Moderation status
• Rights restrictions

CREATOR

• Creator profile
• Creator verification status
• Video recording/import
• Drafts
• Upload
• Resumable upload
• Video metadata
• Captions
• Hashtags
• Mentions
• Sounds
• Publication
• Content management
• Analytics
• Comments
• Notifications
• Moderation status
• Rights status

The applications must be:

• Fast
• Smooth
• Battery-conscious
• Data-efficient
• Secure
• Accessible
• Offline-aware
• Network-resilient
• Production-ready

────────────────────────────────────────

TECHNOLOGY STACK

Framework:

• React Native
• Expo
• TypeScript

Navigation:

• React Navigation

Server State:

• TanStack Query

Client State:

• Zustand

Forms:

• React Hook Form
• Zod

Secure Storage:

• Expo Secure Store or approved platform-secure storage

Local persistence:

• SQLite or approved mobile persistence layer

Video:

• Native-capable video playback through an approved React Native video abstraction

Maps:

• Not a core feature; use approved platform abstraction only where needed

Camera:

• Expo Camera or approved implementation

Media:

• Expo Image Picker / Media Library or approved abstraction

Notifications:

• Firebase Cloud Messaging
• Apple Push Notification Service

Real-time:

• WebSockets
• Socket.IO client where appropriate

Testing:

• Jest
• React Native Testing Library
• Detox or approved E2E framework

────────────────────────────────────────

MOBILE ARCHITECTURE

Use:

• Feature-first architecture
• Strict TypeScript
• Reusable components
• Shared domain presentation
• Explicit navigation boundaries
• Platform abstraction
• Secure-storage boundaries
• Local persistence boundaries
• Server-state/client-state separation
• Network abstraction
• Media abstraction
• Real-time abstraction

Do not place backend business logic inside screens.

Do not duplicate server-state authority unnecessarily.

Do not use Zustand as the authoritative source for:

• Feed
• Video publication
• Moderation
• Rights
• Account
• Recommendation
• Messaging history

────────────────────────────────────────

APPLICATION STRUCTURE

Create a scalable structure:

src/

features/

components/

navigation/

screens/

layouts/

providers/

hooks/

services/

stores/

database/

storage/

network/

media/

video/

camera/

upload/

realtime/

notifications/

config/

types/

utils/

assets/

tests/

Separate feature modules for:

• Authentication
• Profiles
• Creators
• Feed
• Video
• Discovery
• Search
• Hashtags
• Sounds
• Engagement
• Comments
• Collections
• Messaging
• Notifications
• Moderation
• Rights
• Creator
• Upload
• Drafts
• Analytics
• Privacy
• Settings

────────────────────────────────────────

EXPO FOUNDATION

Implement:

• Expo configuration
• iOS configuration
• Android configuration
• Bundle identifiers
• App metadata
• Deep links
• Notification configuration
• Camera configuration
• Media-library configuration
• Secure-storage configuration
• Environment configuration

Separate:

• Development
• Test
• Staging
• Production

Do not put secrets in client configuration.

────────────────────────────────────────

NAVIGATION

Implement React Navigation.

CONSUMER:

• Home
• Discover
• Search
• Activity
• Inbox
• Profile
• Video
• Comments
• Notifications
• Settings

CREATOR:

• Creator Home
• Camera
• Upload
• Drafts
• Content
• Analytics
• Comments
• Profile
• Settings

Support:

• Stack
• Tabs
• Modals
• Nested navigation
• Protected routes
• Deep links

Navigation is never a security boundary.

────────────────────────────────────────

DESIGN SYSTEM

Create reusable mobile components:

• Button
• IconButton
• TextInput
• SearchInput
• Avatar
• Badge
• Sheet
• BottomSheet
• Modal
• Dialog
• Toast
• Snackbar
• Tabs
• SegmentedControl
• Chip
• Card
• ListItem
• AvatarGroup
• Progress
• Skeleton
• EmptyState
• ErrorState
• LoadingState
• VideoPlayer
• FeedItem
• CommentRow
• CommentComposer
• CreatorHeader
• FollowButton
• LikeButton
• ShareSheet
• SaveButton
• ReportSheet
• UploadProgress
• MediaPreview
• AnalyticsCard

Support:

• Safe areas
• Dynamic Type
• Dark mode
• Accessibility
• Haptics where appropriate

────────────────────────────────────────

THEME

Support:

• Light
• Dark
• System

Persist preference.

Respect:

• Reduced motion
• High contrast
• Dynamic Type
• Platform accessibility settings

────────────────────────────────────────

AUTHENTICATION

Implement:

• Registration
• Login
• Logout
• Session restoration
• Token refresh
• Email verification
• Password reset
• Password change
• Device registration
• Session expiration

Prepare for:

• OAuth
• MFA
• Passkeys

Store authentication credentials only in secure platform storage.

────────────────────────────────────────

NETWORKING

Implement typed API client supporting:

• HTTPS
• Authentication
• Request ID
• Correlation ID
• Timeouts
• Cancellation
• Retry where safe
• Error normalization
• Connectivity detection

Never blindly retry:

• Content publication
• Account mutations
• Financial operations
• Other non-idempotent actions

────────────────────────────────────────

CONNECTIVITY

Handle:

• Online
• Offline
• Weak network
• High latency
• Packet loss
• Wi-Fi/cellular transition
• Reconnect

On reconnect:

1. Refresh critical server state.
2. Reconcile feed state.
3. Reconcile current conversation state.
4. Reconcile upload state.
5. Re-establish WebSocket subscriptions.
6. Reconcile pending safe mutations.

Do not fabricate server state while offline.

────────────────────────────────────────

SECURE STORAGE

Use secure storage for:

• Access credentials
• Refresh credentials
• Device identity
• Other approved secrets

Use ordinary local persistence only for:

• Non-sensitive cache
• Preferences
• Safe draft metadata
• Feed presentation state
• Offline metadata

Never store passwords.

────────────────────────────────────────

VIDEO PLAYER

Build a production-ready vertical short-video player.

Support:

• HLS or approved adaptive playback
• Autoplay
• Play/pause
• Mute/unmute
• Volume
• Progress
• Buffering state
• Error state
• Poster image
• Captions
• Fullscreen
• Picture-in-picture where supported
• Playback authorization refresh

────────────────────────────────────────

VERTICAL FEED

Implement TikTok-style vertical browsing.

Support:

• One active video at a time
• Gesture/page transitions
• Preload nearby content
• Autoplay
• Pause when backgrounded
• Pause when not visible
• Smooth transitions
• Limited prefetching

Avoid decoding many videos simultaneously.

────────────────────────────────────────

VIDEO PRELOADING

Implement adaptive preloading.

Prioritize:

1. Current video
2. Next video
3. Previous video where appropriate

Use:

• Network conditions
• Device capabilities
• Available memory
• Playback state

Avoid excessive cellular data usage.

────────────────────────────────────────

PLAYBACK AUTHORIZATION

Obtain playback authorization from backend.

Handle:

• Token expiration
• Authorization denial
• Content removal
• Rights restriction
• Region restriction
• Moderation restriction

Never bypass secure playback controls.

────────────────────────────────────────

FOR YOU FEED

Consume backend For You feed.

Support:

• Infinite scrolling
• Page cursor
• Pull-to-refresh
• Candidate prefetch
• Seen-content tracking
• Recommendation updates

The client must not independently rank feed items.

────────────────────────────────────────

FOLLOWING FEED

Display content from followed creators.

Support:

• Pagination
• Refresh
• Follow/unfollow
• Engagement

────────────────────────────────────────

TRENDING

Display:

• Trending videos
• Trending creators
• Trending hashtags
• Trending sounds

Respect region and backend eligibility.

────────────────────────────────────────

DISCOVERY

Support discovery surfaces for:

• Creators
• Hashtags
• Sounds
• Videos
• Trending topics

────────────────────────────────────────

VIDEO METADATA UI

Display:

• Caption
• Hashtags
• Creator
• Sound
• Like count
• Comment count
• Share count
• Save state
• Repost state

Only display server-provided eligible metadata.

────────────────────────────────────────

LIKES

Implement:

• Like
• Unlike
• Like count
• Current user state

Use optimistic UI only when safe.

Reconcile with backend state.

────────────────────────────────────────

COMMENTS

Support:

• Comment list
• Infinite loading
• Comment creation
• Replies
• Comment likes
• Pin state where provided
• Delete own comment
• Report

Use a virtualized comment list.

────────────────────────────────────────

COMMENT COMPOSER

Support:

• Text input
• Mentions
• Validation
• Submit
• Retry
• Character count where required

Handle keyboard and bottom-sheet behavior correctly on iOS and Android.

────────────────────────────────────────

SHARES

Support:

• Native share sheet
• Copy share reference
• Internal sharing where supported

Private/restricted content must not receive unauthorized public share access.

────────────────────────────────────────

SAVES

Support:

• Save
• Unsave
• Collection selection

Collections:

• Create
• Rename
• Delete
• Add
• Remove

────────────────────────────────────────

REPOSTS

Support:

• Repost
• Remove repost
• Repost state

────────────────────────────────────────

PROFILES

Support:

• Avatar
• Username
• Display name
• Bio
• Verification
• Followers
• Following
• Content
• Reposts where public
• Follow/unfollow
• Block
• Report

Respect privacy and visibility.

────────────────────────────────────────

CREATOR PROFILES

Display:

• Verified status
• Creator identity
• Content
• Follower count
• Sounds where applicable
• Analytics access for owner

────────────────────────────────────────

FOLLOWING

Support:

• Follow
• Unfollow
• Follower state
• Optimistic state where safe

Reconcile after server response.

────────────────────────────────────────

SEARCH

Implement:

• Search input
• Autocomplete
• Recent searches
• Video results
• Creator results
• Hashtag results
• Sound results

Debounce queries.

Cancel stale requests.

────────────────────────────────────────

HASHTAGS

Display:

• Hashtag
• Video feed
• Trending metadata
• Related hashtags where available

Only display eligible public content.

────────────────────────────────────────

SOUNDS

Display:

• Sound
• Creator/attribution
• Usage count
• Video feed
• Use sound action
• Rights availability

Do not present restricted sounds as available for use.

────────────────────────────────────────

MESSAGING

Implement direct messaging.

Support:

• Conversation list
• Conversation
• Messages
• Send
• Delivery state
• Read state
• Attachments where approved
• Block/report

Use WebSocket/Socket.IO where appropriate.

────────────────────────────────────────

REAL-TIME MESSAGING

Handle:

• Connect
• Authenticate
• Subscribe
• Message delivery
• Read state
• Disconnect
• Reconnect
• Duplicate events
• Stale events

When disconnected:

• Persist safe local UI state
• Recover from server
• Do not invent missing messages

────────────────────────────────────────

NOTIFICATIONS

Support:

• Push permissions
• Device token registration
• Foreground notifications
• Background notifications
• Terminated-app notifications
• Notification center
• Badge count
• Deep links

Types:

• Follows
• Likes
• Comments
• Replies
• Mentions
• Shares
• Messages
• Creator updates
• Moderation
• Rights
• Security
• System

────────────────────────────────────────

BLOCKING

Support:

• Block
• Unblock
• Blocked list

After block:

• Stop messaging
• Stop unwanted notifications
• Stop follow interactions
• Hide blocked content where backend indicates

Do not rely only on local filtering.

────────────────────────────────────────

REPORTING

Support reporting:

• Video
• Creator
• Profile
• Comment
• Message
• Sound
• Hashtag

Use backend report categories.

────────────────────────────────────────

MODERATION STATUS

Display appropriate states when content is:

• Under review
• Restricted
• Removed
• Restored

Do not expose internal moderation details unnecessarily.

────────────────────────────────────────

RIGHTS STATUS

Handle:

• Sound restriction
• Video restriction
• Regional unavailability
• Content removal

Update playback and publishing UI according to server state.

────────────────────────────────────────

CREATOR CAMERA

Implement creator capture flow:

• Camera preview
• Record
• Pause
• Resume
• Stop
• Camera switch
• Flash
• Timer where appropriate
• Video duration limit
• Preview

Use device capabilities safely.

────────────────────────────────────────

MEDIA PICKER

Support:

• Gallery
• Camera roll
• Video selection
• Multiple media where product flow supports it

Validate:

• File type
• Size
• Duration
• Resolution

────────────────────────────────────────

DRAFTS

Support:

• Create draft
• Edit draft
• Save draft
• Resume
• Delete
• Upload later

Persist safe draft state locally.

Do not store large source videos permanently in an uncontrolled local database.

────────────────────────────────────────

UPLOAD

Support:

• Upload initialization
• Signed upload
• Multipart/resumable upload
• Progress
• Pause
• Resume
• Retry
• Cancel
• Expiration
• Completion

Upload actual video bytes directly to object storage where backend architecture supports it.

────────────────────────────────────────

UPLOAD RESILIENCE

If connection breaks:

• Preserve upload session
• Persist safe metadata needed for resume
• Resume when possible
• Revalidate authorization
• Handle expired upload sessions

Do not create duplicate videos because of retries.

────────────────────────────────────────

CREATOR PUBLISHING

Support:

• Video preview
• Caption
• Hashtags
• Mentions
• Sound
• Cover
• Visibility
• Comments settings where supported
• Publication

Publication must remain server-authoritative.

────────────────────────────────────────

PROCESSING STATUS

Display:

• Uploading
• Processing
• Moderation
• Ready
• Published
• Failed

Support retry for recoverable errors.

────────────────────────────────────────

CAPTIONS

Support:

• Caption preview
• Caption editing
• Caption language
• Auto-generated caption status
• Accessibility presentation

────────────────────────────────────────

CREATOR ANALYTICS

Display:

• Views
• Watch time
• Completion
• Average watch duration
• Likes
• Comments
• Shares
• Saves
• Followers
• Traffic source
• Sound usage

Support:

• Date range
• Charts
• Content-level analytics

Do not expose private user-level recommendation data.

────────────────────────────────────────

PRIVACY

Implement:

• Privacy settings
• Account settings
• Recommendation controls where supported
• Advertising controls where supported
• Data export request
• Account deletion request

Use backend-authoritative status.

────────────────────────────────────────

DEEP LINKS

Support:

• Video
• Creator
• Hashtag
• Sound
• Profile
• Message
• Notification
• Moderation
• Rights
• Privacy

After opening a deep link:

• Validate authentication
• Validate resource availability
• Validate authorization

Never trust deep-link parameters as security authority.

────────────────────────────────────────

BACKGROUND / FOREGROUND

Handle:

• App background
• App foreground
• Screen lock
• Audio interruption
• Call interruption
• Low-memory termination
• Notification open

When returning to foreground:

• Reconcile critical server state
• Restore player safely
• Reconnect WebSocket
• Refresh authorization where necessary

────────────────────────────────────────

BATTERY OPTIMIZATION

Minimize:

• Background network activity
• Aggressive polling
• Continuous media prefetch
• Unnecessary location usage
• Excessive analytics

Adapt behavior to:

• Network
• Battery
• Device capability

────────────────────────────────────────

DATA USAGE OPTIMIZATION

Support:

• Reduced data mode
• Limited video prefetch
• Adaptive quality
• Image compression
• Background-download restrictions

Do not degrade critical functionality without clear indication.

────────────────────────────────────────

MEMORY MANAGEMENT

Prevent:

• Retaining many video players
• Large decoded-image caches
• Unbounded feed state
• Unbounded comment state
• Unbounded message history

Use:

• Virtualized lists
• Resource cleanup
• Cache limits
• Lifecycle-aware components

────────────────────────────────────────

ACCESSIBILITY

Support:

• VoiceOver
• TalkBack
• Dynamic Type
• Screen reader labels
• Accessible actions
• Large touch targets
• Captions
• Reduced motion
• High contrast
• Accessible alternatives for video-driven content

The core feed must remain usable with accessibility services.

────────────────────────────────────────

LOCALIZATION

Support:

• Multiple languages
• Locale selection
• Date/time
• Number formatting
• Relative time
• RTL
• Localized validation
• Localized notifications

Do not hard-code user-facing strings.

────────────────────────────────────────

ERROR HANDLING

Handle:

• Network failure
• Playback failure
• Authorization failure
• Content removal
• Upload failure
• Processing failure
• Search failure
• Message failure
• Notification failure
• Moderation restriction
• Rights restriction
• Session expiration
• Storage failure

Provide clear recovery actions.

────────────────────────────────────────

SECURITY

Implement:

• Secure storage
• Protected navigation
• Safe deep links
• Secure upload flow
• Secure playback flow
• Sensitive-data minimization
• Device registration
• Safe local persistence
• Token handling
• Network security

Never store:

• Passwords
• API secrets
• Permanent playback credentials
• Cloud credentials

────────────────────────────────────────

TESTING

UNIT TESTS

Test:

• Feed state
• Player state
• Upload state
• Draft state
• Search state
• Message state
• Notification state
• Permission handling
• Validation
• Reconciliation

COMPONENT TESTS

Test:

• Video player
• Feed item
• Comments
• Search
• Profile
• Creator profile
• Upload
• Camera controls
• Analytics
• Messaging
• Notifications
• Report flow
• Privacy flow

INTEGRATION TESTS

Test:

• Authentication
• API client
• TanStack Query
• WebSockets
• Upload
• Playback authorization
• Notifications
• Deep links
• Background/foreground transitions

E2E TESTS

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
• Block
• Privacy request

CREATOR:

• Creator onboarding
• Camera
• Record
• Import
• Draft
• Upload
• Resume upload
• Edit metadata
• Publish
• View analytics
• Manage comments

────────────────────────────────────────

NETWORK TESTING

Test:

• Offline
• Weak network
• High latency
• Packet loss
• Reconnect
• Wi-Fi/cellular transition

Verify:

• No duplicate upload
• No duplicate publication
• Correct feed reconciliation
• Correct message reconciliation
• Safe retry behavior

────────────────────────────────────────

PLATFORM TESTING

Test on:

• Supported iOS versions
• Supported Android versions
• Small devices
• Large devices
• Different aspect ratios
• Low-memory devices where practical
• Different network conditions

────────────────────────────────────────

ACCESSIBILITY TESTING

Test:

• VoiceOver
• TalkBack
• Dynamic Type
• Large text
• Screen-reader labels
• Captions
• Accessible actions
• Focus
• Reduced motion

────────────────────────────────────────

PERFORMANCE TESTING

Measure:

• Cold startup
• Warm startup
• Feed first-content latency
• Video first-frame latency
• Scroll/frame performance
• Memory
• Upload throughput
• Search latency
• Message latency
• Battery impact
• Network usage

────────────────────────────────────────

DOCUMENTATION

Generate:

• Mobile architecture
• Consumer application
• Creator application
• Navigation
• Authentication
• Video player
• Feed
• Recommendation consumption
• Search
• Hashtags
• Sounds
• Engagement
• Comments
• Messaging
• Notifications
• Blocking
• Reporting
• Moderation
• Rights
• Camera
• Media picker
• Drafts
• Upload
• Resumable upload
• Publication
• Creator analytics
• Privacy
• Deep links
• Background/foreground
• Battery optimization
• Data usage
• Memory management
• Accessibility
• Localization
• Security
• Performance
• Testing

────────────────────────────────────────

PROJECT INDEX

Update the mobile Project Index with:

• Consumer app
• Creator app
• Screens
• Navigation
• Features
• Components
• Hooks
• Stores
• Queries
• API client
• WebSocket client
• Video player
• Feed
• Discovery
• Search
• Hashtags
• Sounds
• Engagement
• Comments
• Collections
• Reposts
• Messaging
• Notifications
• Blocking
• Reporting
• Moderation
• Rights
• Camera
• Media picker
• Drafts
• Upload
• Resumable upload
• Publication
• Analytics
• Privacy
• Deep links
• Secure storage
• Local persistence
• Tests
• Accessibility
• Performance
• Dependencies
• Generated files
• Modified files
• Remaining work
• Current milestone

────────────────────────────────────────

IMPLEMENTATION MILESTONES

MOBILE MILESTONE 1

Expo foundation, navigation, design system, API client, authentication, secure storage, providers, theme, connectivity detection, and error handling.

MOBILE MILESTONE 2

Consumer home, vertical For You feed, Following feed, Trending, video player, autoplay, preloading, playback authorization, and feed pagination.

MOBILE MILESTONE 3

Profiles, creators, follows, likes, comments, replies, shares, saves, collections, reposts, hashtags, sounds, and discovery.

MOBILE MILESTONE 4

Search, autocomplete, creator discovery, notification center, push notifications, deep links, and direct messaging foundation.

MOBILE MILESTONE 5

Real-time messaging, WebSocket synchronization, blocking, reporting, moderation status, rights status, privacy settings, and account settings.

MOBILE MILESTONE 6

Creator camera, media picker, drafts, upload sessions, resumable uploads, media preview, metadata editing, captions, hashtags, mentions, sounds, and publication.

MOBILE MILESTONE 7

Creator content management, creator analytics, advanced upload recovery, performance optimization, memory management, battery optimization, and data-usage controls.

MOBILE MILESTONE 8

Accessibility, localization, security hardening, deep-link hardening, offline/network resilience, integration tests, E2E tests, platform testing, performance testing, and production readiness.

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

This volume covers the mobile consumer and creator applications.

Do not implement:

• Backend
• Web frontend
• Infrastructure
• Terraform
• Kubernetes
• CI/CD

Consume the approved backend contracts exactly.

Do not redesign API or database contracts.

────────────────────────────────────────

QUALITY BAR

Treat these applications as production-grade global social-video clients supporting:

• Hundreds of millions of users
• Millions of creators
• Billions of video impressions
• Massive feed traffic
• High video playback
• Large upload traffic
• Large messaging traffic
• Multiple network conditions
• Multiple device capabilities
• Multiple regions
• Strict privacy
• Strict security
• Strict accessibility

Prioritize:

• Smooth video playback
• Fast feed startup
• Reliable uploads
• Correct real-time synchronization
• Efficient memory use
• Battery efficiency
• Data efficiency
• Secure storage
• Accessibility
• Resilience
• Maintainability
• Production readiness
