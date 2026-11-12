# Project status

This package is a more complete MVP implementation, but it has not been compiled or device-tested in this environment.

## Implemented in source
- Compose screens: Home, Scanner, Projects, Settings
- Room persistence for project records
- DataStore dark-mode preference
- WorkManager dependency and scan worker foundation
- Bounded HTTPS same-host website resource scanner
- SAF folder import for user-selected Android project folders
- APK metadata inspection and APK copy into app-private storage
- Project browser and text file preview
- ZIP export and ZIP import through Android document pickers
- ZIP path traversal, entry-count and expanded-size checks
- Scan reports, storage usage, project deletion
- Basic scan cancellation and progress state

## Still needs real-device validation / future polish
- Compile and run on a real Android device
- Test multiple Android OEM file pickers
- Improve handling of unusual/very large websites and binary resources
- Add automated unit/instrumentation tests
- Add resumable background scanning and notification controls
- Add richer preview for images and binary assets
- Add database migration tests and accessibility review

Do not treat “all features” as a claim that every possible website or APK can be cloned. Website source access and APK reverse engineering have inherent technical limits.
