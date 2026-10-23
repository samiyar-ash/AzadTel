# AzadTel Android

A small Kotlin Android app that opens `https://samiyarashouri.ir/AzadTel` inside an Android WebView.

## Features
- Opens AzadTel on launch
- Back, forward, and reload controls
- Shows the current page URL
- Uses Android WebView for web rendering
- GitHub Actions builds an APK and uploads it as an artifact

## Add your app icon
Place your square PNG image in the repository root and name it exactly:

`icon.png`

The GitHub Actions workflow copies it into Android resources before building. A built-in fallback icon is used when `icon.png` is absent. A 512x512 PNG is recommended.

## Build APK on GitHub
1. Create a new GitHub repository.
2. Upload all files and folders from this project (including the hidden `.github` folder).
3. Commit/push to the `main` branch. The workflow also supports manual runs from **Actions → Build Android APK → Run workflow**.
4. Open the repository's **Actions** tab.
5. Open the successful **Build Android APK** run.
6. In **Artifacts**, download `AzadTel-debug-apk`.
7. Extract the downloaded ZIP; it contains `app-debug.apk`.

## Important
- The APK produced by this workflow is a **debug APK** suitable for testing and direct installation. It is not a Play Store release build.
- The app needs an internet connection. The website itself must allow its pages and required features to work inside Android WebView.
- JavaScript and DOM storage are enabled because modern web apps commonly need them.
- External links currently remain inside the app. Some services, file uploads/downloads, camera/microphone permissions, payment flows, or popup-based login may need additional native handling if AzadTel uses them.
