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
https://github.com/HYAIPE/DiscordTranslator — issues and contributions
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
Automatically translates Discord chat messages into English as they appear on
discord.com.
```

**Permission justifications**

| Permission | Justification |
|---|---|
| `storage` | Stores a single ON/OFF preference for the translation toggle. No other data is stored. |
| Host `translate.googleapis.com` | Sends visible message text to Google Translate to retrieve translations — the extension's single core function. |
| Content script on `discord.com` | Required to read chat messages and display their translations in place. |

**Remote code:** No, I am not using remote code. (Only translation *data* is
fetched; no external scripts are loaded or executed.)

**Data usage:**

- Check **"Website content"** (message text is transmitted to Google Translate
  to provide the extension's single purpose).
- Leave everything else unchecked (no personally identifiable information, no
  authentication data, no location, etc.).
- Certify: data is **not** sold, **not** used for purposes unrelated to the
  single purpose, **not** used for creditworthiness.

**Privacy policy URL**

```
https://github.com/HYAIPE/DiscordTranslator/blob/main/PRIVACY.md
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
