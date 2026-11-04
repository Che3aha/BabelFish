# Babel Fish Universal Translator

A modern installable translation app for GitHub Pages.

The welcome screen is titled **The Impossible Art of Being Understood** and carries the field warning: **WARNING: PROLONGED USE MAY LEAD TO UNDERSTANDING OTHER PEOPLE.**

<img width="819" height="573" alt="image" src="https://github.com/user-attachments/assets/3abfef5c-1a14-427e-98b3-609bf4238d99" />

## Important app identity

Babel Fish uses the permanent manifest ID `/babel-fish-universal-translator-app-id-v1`. Do not reuse this ID for another app. The unique ID prevents Chrome or Edge from treating Babel Fish as an update to another PWA hosted under the same GitHub Pages account.

If a previous Babel Fish build was mistaken for another installed app, choose **Ignore** in the branding-update prompt. Remove only the incorrect installed desktop shortcut/app, reinstall the other app from its own published URL, publish this corrected Babel Fish package, and then install Babel Fish separately.

The interface uses two simple screens: a welcome screen and a focused translator screen. Voice input stays active until the user taps **Stop & Translate**, and translated text is read aloud automatically by default.

The online relay supports more than 130 languages with true automatic source-language detection and a backup translation service. Language names and the main interface follow the phone or computer language; translated interface labels are cached after the first online load. Offline translation depends on language packs supplied by the browser/device, with a small emergency phrasebook as a final fallback.

Read-aloud waits for the device voice list before playback, uses a matching voice for Serbian, Arabic, and other target languages, and prefers a British female voice for English. If the device has no matching installed voice, the app tries an online multilingual voice and then the device default voice.

Voice dictation automatically starts a fresh recognition session when a phone or browser ends a session, preserving the accumulated transcript until the full 500-character limit. Serbian, Croatian, and Bosnian translations use direct language pairs rather than an English intermediate step.

## Speech-recognition diagnostics

Build **v1.5.0-simplified-ui** retains the speech-recognition fixes that track interim and final results by their browser result indexes. Interim text is replaced as it changes; each final result is committed once. Recognition sessions have unique IDs so stale events cannot modify a newer session. A narrowly scoped guard suppresses an exact result replayed immediately after an automatic restart, while intentional repetition within a recording or after a user stop/restart remains intact. Recognition is stopped before translation and read-aloud.

Diagnostics are hidden during normal use. For troubleshooting only, add `?diagnostics=1` to the page URL. The in-memory log shows the build, browser information, recording starts/stops, session IDs, result indexes, final/interim state, and character counts. It does not log spoken text.

### Phone test

1. Confirm the footer shows ` v1.6.1-compact-ui`. If troubleshooting, add `?diagnostics=1` and confirm the same version in the diagnostic panel.
2. Say one sentence once and verify it appears once.
3. Dictate several sentences with short pauses and confirm the counter can continue toward 500 characters.
4. Intentionally say the same sentence twice; both copies should remain.
5. Stop, translate, start a new recording, and verify the new session is separate.
6. Let the translated result read aloud and confirm the microphone is no longer listening.

Run the same steps on a second phone. If only one browser fails, compare the local diagnostic logs and browser versions; that indicates a browser/recognition-engine difference, not proof of faulty phone hardware.

## Simplified translator screen

- Language selectors are labelled **Input** and **Output**.
- The duplicate console heading has been removed.
- Read aloud, replay, copy, and share use compact symbol buttons with accessible labels and tooltips.
- Translation status badges and local diagnostics stay out of the normal interface.

## Translation relay fix

Build **v1.5.1-relay-fix** no longer treats `navigator.onLine` as proof that translation is unavailable. Some older phones and installed web apps report an incorrect offline state. Babel Fish now tries both online translation relays first, then falls back to an on-device language model or the emergency phrasebook. The common casual phrase **Kako si?** is also available in the offline phrasebook.

## Installation-ready experience

Build **v1.6.0-install-ready** adds:

- device-specific installation help for iPhone, iPad, Android, and desktop browsers;
- a pre-install compatibility check for translation, speech input, read-aloud, offline shell, and output language;
- a first-run device check after installation without requesting microphone permission prematurely;
- an update-ready banner with a safe restart action;
- wide and mobile installation-preview screenshots;
- long-press/right-click shortcuts for Speak, Type, and the Field Guide;
- a GitHub Pages-compatible Share Target so supported devices can share text into Babel Fish;
- clearer language explaining that 130+ languages require online translation, while offline coverage depends on downloaded device models and essential phrases.

Build **v1.6.1-compact-ui** simplifies the translator header with an arrow-only return control, removes the online/offline badge, makes the Input and Output language selectors more compact, and changes the landing-page organism label and warning to Babel Fish yellow.

## Localized Guide and app sharing

Build **v1.4.0-local-guide-share** localizes the complete Field Guide to the phone or computer's language. Serbian Guide text is built in; other supported device languages are translated online on first use and cached locally, with a backup translation relay. Language names also follow the device locale.

Every completed translation includes **Share to app**. On supported phones and desktops it opens the operating system's native share menu, allowing the user to choose compatible installed programs such as Messages, WhatsApp, email, Notes, social apps, or workplace tools. If native sharing is unavailable, the translation is copied for pasting into another program.

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
