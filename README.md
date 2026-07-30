# SRT to VTT Converter

Convert subtitle files between SubRip (.srt) and WebVTT (.vtt) in both directions. The input format is auto-detected, multi-line cues and blank lines are handled, and everything runs in your browser with no external dependencies. Works offline.

## Live demo

https://0xelitesystem.github.io/srt-to-vtt-converter/

## Features

- Both directions: SubRip to WebVTT and WebVTT to SubRip.
- Auto-detects the input format from its header and timestamp style.
- SubRip to WebVTT: adds the `WEBVTT` header and converts comma decimal separators (`00:00:01,000`) to dots (`00:00:01.000`).
- WebVTT to SubRip: adds sequential cue indices, converts dots back to commas, and strips the `WEBVTT` header plus `NOTE`, `STYLE`, and `REGION` blocks.
- Toggle to keep the numeric cue indices as WebVTT cue ids, or drop them.
- Load a file, paste text, or load a built-in example.
- Copy button and a download button that builds the file in-browser with a Blob and object URL.
- Handles multi-line cues, blank lines, and a leading byte-order mark.
- Light and dark themes, keyboard-friendly (Ctrl or Cmd plus Enter to convert).

## How it works

The converter normalizes line endings, splits the text into cue blocks on blank lines, and parses each block into a start time, end time, optional settings, and cue lines. Timestamps are parsed to milliseconds and re-emitted with the target separator, so `00:00:01,000` becomes `00:00:01.000` for WebVTT and back to `00:00:01,000` for SubRip. When converting to SubRip, WebVTT cue settings are dropped because SubRip has no equivalent.

## Privacy

Everything runs in your browser. Files you load with the file picker are read locally with the FileReader API and never uploaded. There are no network requests, no analytics, and no external scripts.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. Copyright 0xelitesystem 2026.
