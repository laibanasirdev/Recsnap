# RecSnap

A free screen recorder Chrome extension. Click the toolbar icon, hit Start Recording, and your video auto-downloads when you stop. No account, no upload, no backend.

## Features

- Record full screen, a window, or a browser tab
- Optional microphone audio (mixed with system audio)
- Quality selector: 1080p, 720p, 480p
- Pause and resume mid-recording
- Live timer with recording indicator
- In-session recording history
- Auto-downloads as `.webm`
- Dark UI, no dependencies

## Installation

1. Clone or download this repo
2. Open Chrome and go to `chrome://extensions`
3. Enable **Developer mode** (toggle in the top right)
4. Click **Load unpacked** and select this folder
5. The RecSnap icon will appear in your Chrome toolbar

## Usage

1. Click the RecSnap icon in the toolbar
2. Choose a source: **Screen**, **Window**, or **Tab**
3. Select a quality (720p default)
4. Toggle **Mic** on if you want microphone audio
5. Click **Start Recording** — Chrome will prompt you to choose what to share
6. Use **Pause** / **Resume** as needed
7. Click **Stop** — the recording auto-downloads to your Downloads folder

## Files

| File | Purpose |
|------|---------|
| `manifest.json` | Chrome extension configuration (Manifest V3) |
| `popup.html` | Full UI and recording logic |
| `background.js` | Service worker (minimal) |
| `icons/` | Extension icons at 16×16, 48×48, 128×128 px |

## Output Format

Recordings are saved as `.webm` with the filename `RecSnap_YYYY-MM-DDTHH-MM-SS.webm`. The exact codec used depends on what Chrome supports (`vp9+opus` preferred).

## Permissions

| Permission | Reason |
|------------|--------|
| `activeTab` | Identify the current tab |
| `downloads` | Trigger the auto-download |
| `storage` | Reserved for future settings persistence |

Screen/audio capture uses the browser's built-in `getDisplayMedia` API — no extra permissions required.

## Browser Support

Chrome 88+ (Manifest V3 required). Does not work in Firefox or Safari as a Chrome extension.
