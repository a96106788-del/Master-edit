# Master Flow Android starter

This is an Android Studio project that packages the Master Flow mobile editor prototype in an Android WebView.

## Build an installable APK
1. Install Android Studio (current stable) and Android SDK Platform 35.
2. Open this folder in Android Studio.
3. Let Gradle sync complete.
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Find the debug APK at `app/build/outputs/apk/debug/app-debug.apk`.
6. Transfer that APK to your Android phone and install it. You may need to allow installation from that source.

## Included
- Android launcher activity and WebView shell
- Video file picker and playback
- Basic timeline UI, seek, split marker and trim-range selection
- Text overlay, preview filters, playback speed, audio file preview
- Reels template selection and export settings UI

## Important limitations
This is a buildable starter/prototype, not a full CapCut replacement. Split and trim are UI/preview operations; transitions, AI tools, multilayer compositing and final MP4 rendering are not implemented. The export button reports the selected settings but does not render a new video. A production release needs a native media pipeline (for example Android Media3 Transformer or FFmpeg), proper permissions, testing, signing, and privacy review.


## Build APK from an Android phone using GitHub Actions (free tier)

1. Create a GitHub account and a **new public repository** named `MasterFlow`.
2. Upload the contents of this project ZIP to the repository. The files must be at the repository root (so `settings.gradle`, `build.gradle`, and the `app/` folder are visible at the top level).
3. The workflow is already included at `.github/workflows/android-apk.yml`.
4. Open the repository's **Actions** tab. If GitHub asks, enable Actions.
5. Choose **Build Master Flow APK** and tap **Run workflow** (or push/upload a commit to `main`).
6. When the run finishes with a green check, open that run, scroll to **Artifacts**, and download `Master-Flow-debug-APK`.
7. Extract the downloaded artifact ZIP on your phone. Tap `app-debug.apk` to install it. If Android blocks it, allow installation from that browser/file manager when prompted.

Notes:
- GitHub Actions has usage limits; public repositories generally provide a free way to run this workflow, subject to GitHub's current limits and policies.
- This creates a **debug APK** for testing, not a Play Store release-signed APK.
- This project is a WebView-based prototype. The APK packages the current Master Flow interface; full professional video rendering/export and advanced effects are not implemented yet.
