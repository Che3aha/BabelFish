# Babel Fish Universal Translator

A modern installable translation app for GitHub Pages.

## Important app identity

Babel Fish uses the permanent manifest ID `/babel-fish-universal-translator-app-id-v1`. Do not reuse this ID for another app. The unique ID prevents Chrome or Edge from treating Babel Fish as an update to another PWA hosted under the same GitHub Pages account.

If a previous Babel Fish build was mistaken for another installed app, choose **Ignore** in the branding-update prompt. Remove only the incorrect installed desktop shortcut/app, reinstall the other app from its own published URL, publish this corrected Babel Fish package, and then install Babel Fish separately.

The interface uses two simple screens: a welcome screen and a focused translator screen. Voice input stays active until the user taps **Stop & Translate**, and translated text is read aloud automatically by default.

The online relay supports more than 130 languages with true automatic source-language detection and a backup translation service. Language names and the main interface follow the phone or computer language; translated interface labels are cached after the first online load. Offline translation depends on language packs supplied by the browser/device, with a small emergency phrasebook as a final fallback.

Read-aloud waits for the device voice list before playback, uses a matching voice for Serbian, Arabic, and other target languages, and prefers a British female voice for English. If the device has no matching installed voice, the app tries an online multilingual voice and then the device default voice.

Voice dictation automatically starts a fresh recognition session when a phone or browser ends a session, preserving the accumulated transcript until the full 500-character limit. Serbian, Croatian, and Bosnian translations use direct language pairs rather than an English intermediate step.

## Speech-recognition diagnostics

Build **v1.3.0-samsung-fix** tracks interim and final results by their browser result indexes. Interim text is replaced as it changes; each final result is committed once. Recognition sessions have unique IDs so stale events cannot modify a newer session. A narrowly scoped guard suppresses an exact result replayed immediately after an automatic restart, while intentional repetition within a recording or after a user stop/restart remains intact. Recognition is stopped before translation and read-aloud.

Enable the local diagnostic panel from **Field Guide → Local diagnostics**, or add `?diagnostics=1` to the page URL. The in-memory log shows the build, browser information, recording starts/stops, session IDs, result indexes, final/interim state, and character counts. It does not log spoken text.

### Phone test

1. Confirm the footer and diagnostic panel show `v1.3.0-samsung-fix`.
2. Say one sentence once and verify it appears once.
3. Dictate several sentences with short pauses and confirm the counter can continue toward 500 characters.
4. Intentionally say the same sentence twice; both copies should remain.
5. Stop, translate, start a new recording, and verify the new session is separate.
6. Let the translated result read aloud and confirm the microphone is no longer listening.

Run the same steps on a second phone. If only one browser fails, compare the local diagnostic logs and browser versions; that indicates a browser/recognition-engine difference, not proof of faulty phone hardware.

The built-in **Field Guide** explains how to use the app and presents the fictional Babel Fish brainwave theory in original satirical wording.

For English translations, read-aloud prefers an installed British female voice and falls back gracefully when the device does not provide one.

## Publish on GitHub Pages

1. Create a new public GitHub repository.
2. Extract the ZIP and upload **all files** to the repository root. Do not upload the ZIP itself.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then click **Save**.
6. Wait for GitHub to show the published URL.

## Install the app

- **Windows/macOS:** open the published page in Chrome or Edge and click **Install app**.
- **Android:** open it in Chrome and choose **Install app** or **Add to Home screen**.
- **iPhone/iPad:** open it in Safari, tap **Share**, then **Add to Home Screen**.

## Notes

- Full translation works online. When offline, the app uses downloaded browser language packs when available and includes a small essential-phrase fallback for English, Serbian, Croatian, Bosnian, German, French, Spanish, Italian, and Portuguese.
- Microphone input depends on browser speech-recognition support and permission.
- The app shell remains available offline, but live translation does not.
