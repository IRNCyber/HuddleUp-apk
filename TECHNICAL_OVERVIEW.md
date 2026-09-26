# HuddleUp technical overview

This document describes the Android app implementation in the linked source repository. It is intended for maintainers and operators; it is not a deployment guarantee or a privacy policy.

## Application

- Display name: Huddleup
- Android application ID: `com.huddleup.app`
- Current project version: `1.0.0` (version code `1`)
- App framework: Expo SDK 52 and React Native 0.76
- Data store and authentication integration: Firebase Authentication and Cloud Firestore
- Media attachment integration: Supabase Storage, using Firebase-authenticated requests

## Service configuration

The app reads its client configuration from environment variables at build time. Start from the source repository's `.env.example` and configure the matching provider consoles for your own deployment. The example file lists:

- Firebase API key, auth domain, project ID, storage bucket, messaging sender ID, and app ID.
- Supabase project URL and publishable key for media storage.
- Optional Google OAuth client IDs and Facebook app ID.
- Optional X/Twitter provider credentials, configured through Firebase Authentication.

Enable only the authentication providers supported by your deployment. Provider setup, OAuth redirect configuration, allowed domains, Firebase rules, and Supabase storage policies must match the app configuration. Never commit private credentials or service-role keys to the app source or APK. Client-side configuration is not a substitute for server-side access rules.

Without Firebase configuration, the app may enter a limited demo state; account, cloud data, and messaging features need a configured backend. Media uploads also require working Supabase Storage settings and policies.

## Build and release notes

The source repository contains the Android project and package scripts. A release intended for distribution must be built from the intended source revision, configured for the deployment, and signed with a production Android signing key. Keep that private key and its passwords secure and backed up; losing them can prevent users from installing updates signed as the same app. Do not distribute a debug-signed build as a production release.

Before publishing, maintainers should verify the release artifact, document its version and checksum, and ensure the published privacy information and store disclosures match the actual backend configuration and data practices. Store acceptance is determined by each store's review process.

## Android permissions and user data

The Android manifest requests internet access and includes media/storage-related permissions. The app can handle profile data, account identifiers, campus information, posts, comments, messages, reports, and selected media attachments. The Firebase and Supabase projects configured by the operator determine where cloud data is processed and stored. The operator should publish accurate privacy and retention information and secure the Firebase and storage rules.

## Source and documentation

- [Android app source](https://github.com/IRNCyber/HuddleUp)
- [APK and documentation repository](https://github.com/IRNCyber/HuddleUp-apk)
- [User guide](USER_GUIDE.md)
