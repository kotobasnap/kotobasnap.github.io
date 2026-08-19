---
layout: default
title: Privacy Policy
lang: en
description: How Kotoba Snap handles your information.
---

<p class="langswitch"><a href="/privacy/">简体中文</a></p>

**Effective date: 2026-07-28**
**Last updated: 2026-08-19**

Kotoba Snap ("the app") is a Japanese vocabulary learning tool: you photograph or pick an image, the app recognizes the Japanese text in it, and helps you turn unfamiliar words into flashcards with a review schedule.

This policy explains how the app handles your information. **The app has no accounts — you do not register or sign in, and every feature works without doing so.**

## 1. What the developers never receive

We (the developers of this app) **operate no server**, and therefore **never receive or store** any of the following:

- The images you photograph or select
- The text recognized in those images
- The flashcards, notes, and review history you create
- Your name, email address, phone number, location, or any account information

The app's own code never transmits any of it anywhere.

That is not the same as "nothing ever leaves your device". Two paths do: **your phone's own operating-system backup** (section 2) and **diagnostic data sent by the Google ML Kit SDK this app integrates** (section 4). Please read both.

## 2. Where your data lives

All of the following is stored in the app's **private storage area on your device**:

- **A copy of your source images.** Images you photograph or select are copied into the app's private directory so you can later see where a flashcard came from. This copy is **not in your system photo library** and is not accessible to other apps.
- **Flashcard data**: written form, reading, part of speech, meanings, your own notes, JLPT level, and the link to the source image.
- **Review history**: when you reviewed a card and how you rated it.
- **App settings** and usage counters.
- **A dictionary index** built locally from the dictionary data bundled with the app. It contains none of your input.

You can cap how much space source images may use, or clear all source images at once, from Settings. Deleting a flashcard also deletes its review history.

### Operating-system backup and moving to a new phone

**This app provides no cloud sync operated by us**, and never sends your images, flashcards, or review data to our servers.

However, **your phone's own operating-system backup may back up and restore some of this app's data**, depending on your system settings. In the current version:

| | iPhone (iCloud Backup) | Android (Google Auto Backup) |
|---|---|---|
| Flashcards, review history, settings | Included in system backup by default | Included in system backup by default |
| Source image copies | **Explicitly excluded** from backup | **Explicitly excluded** from backup |

"Included by default" describes the platform's default behaviour. Whether a backup actually exists, and whether it can be restored, depends on whether you have system backup enabled and whether it completed successfully.

**Source image copies are explicitly excluded on both platforms**, to keep fewer copies of your photos in the cloud or in transit. On Android this exclusion applies to cloud backup, to direct device-to-device transfer when setting up a new phone, and to transfers to a non-Android device.

So after moving to a new phone: **your flashcards and review history come back; the source images do not.** The "by source image" grouping still exists and still works — it simply shows a placeholder instead of the photo.

These backups live in **your own Apple or Google account**, which we cannot access. Whether backup is on, and how to delete an existing backup, is governed by your system settings and Apple's or Google's policies.

**Uninstalling the app deletes all local data on that device.** If your system has already made a backup, what happens to that copy is determined by those platform backup settings, not by us.

## 3. Text recognition happens on your device

Text recognition (OCR) runs **locally on your device**:

- On Android, via Google ML Kit's on-device text recognition.
- On iOS, primarily via Apple's VisionKit, with Google ML Kit as a fallback.

**Your images and their recognized text are not sent to us, and are not sent to Google.** On the latter, Google states in the [ML Kit Terms of Service](https://developers.google.com/ml-kit/terms) that when you use ML Kit APIs, processing of the input data (images, video, text) fully happens on-device, and ML Kit does not send that data or the resulting outputs to Google servers. Apple's VisionKit is a built-in on-device system capability and likewise recognizes text locally.

Japanese word segmentation, dictionary lookup, and review scheduling are likewise entirely local — the dictionary ships with the app and needs no network connection.

### 3.1 Reference translation is also on-device, but its language pack is downloaded

The app can show a sentence-by-sentence **reference translation** (Japanese → Simplified Chinese) of the recognized text. Translation also runs **locally on your device**:

- On iOS 18 and later, via Apple's built-in system translation. The feature is not offered below iOS 18.
- On Android, via Google ML Kit's on-device translation.

**Neither your images nor the recognized text are sent anywhere to produce a *reference translation*** — not to us, not to Google or Apple. (AI translation is a different thing and does send them; it is off by default — see 3.3.)

**One part does use the network, and we state it separately: the translation language pack does not ship with the app and has to be downloaded the first time you use the feature.** That is a real network request, it happens only after you tap to start it, and what is downloaded is a general-purpose language model — **the request carries none of your images or text**. Once downloaded the pack stays on your device and translation needs no network afterwards.

On Android that download is performed by Google's ML Kit; on iOS it is performed by the system and follows your own cellular-data settings.

### 3.2 What needs the network, and what does not

In one sentence: **by default, apart from downloading a language pack the first time you use Reference Translation, nothing in this app needs a network connection.** If you turn on AI Translation and enter your own API key, that feature does use the network — it is off by default. See the table below and section 3.3.

| Feature | Needs network? |
|---|---|
| Taking a photo / picking from the library | **No** |
| Text recognition (OCR) | **No** |
| Furigana | **No** |
| Dictionary lookup, candidates, glosses | **No** (the dictionary ships with the app) |
| Creating, editing, searching and organising cards | **No** |
| Review and review scheduling | **No** |
| Revisiting a source image and its recognized text | **No** |
| Backup export / import | **No** |
| **Reference translation** — first use | **Yes**: downloads a language pack, once |
| **Reference translation** — after the pack is downloaded | **No** |
| **AI translation** (off by default; you must turn it on and add your own key) | **Yes**: each translation sends the recognized text to the provider you chose |

In other words: **once the pack has been downloaded, the app's features work in airplane mode — as long as you have not turned AI Translation on.** (The privacy-policy link under Settings → About opens a web page in your browser, which naturally needs the network; it does not handle any of your data.)

### 3.3 AI translation (optional, off by default)

This feature is off by default. Turning it on takes two deliberate steps: switching it on in settings, and entering **an API key you obtained yourself from a provider**. Until you have done both, the feature has no entry point anywhere in the app and makes no network requests of any kind.

Once it is on, each time **you tap** to translate:

- **The recognized text is sent to the provider you chose.** Nothing is translated automatically; it goes only when you ask.
- **The source image is never sent.** Not at any point.
- **The key is kept only in this device's secure storage** (iOS Keychain / Android Keystore). It is not included in backups and does not move to a new phone — after switching devices you will need to enter it again. The app never sends the key to us (we have no server), and never writes it to logs, crash reports, or export files.
- **Usage is billed to your own account with that provider.** We do not handle, take a share of, or see your usage.

**Whichever provider you choose is where your text goes, under that provider's own terms.** The providers currently available, and what matters about each:

| Provider | What matters |
|---|---|
| Claude (Anthropic) | Its commercial terms state that customer content is not used to train models |
| ChatGPT (OpenAI) | API data is not used for training by default; abuse-monitoring logs are retained for up to 30 days |
| DeepSeek | **Data is processed and stored in mainland China, and this provider uses submitted content for model training by default** — turning that off is something you do on their own site |

The app shows an explanation and asks for your agreement before the first time it sends text to a given provider, and **asks again if you switch providers**, because who receives your text has changed.

We make no representations about how these providers handle your data — that is a relationship between you and them. The table reflects each provider's published terms as of 2026-08-08; where it differs from a provider's current terms, theirs govern.

One more thing needs stating separately because it is not tied to any feature: the Google ML Kit SDK integrated in this app automatically sends limited diagnostic data (see section 4). It is not triggered by any particular feature, and it does **not** include your images or text.

## 4. Diagnostic data collected by a third-party SDK

**The app does use the network, and we cannot claim that no data ever leaves your device.**

The Google ML Kit SDK integrated in this app automatically sends limited diagnostic and usage metrics to Google. **This version provides no in-app setting to turn that SDK telemetry off.**

Per Google's official data disclosures ([Android](https://developers.google.com/ml-kit/android-data-disclosure) / [iOS](https://developers.google.com/ml-kit/ios-data-disclosure)), that information includes:

**Common to both platforms**

- Device information (manufacturer, model, OS version and build)
- App package name / bundle ID and version
- Per-installation identifiers, which Google states are **not** intended to uniquely identify a user or physical device
- Performance metrics (such as latency)
- API configuration (such as image format and resolution)
- Event type and error codes

**Android only, in addition**

- Input/output sizes and feature version

Google states that this data is transmitted over HTTPS and is not shared with third parties. **These diagnostic metrics do not include your images or the recognized text** — as described in section 3, Google states this explicitly in the ML Kit Terms of Service.

For how Google handles this data, see [Google ML Kit Terms & Privacy](https://developers.google.com/ml-kit/terms) and the [Google Privacy Policy](https://policies.google.com/privacy).

Beyond the ML Kit diagnostic and usage metrics described above, the app contains **no** advertising SDK, no general-purpose behavioural analytics SDK, and no crash-reporting SDK.

## 5. Permissions

| Permission | Why |
|---|---|
| Camera | Used only when you choose "Take photo", to capture the image to be recognized |
| Photos / Photo library | Used only when you choose "Import from library". The app receives only the single image you selected; it does not read your library as a whole |

The app requests no location, contacts, microphone, phone, or SMS permissions.

On Android this app declares no permissions of its own. The app info page may show `INTERNET` and `ACCESS_NETWORK_STATE`; those come from the Google ML Kit components described in section 4.

## 6. Children

The app is not directed at children under 13. It has no accounts and **asks for no name, email address, date of birth, or any other identifying information**.

Where images and flashcards are stored, and how operating-system backup treats them, is described in section 2; the Google ML Kit diagnostic data is described in section 4. These apply the same way to everyone, including children.

## 7. Your rights

**We hold none of your content on any server of ours**, so your control over that content is entirely on your device:

- **Access**: every flashcard and source image is viewable in the app.
- **Deletion**: delete individual flashcards, clear all source images, or uninstall the app to remove all local data on that device.
- **Export**: not available in this version.

Two things we cannot do on your behalf:

- The copy held in an **operating-system backup** — manage it in your iCloud or Google account backup settings (section 2).
- The **diagnostic data Google ML Kit has received** is held by Google; see the Google privacy links in section 4. We neither hold it nor can delete it for you, so we will not promise you a deletion channel we cannot honour.

If you have questions about how the app handles data, or want help understanding any of the above, contact us at the address below.

## 8. Changes to this policy

If this policy changes, we will update the "Last updated" date at the top of this page. Where required by law or otherwise appropriate, we will provide additional notice.

## 9. Contact us

**kotobasnap.support@gmail.com**

We will do our best to respond within a reasonable time.
