# IME Field Guide

A single-page guide to CJK input method (IME) issues, with Microsoft and Apple examples for Chinese (Simplified and Traditional), Japanese and Korean.

## What is inside

- **Basics**: how keys become text, which events an app receives, and six IME bug families to test for.
- **Microsoft vs Apple**: side-by-side examples for each language.
- **Bug Lab**: 11 hands-on labs (5 Japanese, 4 Korean, 2 Chinese) covering the six bug families. You type with your own IME in real input boxes, follow numbered steps, and the page reads the browser's real events to tell you whether the bug showed up. Each lab lists the exact input source, layout and mode for Windows (Microsoft IME) and macOS (Apple IME), has a buggy and a fixed version of the demo app, and drafts a bug report you can copy.
- **Live Inspector**: type with your own IME and see every composition and key event.

## Bug Lab scenarios

| Code | Family | Scenario |
|---|---|---|
| JA-1 | Hotkey leak | Space plays the video while you convert |
| JA-2 | Enter submits early | Enter sends the message while you confirm |
| JA-3 | Full-width leakage | Full-width digits in a frame field |
| JA-4 | Lost composition | The app rewrites the box and drops your draft |
| JA-5 | Candidate window position | Candidate list far from the caret |
| KO-1 | Hotkey leak | Space and number keys leak while you type Hangul |
| KO-2 | Enter submits early | Enter sends and leaves the last syllable behind |
| KO-3 | Key code vs character | Ctrl or Cmd shortcuts fail in Hangul mode |
| KO-4 | Lost composition | The app rewrites the box and breaks the syllable |
| ZH-1 | Full-width leakage | Full-width colon in a timecode (Simplified) |
| ZH-2 | Hotkey leak | Tone keys select tracks (Traditional) |

## Run it

Open `index.html` in a browser. No build step. Fonts load from Google Fonts.

The labs need the matching input source installed and a hardware keyboard. A standard US QWERTY layout is assumed.

## Note

The scenarios model common bug classes, not specific tracked bugs. Exact behavior varies by OS version, IME version, browser and settings. Some labs (for example KO-3 and the Enter labs) give different results on different platforms, and the page reports what your browser actually received. Confirm on your own build before relying on any example.
