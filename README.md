# IME Field Guide

A single-page guide to CJK input method (IME) issues, with Microsoft and Apple examples for Chinese (Simplified and Traditional), Japanese and Korean.

## What is inside

- **Basics**: how keys become text, which events an app receives, and nine IME bug families to test for.
- **Microsoft vs Apple**: one comparison table per language.
- **Bug Lab**: 17 hands-on labs (8 Japanese, 5 Korean, 4 Chinese) covering the nine bug families. You type with your own IME in real input boxes, follow numbered steps, and the page reads the browser's real events to tell you whether the bug showed up. Each lab lists the input source, layout and mode for Windows (Microsoft IME) and macOS (Apple IME), has a buggy and a fixed version of the demo app, and drafts a bug report you can copy.
- **Checklist**: where to repeat each check in a real desktop app, checks that have no lab (reconversion, undo, switching away, characters outside the BMP and more), and what to record in every IME bug. Copies as Markdown.
- **Inspector**: type with your own IME and see every composition and key event.

Each lab has its own link, for example `index.html#lab/ko-enter`, so you can send someone straight to one test.

## Bug Lab scenarios

| Code | Family | Scenario |
|---|---|---|
| JA-1 | Hotkey leak | Space plays the video while you convert |
| JA-2 | Enter submits early | Enter sends the message while you confirm |
| JA-3 | Full-width leakage | Full-width digits in a frame field |
| JA-4 | Lost composition | The app rewrites the box and drops your draft |
| JA-5 | Candidate window position | Candidate list far from the caret |
| JA-6 | Navigation key leak | Esc closes the dialog while you cancel the draft |
| JA-7 | Navigation key leak | Arrow keys move the playhead while you pick segments |
| JA-8 | Navigation key leak | Tab picks a prediction, but focus jumps |
| KO-1 | Hotkey leak | Space and number keys leak while you type Hangul |
| KO-2 | Enter submits early | Enter sends and leaves the last syllable behind |
| KO-3 | Key code vs character | Ctrl or Cmd shortcuts fail in Hangul mode |
| KO-4 | Lost composition | The app rewrites the box and breaks the syllable |
| KO-5 | First key lost | Type-to-rename loses the first jamo |
| ZH-1 | Full-width leakage | Full-width colon in a timecode (Simplified) |
| ZH-2 | Hotkey leak | Tone keys select tracks (Traditional) |
| ZH-3 | Acts on draft text | Live search filters on pinyin letters |
| ZH-4 | Acts on draft text | A 6-character limit cuts the pinyin draft |

## Run it

Open `index.html` in a browser. No build step and no external files: the page uses system fonts and picks CJK fonts by language.

The labs need the matching input source installed and a hardware keyboard. A standard US QWERTY layout is assumed.

## Note

The scenarios model common bug classes, not specific tracked bugs. Exact behavior varies by OS version, IME version, browser and settings. Some labs (for example KO-3, KO-5 and the Enter labs) give different results on different platforms, and the page reports what your browser actually received. Confirm on your own build before relying on any example.
