# First App

A cross-platform dating application foundation built with **Flutter**, **Supabase** (Free Tier), and **Firebase Cloud Messaging (FCM)** for push notifications. This repository currently contains project structure and dependency configuration only; application screens and behavior will be added in later work.

## Technology

- Flutter and Dart for Android, iOS, and other supported platforms.
- Supabase for backend services.
- Firebase Cloud Messaging for push notifications.
- Riverpod for planned state management.

`pubspec.yaml` is the primary dependency file. There is no Python backend or admin utility in this scaffold, so a `requirements.txt` is not needed.

## Project layout

```text
lib/
  core/
    constants/   App and service configuration key placeholders
    services/    Supabase and notification service stubs
    theme/       Theme, color, and typography placeholders
    utils/       Helper and validator placeholders
  features/
    auth/         Authentication feature (data, domain, presentation)
    profile/      Profile feature (data, domain, presentation)
    discovery/    Discovery feature (data, domain, presentation)
    matches/      Matches feature (data, domain, presentation)
    chat/         Chat feature (data, domain, presentation)
  shared/
    models/       Shared model location
    widgets/      Reusable widget location
assets/
  icons/
  images/
```

Each feature owns its data, domain, and presentation code. Keep changes for a feature inside its folder where possible; shared code belongs under `lib/shared/`, and app-wide infrastructure belongs under `lib/core/`. This division lets two developers work on separate features with fewer overlapping edits. Empty folders are tracked with `.gitkeep` files.

## Setup

1. Install the Flutter SDK and the platform tooling required for your target (Android Studio/Android SDK for Android, Xcode for iOS).
2. Clone the repository and enter its directory.
3. Copy `.env.example` to `.env` and fill in the Supabase project URL and anon key. Keep `.env` private; it is ignored by Git.
4. Fetch Dart packages:

   ```sh
   flutter pub get
   ```

5. Configure Firebase for each target platform and add the platform configuration files using the official FlutterFire setup instructions. FCM also requires platform-specific setup and permissions.
6. Once an application entry point and screens have been added, launch on a connected device or emulator with:

   ```sh
   flutter run
   ```

This initial scaffold intentionally has no `main()` entry point or UI yet, so `flutter run` will work after that foundation is added. Do not commit real credentials or Firebase private configuration files.

## Git collaboration

1. Before starting work, update your local base branch:

   ```sh
   git switch main
   git pull --ff-only origin main
   ```

2. Create a focused branch for your change, for example:

   ```sh
   git switch -c feature/profile
   ```

3. Make changes in the relevant feature or shared folder. Avoid editing another feature's files unless the work requires it.
4. Review and commit your changes with a clear message:

   ```sh
   git status
   git add <files>
   git commit -m "Add profile foundation"
   ```

5. Push your branch and open a GitHub pull request:

   ```sh
   git push -u origin feature/profile
   ```

6. Before starting another task, switch back to `main` and pull the latest changes. Resolve conflicts on your branch and coordinate edits when a shared file must change.
