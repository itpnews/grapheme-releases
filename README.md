<p align="center">
  <img src="assets/icon.png" width="128" height="128" alt="Grapheme icon">
</p>

<h1 align="center">Grapheme</h1>

<p align="center">
  On-device push-to-talk voice dictation for macOS — no cloud involved.
</p>

<p align="center">
  <a href="https://github.com/itpnews/grapheme-releases/releases/latest"><img src="https://img.shields.io/github/v/release/itpnews/grapheme-releases?label=version" alt="Latest release"></a>
  <img src="https://img.shields.io/badge/platform-macOS%2014%2B-blue" alt="macOS 14+">
  <img src="https://img.shields.io/badge/notarized-Apple-success" alt="Notarized by Apple">
</p>

---

Grapheme transcribes speech entirely on-device using [WhisperKit](https://github.com/argmaxinc/WhisperKit) on the Neural Engine — no audio ever leaves your Mac. Hold a key, speak, release — the recognized text is inserted right where your cursor is.

## Download

→ **[Latest release](https://github.com/itpnews/grapheme-releases/releases/latest)**

Download `Grapheme-vX.Y.Z.dmg`, open it, and drag `Grapheme.app` into `Applications`.

The build is signed with a Developer ID (`The Metaverse Apps OU`) and notarized by Apple, so Gatekeeper lets it run without warnings.

## How it works

1. Hold **Right ⌥ Option** (the default hotkey) and speak.
2. Release the key — a moment later, the transcribed text appears in whatever field is focused.
3. If the focused app doesn't support programmatic text insertion, the text is copied to the clipboard instead.

Grapheme recognizes Russian and English in the same sentence without switching keyboard layouts, adds punctuation automatically, and cleans up filler words and stray anglicisms/loanwords, restoring them to their original spelling.

A live demo is built into first-run onboarding, so you can see it working before you ever have to dictate blind.

## Permissions

Grapheme needs three system permissions, and it explains each one during onboarding:

| Permission | Why |
|---|---|
| **Input Monitoring** | Detect when the hotkey is pressed and released |
| **Accessibility** | Insert the recognized text into the focused app |
| **Microphone** | Record audio for transcription while the hotkey is held |

Audio and text never leave the device — recognition runs fully offline once the model is downloaded.

## Auto-updates

Grapheme checks for updates via [Sparkle](https://sparkle-project.org) and offers to install new versions as they're released. You can also check manually via **Settings → Check for Updates…** from the menu bar.

Updates are published from this repository. The app binary and the appcast feed are signed with separate keys (Developer ID for the app, EdDSA for the appcast), so compromising one channel doesn't let an attacker forge the other.

## Source code

Grapheme's source is closed and developed in a separate private repository. This repo publishes only the signed, notarized binaries and the `appcast.xml` used for auto-updates.

## Feedback

Found a bug or have a suggestion? Open an [issue](https://github.com/itpnews/grapheme-releases/issues) in this repository.

## System requirements

- macOS 14.0 (Sonoma) or later
- Apple Silicon (WhisperKit relies on the Neural Engine)
