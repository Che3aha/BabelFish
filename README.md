# Babel Fish Universal Translator

A modern installable translation app for GitHub Pages.

## Important app identity

Babel Fish uses the permanent manifest ID `/babel-fish-universal-translator-app-id-v1`. Do not reuse this ID for another app. The unique ID prevents Chrome or Edge from treating Babel Fish as an update to another PWA hosted under the same GitHub Pages account.

If a previous Babel Fish build was mistaken for another installed app, choose **Ignore** in the branding-update prompt. Remove only the incorrect installed desktop shortcut/app, reinstall the other app from its own published URL, publish this corrected Babel Fish package, and then install Babel Fish separately.

The interface uses two simple screens: a welcome screen and a focused translator screen. Voice input stays active until the user taps **Stop & Translate**, and translated text is read aloud automatically by default.

The online relay supports more than 130 languages with true automatic source-language detection and a backup translation service. Language names and the main interface follow the phone or computer language; translated interface labels are cached after the first online load. Offline translation depends on language packs supplied by the browser/device, with a small emergency phrasebook as a final fallback.

Read-aloud waits for the device voice list before playback, uses a matching voice for Serbian, Arabic, and other target languages, and prefers a British female voice for English. If the device has no matching installed voice, the app tries an online multilingual voice and then the device default voice.

Voice dictation automatically starts a fresh recognition session when a phone or browser ends a session, preserving the accumulated transcript until the full 500-character limit. Serbian, Croatian, and Bosnian translations use direct language pairs rather than an English intermediate step.

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
