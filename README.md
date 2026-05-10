# Scale Suicide 🎸

A web-based chromatic scale and arpeggio practice tool for guitarists. Randomizes all 12 keys, runs a precision Web Audio metronome (static or BPM-ramp mode), tracks session time, and logs progress to Excel. Built for daily practice. No install, no server — open and play.

## What it does

Each session presents all 12 notes in random order (or following the circle of fifths/fourths). For each note, you play the selected scale or arpeggio type at the metronome tempo, then press **Next Note** to advance. The stopwatch tracks your total session time. When all 12 are done, a modal asks how it went — you rate the session and save a cumulative Excel log.

## Features

- **"Executed by"** — select Scales or Arpeggios before each session; logged in the Excel output for filtering and comparison
- **Randomized 12-key rotation** with automatic enharmonic notation — the app picks sharps or flats based on the correct key signature for each scale type, no manual selection needed
- **7 scale types** — Major, Dominant 7th, Natural Minor, Harmonic Minor, Melodic Minor, Whole-Half, Half-Whole
- **Key order modes** — Random, Circle of 5ths, Circle of 4ths
- **Accidentals display** — shows the scale's altered notes in two orderings: circle-of-fifths order and scale-degree order, with an eye toggle to hide/reveal (useful for ear training)
- **Precision Web Audio metronome** — lookahead scheduler with pre-synthesized AudioBuffer clicks for accurate timing at any tempo and over long sessions
  - Static mode: fixed BPM (20–280)
  - Ramp mode: gradual BPM increase from start to end tempo, configurable increment and measures per step
- **Configurable time signature** — 1 to 8 beats per bar
- **Beat buttons** — click to cycle each beat between normal, accented (higher pitch), and silent
- **Stopwatch** with pause/resume, current time display, and automatic screen wake lock (prevents screen from turning off during practice)
- **Session rating modal** — "Did you survive?" appears on Save: Whooohooo / OK / Nah
- **Excel export** — cumulative log with all session parameters and color-coded rating column (green / orange / red); CSV fallback if offline
- **Persistent history** — sessions stored in browser localStorage, separate per browser/device
- **iOS silent switch bypass** — audio works even with the iPhone silent switch on

## How to use

1. Select exercise type (Scales or Arpeggios) and scale type
2. Choose key order (Random / Cr.5ths / Cr.4ths) and set metronome parameters
3. Press **Start** — the first random note appears, metronome and stopwatch begin, screen stays on
4. Play that scale/arpeggio in tempo, then press **Next Note** (or hit Spacebar on desktop)
5. Repeat until **12/12** — press **Finish**
6. A modal appears: rate your session, then press **Save** to download the updated Excel log

## Notation

The app automatically uses the correct enharmonic notation for each scale type and root:
- **Major / Natural Minor** — standard key signatures (E major = F# C# G#  D#; Bb major = Bb Eb)
- **Dominant 7th** — one flat more than the corresponding major (G Mixolydian = no accidentals; C Mixolydian = Bb)
- **Harmonic / Melodic Minor** — same key signature base as natural minor, with raised degrees spelled correctly
- **Octatonic scales** — jazz-standard mixed notation, hardcoded per root

## Tech stack

Pure HTML + CSS + Vanilla JavaScript. No frameworks, no build step. Single file.

- Web Audio API with lookahead scheduling and pre-synthesized AudioBuffer clicks
- Screen Wake Lock API (keeps screen on during session; Safari iOS 16.4+, all modern desktop browsers)
- ExcelJS (loaded from CDN on save, CSV fallback if unavailable)
- localStorage (session history persistence)

## Running locally

Just open `index.html` in any modern browser. No server required.

## License

MIT License — see [LICENSE](LICENSE)Sonnet 4.6Adaptive
