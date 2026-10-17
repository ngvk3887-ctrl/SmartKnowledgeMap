# SmartKnowledgeMap — cloud APK build

This repository wraps `www/index.html` in an Android app using Capacitor and builds an installable **debug APK** in GitHub Actions.

## Build from a phone

1. Create a GitHub account if needed, then create a **public repository** named `SmartKnowledgeMap`.
2. Extract the source ZIP on your phone using its file manager. Upload the **contents** of the extracted folder to the repository root (not the enclosing folder). Make sure `.github/workflows/build-apk.yml` is included. If your phone's file manager hides `.github`, enable showing hidden files before uploading.
3. Commit the files to the `main` branch.
4. Open the repository's **Actions** tab and enable workflows if GitHub asks.
5. Open **Build SmartKnowledgeMap APK**, tap **Run workflow**, and wait for the run to finish successfully.
6. Open the repository's **Releases** page. Download `app-debug.apk` directly to the Android phone and tap it to install. Android may ask you to allow installation from that browser/file manager.

## Important notes

- This workflow is designed to publish the APK as a direct `.apk` release asset, rather than asking you to download a ZIP artifact.
- The APK is a debug-signed test build, suitable for installing and testing. It is not a Play Store release.
- The HTML app saves its map in the app's local WebView storage. Uninstalling the app or clearing its storage may erase saved map data; use its Export feature to back up your data.
- This app currently wraps the existing HTML only. It does **not** add AI features or protect any future API keys; any AI integration should call a backend service and never put secret API keys in the HTML or APK.
- The workflow has not been run in this package-generation environment. The APK is not included and must not be considered built until GitHub Actions succeeds and the release asset is verified.
