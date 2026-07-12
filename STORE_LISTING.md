# Chrome Web Store — Submission Kit

Copy-paste reference for every field in the [developer console](https://chrome.google.com/webstore/devconsole).
Upload `auto-translator-for-discord-v1.0.0.zip`.

---

## Store Listing tab

**Item name**

```
Auto Translator for Discord
```

**Summary** (from manifest, shown in search results)

```
Auto-translates Discord messages to English in real time, including new incoming messages. By HYAIPE — open source on GitHub.
```

**Detailed description**

```
Reading Discord servers in a language you don't speak? Chrome's built-in page
translation only works once — the moment a new message arrives or you scroll
back through history, you have to toggle it on and off again, message after
message.

Auto Translator for Discord fixes that. It watches the chat and translates
every message into English the instant it appears — automatically.

HOW IT WORKS

✔ Live translation — new incoming messages are translated the moment they
  render. No clicking, no toggling, no re-translating the page.
✔ Works everywhere in the chat — new messages, edited messages, scrolled-back
  history, and channel switches are all picked up automatically.
✔ In-place replacement — translated text replaces the original and is shown in
  bold, so you can tell it apart from messages that were already in English.
✔ Originals preserved — hover any translated message to see the original text.
✔ Markup-safe — custom emojis, @mentions, and links survive untouched.
✔ Language-aware — messages already in English are detected and left alone.
✔ One-click toggle — click the toolbar icon to switch translation ON or OFF;
  original text is restored instantly.

PRIVACY

Message text is sent to Google's translation service solely to retrieve a
translation. Nothing is collected, stored, logged, or shared. No analytics, no
tracking, no ads. The only saved data is your ON/OFF preference, kept locally
in your browser. The extension runs exclusively on discord.com.

OPEN SOURCE

The complete source code is available at
https://github.com/HYAIPE/Auto-Translator-for-Discord — issues and contributions
welcome. Built by HYAIPE.

NOTE

Works with Discord in the Chrome browser. Not affiliated with, endorsed by, or
sponsored by Discord Inc. or Google LLC.
```

**Category:** Productivity → Tools
**Language:** English

**Graphic assets**

- Store icon 128×128: `icons/icon128.png` (already in the package)
- Screenshots (1–5, 1280×800 or 640×400): capture a translated chat. Use a
  test server or blur usernames and any private content.
- Small promo tile 440×280: optional.

## Privacy tab

**Single purpose description**

```
Automatically translates chat messages on discord.com into English in real
time as they appear, including new incoming messages, edited messages, and
messages loaded by scrolling back through history.
```

**storage justification**

```
Used to persist a single boolean preference (translation ON/OFF) set via the
toolbar icon, so the user's choice is remembered across browser sessions. No
other data is stored.
```

**Host permission justification** (`translate.googleapis.com`)

```
The extension sends the text of chat messages displayed on discord.com to
Google's translation endpoint (translate.googleapis.com) and receives the
translated text back. This is the extension's sole function. The host
permission is required because Manifest V3 service workers must declare hosts
they fetch from; no other host is contacted.
```

**Remote code:** No, I am not using remote code. (Only translation *data* is
fetched as JSON; no external scripts or wasm are loaded or executed.)

**Data usage:**

- Check **"Personal communications"** — the data sent off-device is chat
  message text, which is Google's own example for this category (not the
  generic "Website content" bucket).
- Leave everything else unchecked (no PII, health, financial, authentication,
  location, web history, or user activity data is collected).
- Certify all three disclosures: data is **not** sold or transferred outside
  approved use cases, **not** used for purposes unrelated to the single
  purpose, and **not** used for creditworthiness/lending.

**Privacy policy URL**

```
https://github.com/HYAIPE/Auto-Translator-for-Discord/blob/main/PRIVACY.md
```

## Distribution tab

- **Visibility:** Public, or **Unlisted** for a lighter footprint (installable
  via direct link only).
- **Regions:** All regions.

## Account requirements (one-time)

- Pay the one-time $5 developer registration fee.
- Verify the publisher contact email (hyaipe.io@gmail.com) under
  **Account** → it must be verified before you can publish.
- Enable 2-Step Verification on the Google account (required to publish).

## On every future update

1. Bump `"version"` in `manifest.json` (e.g. `1.0.1`).
2. Rebuild the zip: `tar -a -cf auto-translator-for-discord-vX.Y.Z.zip manifest.json background.js content.js icons`
3. Upload via **Package** → **Upload new package** and resubmit.
