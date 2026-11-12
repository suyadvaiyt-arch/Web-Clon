# DEVIL CLONE STUDIO — Complete MVP Source

Native Android starter application for authorized collection of public website resources and inspection/import of Android projects or APK files selected by the user.

## Technology
- Kotlin, Jetpack Compose, Material 3
- Room database, DataStore
- WorkManager
- OkHttp, Jsoup
- Android Storage Access Framework + DocumentFile
- ZIP import/export

## Included functionality
- Dashboard and bottom navigation
- Local project database and preferences
- HTTPS website scan for a bounded number of same-host public resources
- Pause/cancel support in the scanner screen (scan runs in the app process)
- User-selected Android project folder import through SAF
- APK metadata inspection and local APK copy
- Project file browser and text/code preview
- ZIP export to a user-selected destination
- ZIP import with path traversal, entry-count and expanded-size checks
- Scan report text files and project deletion
- Storage usage display

## Important boundaries
- Website scanning can only retrieve resources that are publicly accessible and linked from the requested page. It does not retrieve server-side PHP, private APIs, databases, login-protected content, or secrets.
- APK inspection reads package metadata and preserves the APK file. It does not recreate the original Android Studio project or recover original source code.
- Use only websites and files that you own or are authorized to inspect.
- Scanning is intentionally bounded and same-host only. It does not bypass access controls, robots restrictions, paywalls, or rate limits.

## Open and build
1. Open this folder in Android Studio.
2. Use JDK 17.
3. Allow Gradle sync and install Android SDK 35.
4. Run the `app` configuration on an Android 8.0+ device.
5. Internet is needed only for website scanning. Project management and ZIP operations work locally.

This is a source project, not a prebuilt or signed APK. Build and test it in Android Studio on a real device before relying on it. Gradle wrapper scripts are not bundled; Android Studio can generate/use the wrapper for the project.

## Storage
Files are stored in the app's private files directory. ZIP export uses Android's document picker, allowing the user to save an archive to Downloads or another chosen folder. Uninstalling the app can remove private project data; export backups first.

## GitHub automatic APK build

1. Create a GitHub repository and upload the **contents** of this project folder to the repository root (so `settings.gradle.kts` and `app/` are at the top level).
2. Keep the default branch named `main`.
3. The workflow is at `.github/workflows/android.yml`.
4. Every push to `main` starts a cloud debug APK build. You can also run it manually from **Actions** → **DEVIL CLONE STUDIO - Automatic APK Build** → **Run workflow**.
5. When the run finishes successfully, open the run, scroll to **Artifacts**, and download `DEVIL-CLONE-STUDIO-debug-APK`. Extract the downloaded artifact ZIP to get the `.apk` file.

This workflow builds a **debug APK** for testing. It is not a signed release APK for publishing. The first build may fail if the app source has compile errors; check the failed Actions log for the exact error. The source project has not been verified by a successful Android build yet.
