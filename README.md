# HuddleUp for Android

HuddleUp is a campus community app for students and teachers to share study material, find classmates, and coordinate in groups.

## What you can do

- Share campus posts for a course, department, or university, with categories for notes, lectures, questions, and study tips.
- Attach photos, videos, and documents to posts.
- Discover classmates, follow profiles, and like, comment on, or save posts.
- Send direct messages and create group conversations.
- Browse short-form video, notifications, and your profile.
- Use campus verification and, for authorized staff, moderation and community-management tools.

Some features require a configured HuddleUp service and may not be available in every deployment.

## Get the Android app

The Android application ID is `com.huddleup.app`. When a release is available, download the APK from this repository's [Releases](https://github.com/IRNCyber/HuddleUp-apk/releases) page. This repository does not currently contain a published release APK.

To install an APK downloaded from GitHub, open it on your Android device and follow Android's prompts to allow installation from the app you used to download it. Only install a release you trust. Android may show an additional confirmation before installation.

## Documentation

- [User guide](USER_GUIDE.md)
- [Technical overview and service setup](TECHNICAL_OVERVIEW.md)

## Project links

- [App source repository](https://github.com/IRNCyber/HuddleUp)
- [Report an issue](https://github.com/IRNCyber/HuddleUp-apk/issues)

## Services and privacy

The app source integrates Firebase Authentication and Cloud Firestore for sign-in and app data. It also integrates Supabase Storage for campus media attachments. Which sign-in methods work depends on the deployment's provider configuration. Review the privacy information supplied by the operator of the HuddleUp service you use before creating an account or sharing content.
