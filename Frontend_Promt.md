Using the approved Architecture Blueprint and the Master Prompt above:

Begin frontend and mobile implementation ONLY.

Do NOT generate backend code.

Do NOT generate infrastructure code.

Do NOT redesign APIs.

Do NOT redesign the database.

Assume the backend implementation already exists and consume its published API contracts exactly as defined in the Architecture Blueprint.

The application must achieve App Store / Google Play flagship quality comparable to:

- TikTok
- Instagram Reels
- YouTube Shorts

Every implementation must be production-ready, accessible, responsive, highly performant, and maintainable.

Generate code incrementally according to the Master Prompt milestone strategy.

──────────────────────────────────────

MISSION

Build the complete production-ready mobile application and creator interfaces for the enterprise short-form video platform.

The application must deliver a world-class user experience with fluid animations, seamless video playback, instant interactions, and exceptional responsiveness.

Optimize for:

- 60–120 FPS animations
- Low memory usage
- Fast startup
- Battery efficiency
- Offline resilience
- Smooth scrolling
- Instant feed loading

──────────────────────────────────────

TECH STACK

Framework

- React Native
- Expo
- TypeScript

Navigation

- React Navigation

State Management

- Zustand

Server State

- TanStack Query

Forms

- React Hook Form
- Zod

Video

- Expo Video / React Native Video

Animations

- React Native Reanimated
- React Native Gesture Handler
- Moti

Lists

- FlashList

Icons

- Lucide Icons

Utilities

- date-fns

Notifications

- Expo Notifications

Storage

- MMKV
- SecureStore

──────────────────────────────────────

ARCHITECTURE

Follow:

- Feature-first organization
- Clean Architecture
- SOLID
- Strict TypeScript
- Modular feature design
- Shared UI library
- Shared design system
- Separation of presentation and business logic

──────────────────────────────────────

APPLICATIONS

Generate:

Main Mobile App

Creator Studio (Mobile)

Moderator Interface (Mobile)

Shared Component Library

Shared Design System

Shared API Client

Shared Hooks

Shared Utilities

──────────────────────────────────────

FOLDER STRUCTURE

Generate scalable organization including:

app/

features/

components/

screens/

navigation/

layouts/

hooks/

providers/

services/

stores/

lib/

theme/

styles/

assets/

animations/

types/

config/

utils/

──────────────────────────────────────

NAVIGATION

Implement:

Authentication Flow

Main Tabs

Stack Navigation

Deep Linking

Protected Routes

Modal Navigation

Creator Navigation

Moderator Navigation

Universal Links

──────────────────────────────────────

AUTHENTICATION

Generate interfaces for:

Registration

Login

Logout

Forgot Password

Reset Password

Email Verification

Session Management

Token Refresh

Remember Me

Biometric Authentication

Role-based Navigation

──────────────────────────────────────

HOME EXPERIENCE

Generate:

For You Feed

Following Feed

Discover Feed

Trending Feed

Local Feed

Newest Feed

Category Feed

Support:

Infinite Scroll

Instant Feed Loading

Pull to Refresh

Feed Recovery

Skeleton Loading

──────────────────────────────────────

VIDEO PLAYER

Implement production-grade player supporting:

Adaptive Streaming

Auto Play

Auto Pause

Mute

Volume Control

Brightness Control

Playback Speed

Picture-in-Picture Ready

Background Playback Ready

Seek Bar

Captions

Subtitles

Quality Selection

Buffer Management

Gesture Controls

──────────────────────────────────────

VIDEO INTERACTIONS

Implement:

Like

Unlike

Comments

Replies

Bookmarks

Favorites

Shares

Copy Link

Report

Not Interested

Follow Creator

Creator Profile

──────────────────────────────────────

VIDEO CREATION

Generate interfaces for:

Video Upload

Draft Videos

Scheduled Posts

Upload Progress

Thumbnail Selection

Caption Editor

Hashtag Suggestions

Mention Suggestions

Visibility Settings

──────────────────────────────────────

COMMENTS

Implement:

Nested Replies

Mentions

Emoji Support

Like Comments

Pinned Comments

Comment Moderation

──────────────────────────────────────

CREATOR STUDIO

Generate:

Dashboard

Content Management

Draft Management

Scheduled Content

Video Analytics

Audience Analytics

Revenue Dashboard (Future Ready)

Engagement Dashboard

Follower Growth

──────────────────────────────────────

SEARCH

Implement:

Instant Search

Autocomplete

Trending Searches

Creator Search

Video Search

Hashtag Search

Search Filters

Search History

──────────────────────────────────────

DISCOVER

Generate:

Trending Videos

Trending Creators

Trending Hashtags

Categories

Challenges

Music

Recommended Creators

──────────────────────────────────────

PROFILES

Generate:

User Profiles

Creator Profiles

Verification Badges

Followers

Following

Statistics

Videos

Favorites

Liked Videos

Settings

──────────────────────────────────────

MESSAGING

Implement:

Conversation List

Chat

Media Sharing

Typing Indicators

Read Receipts

Conversation Search

──────────────────────────────────────

NOTIFICATIONS

Generate:

Notification Center

Push Notification Handling

Unread Counts

Notification Preferences

──────────────────────────────────────

STATE MANAGEMENT

Implement Zustand stores for:

Authentication

Feed

Player

Notifications

Messaging

Upload Queue

Downloads

Theme

User Preferences

Search

──────────────────────────────────────

SERVER STATE

Implement TanStack Query.

Support:

Caching

Infinite Queries

Optimistic Updates

Background Refresh

Retries

Offline Cache

Cache Invalidation

──────────────────────────────────────

API CLIENT

Generate:

Typed API Client

Authentication Interceptors

Retry Logic

Request Cancellation

File Upload Helpers

Download Helpers

Pagination Helpers

──────────────────────────────────────

FORMS

Generate production-ready forms using:

React Hook Form

Zod Validation

Inline Validation

Async Validation

File Upload

Loading States

Error Handling

──────────────────────────────────────

FILE UPLOADS

Support:

Large Videos

Resumable Uploads

Background Uploads

Upload Queue

Progress Tracking

Retry

Validation

Thumbnail Preview

──────────────────────────────────────

OFFLINE MODE

Implement:

Offline Cache

Offline Viewing

Download Queue

Synchronization

Pending Actions

Automatic Recovery

──────────────────────────────────────

PERFORMANCE

Optimize:

FlashList

Memoization

Image Optimization

Video Preloading

Lazy Loading

Code Splitting

Background Prefetching

Memory Optimization

Startup Optimization

──────────────────────────────────────

ACCESSIBILITY

Implement:

WCAG 2.2 AA Compliance

Screen Reader Support

Keyboard Support

VoiceOver

TalkBack

Reduced Motion

Dynamic Text

Focus Management

──────────────────────────────────────

RESPONSIVE DESIGN

Support:

Phones

Foldables

Tablets

Landscape

Portrait

──────────────────────────────────────

THEMING

Support:

Light Theme

Dark Theme

System Theme

Dynamic Themes

──────────────────────────────────────

ANIMATIONS

Use Reanimated and Moti for:

Page Transitions

Feed Transitions

Shared Element Transitions

Video Controls

Bottom Sheets

Comments

Dialogs

Micro-interactions

Loading States

Like Animations

Follow Animations

──────────────────────────────────────

ERROR HANDLING

Generate:

Error Boundaries

Offline Screens

Network Recovery

Retry Components

Maintenance Screens

──────────────────────────────────────

TESTING

Generate:

Unit Tests

Component Tests

Integration Tests

Accessibility Tests

Performance Tests

UI Test Architecture

──────────────────────────────────────

DOCUMENTATION

Generate:

Component Documentation

Navigation Documentation

Design System Documentation

State Management Standards

Frontend Standards

API Usage Guide

──────────────────────────────────────

PROJECT ORGANIZATION

Maintain throughout development:

Current Milestone

Generated Screens

Generated Components

Generated Features

API Integrations

Remaining Work

Dependencies

──────────────────────────────────────

OUTPUT FORMAT

For every generated file provide:

1. Exact file path
2. Complete file contents

Never generate placeholders.

Never generate pseudo-code.

Never omit implementations.

Never regenerate unchanged files.

Only modify files when required.

──────────────────────────────────────

STOP CONDITIONS

Generate the frontend incrementally according to the Master Prompt.

Each milestone should contain approximately 20–40 files.

At the end of every milestone:

- Verify the application compiles successfully.
- Update the project index.
- List completed screens and features.
- Identify the next file to generate.

STOP and wait for approval before generating the next milestone.
