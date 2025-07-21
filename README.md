# ✅ Android App Production Release Checklist

A complete pre-release checklist for Android (or Flutter) apps to ensure a stable, secure, and Play Store–ready production release.

---

## 📊 Analytics & Crash Reporting
- [ ] Integrate Firebase Analytics, Mixpanel, or Amplitude.
- [ ] Add a crash reporting library (e.g., Firebase Crashlytics, Sentry).
- [ ] Validate crash-free sessions and monitor runtime exceptions.
- [ ] Ensure analytics events do not expose sensitive data.

---

## 🔐 API Keys & Secrets Protection
- [ ] Ensure no secrets or API keys are hardcoded in the APK.
- [ ] Store secrets securely (encrypted storage, keystore, or backend proxy).
- [ ] Use Firebase Remote Config or secure key management.
- [ ] Add string/code obfuscation (Proguard/R8) to sensitive logic.

---

## 🧪 Build & Configuration
- [ ] Disable all debug logs and ensure `BuildConfig.DEBUG == false`.
- [ ] Verify all API URLs and keys point to production.
- [ ] Apply Proguard/R8 for code shrinking and optimization.
- [ ] Use Play Integrity API or SafetyNet for tamper/root detection.
- [ ] Verify `android:exported` flags on all activities/services (Android 12+).

---

## 📦 App Size & Performance
- [ ] Check current APK/AAB size vs previous release.
- [ ] Remove unused assets, layouts, images.
- [ ] Clean dead code and unused dependencies.
- [ ] Measure app performance with Android Profiler.
- [ ] Run `adb shell dumpsys batterystats` for battery impact analysis.

---

## 🧩 Feature Flags & Kill Switches
- [ ] Use feature toggles (e.g., Firebase Remote Config) for gradual rollouts.
- [ ] Add kill switches for experimental or risky features.
- [ ] Include fallback logic if a feature is disabled remotely.

---

## 📲 UI/UX & User-Facing Updates
- [ ] Use adaptive icons for all Android versions.
- [ ] Implement Android 12+ splash screen API.
- [ ] Ensure proper app localization and translated strings.
- [ ] Be ready with updated "WHAT’S NEW" Play Store content.
- [ ] Upload latest screenshots and feature graphics.

---

## 🧾 Legal Compliance
- [ ] Add Privacy Policy & Terms of Service (in-app and store listing).
- [ ] Ensure GDPR, COPPA (if kids), or regional law compliance.
- [ ] Provide user consent flows if necessary.

---

## 🔍 Deep Linking & Navigation
- [ ] Test App Links and deep links end-to-end.
- [ ] Verify `intent-filters` in `AndroidManifest.xml`.
- [ ] Validate navigation flows using go_router / Navigator 2.0 if Flutter.

---

## 🕰️ Background Tasks
- [ ] Validate all scheduled jobs (WorkManager, JobScheduler, AlarmManager).
- [ ] Ensure battery/doze constraints are handled.
- [ ] Validate app behavior in no-network or airplane mode.

---

## 🔄 Migration Logic
- [ ] Add migration logic for local database changes (Room, Hive, etc.).
- [ ] Test upgrades from previous APKs to current version.
- [ ] Ensure SharedPreferences and Remote Config changes are handled properly.

---

## 🧪 Testing
- [ ] Add unit tests for all new logic and edge cases.
- [ ] Run all unit and integration tests.
- [ ] Test upgrade scenarios from older versions.
- [ ] Test across multiple OS versions and screen sizes.
- [ ] Test offline behavior (no internet, airplane mode).

---

## 🛡️ Security Review
- [ ] Review AndroidManifest.xml for unnecessary permissions.
- [ ] Secure all data storage (keystore, encrypted preferences, etc.).
- [ ] Obfuscate code with Proguard/R8.
- [ ] Monitor for reverse engineering threats using SafetyNet or Play Integrity.

---

## 🛍️ Play Store Release Prep
- [ ] Confirm correct `versionCode` and `versionName`.
- [ ] Respond to previous Play Store feedback and reviews.
- [ ] Add in-app review prompt (Google API).
- [ ] Update screenshots and changelog.
- [ ] Use internal → closed → production tracks for rollout.
- [ ] Enable staged rollout if it's a major release.

---

## 🧠 Pro Tips
- Use CI/CD (Bitrise, GitHub Actions, Codemagic) to automate this checklist.
- Store secrets in CI environments, never in code.
- Monitor logs post-release via Crashlytics or Logcat.
- Set up alerts for crash spikes or performance degradation.

---

_This checklist helps ensure your Android/Flutter app is release-ready and secure. Fork this checklist and adapt it to your team or project!_
