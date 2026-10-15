# Crypto Trainer — Android APK starter

This is a React app configured for Capacitor so it can be packaged as an Android APK. The APK is **not included yet**: this environment does not have Android SDK/Gradle installed. Use Android Studio locally or the included GitHub Actions workflow to build it.

## Build locally (Android Studio / SDK required)
1. Install Node.js 22, Java 17 and Android Studio with Android SDK.
2. In the project directory run:
   ```bash
   npm install
   npm run build
   npx cap add android
   npx cap sync android
   npx cap open android
   ```
3. In Android Studio select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. Debug APK output: `android/app/build/outputs/apk/debug/app-debug.apk`.

## Build APK in GitHub Actions
1. Create a new GitHub repository and upload the project files.
2. Push the files to the `main` branch.
3. Open the repository's **Actions** tab and run **Build Android APK** (or wait for the push workflow).
4. Download the artifact named `crypto-trainer-debug-apk`. It contains `app-debug.apk`.

## Features / caveats
- CoinGecko public market API, top 50 by market cap, price changes 1h/24h/7d.
- Local demo trading journal, virtual balance and JSON export.
- The app needs an internet connection for market prices. API limits may affect refresh cadence.
- The macro panel is a placeholder. Signals are simple illustrative rules, not financial advice.
- No OKX connection and no real orders. Local browser storage may be cleared by Android/WebView data cleanup.
- The generated debug APK is for testing/sideloading. Publishing on Google Play needs a signed release build and additional checks.
