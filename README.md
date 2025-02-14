# Expo Android Build Failure: Package Name Mismatch

This repository demonstrates a common yet elusive bug in Expo's Android build process.  The build fails with an error related to `google-services.json`, even when the file appears correctly configured. The root cause is a subtle discrepancy between the application ID (package name) specified in `google-services.json` and the `applicationId` in the `android/app/build.gradle` file.

## Reproducing the Bug

1. Clone this repository.
2. Run `npm install`.
3. Attempt to build an Android APK using `expo build:android`.

You will encounter a build failure due to the package name mismatch.  The solution is provided in the `bugSolution.js` file.

## Solution

The solution involves ensuring perfect consistency between the `package_name` in `google-services.json` and the `applicationId` in `android/app/build.gradle`.  Refer to `bugSolution.js` for the corrected files.

## Note

This bug highlights the importance of double-checking seemingly minor details during the Android build configuration. Even a seemingly insignificant character difference between the package names will result in a build error. This is especially relevant if you migrated a project, renamed the project, or have conflicting package names elsewhere.