# Scale Suicide 🎸💀

A web-based scale and arpeggio practice tool for guitarists. Inspired by the basketball conditioning drill of the same name — sprint through all 12 keys, survive. Randomizes root notes, runs a precision Web Audio metronome, tracks session time, and logs cumulative progress to Excel. No install, no server — open and play. Works as a home screen app on iPhone via Safari.

## What it does

Each session presents all 12 root notes in random order (or following the circle of fifths/fourths). For each root, you play the assigned scale or arpeggio type at the metronome tempo in the selected execution style, then press **Next Note** to advance. When all 12 are done, the app automatically scores the session against your Personal Best and saves to the Excel log.

## Features

### Exercise configuration
- **"Executed by"** — select Scales or Arpeggios before each session
- **💀 Random** — randomizes exercise type and execution mode in one click
- **Scale types** — Major, Dominant 7th, Natural Minor, Harmonic Minor, Melodic Minor, Whole-Half, Half-Whole
- **Arpeggio types (4-voice)** — Maj7, 7, min7, min7b5, dim7, minMaj7, Maj7♯5, 7sus4, Maj6, min6
- **Execution modes for scales** — Box, 3 notes/string, 2 notes/string, 4 notes/string
- **Execution modes for arpeggios** — Box, Diatonic approach ↓/↑, Diatonic enclosure, Chromatic approach ↓/↑, Chromatic enclosure, Pivot, Triplet
- **Box/fret position** — always shown for arpeggios, shown for Box mode on scales; 13 positions from 0-4 (open) to 12-16; **Change** button randomizes on demand

### Note ordering
- Random (default), Circle of 5ths, Circle of 4ths
- Automatic enharmonic notation — sharps or flats chosen from the correct key signature for each scale type and root

### Theory display panel
- **COF row** — scale accidentals in circle-of-fifths order
- **Scale row** — all notes of the scale in ascending order; chord tones for arpeggios
- **Maj. Rel. box** — relative major note, shown only where musically relevant:
  - Natural / Harmonic / Melodic Minor → relative major (e.g. Ab min → Cb)
  - Dominant 7th / Mixolydian → parent major key (e.g. G Mix → C)
  - Major, octatonic, arpeggios → —
- Eye toggle to hide/reveal all theory fields (useful for ear training)

### Metronome
- Precision Web Audio engine — lookahead scheduler with pre-synthesized AudioBuffer clicks, accurate at any tempo over long sessions
- iOS silent switch bypass — audio plays even with the iPhone mute switch on
- Standalone ▶/⏹ button to run the metronome without starting a session
- **Static mode** — fixed BPM (20–280), default 80
- **Ramp mode** — gradual BPM increase from start to end tempo, configurable increment and measures per step
- Configurable time signature (1–8 beats per bar), all beats equal by default
- Beat buttons — click to cycle each beat: normal → accented (higher pitch) → silent

### Automatic scoring (Personal Best)
- Metric: **total session time** (mm:ss.cc) — independent of BPM choice
- Compared against your best time for the same scale/arpeggio type
- **Whooohooo** — within 110% of your PB
- **OK** — between 110% and 140% of your PB
- **Slow Study** — more than 140% of your PB
- **New PB** — first time for that type, or you beat your record
- Feedback message shown after every save: time, PB comparison, percentage

### Session tracking
- Stopwatch with pause/resume
- Screen Wake Lock — prevents screen from turning off during practice (Safari iOS 16.4+, all modern desktop browsers); also active when metronome runs standalone
- Persistent history via browser localStorage (separate per browser/device)
- **Import history** — load a previous Excel log to restore full history on a new device (replaces current history with file contents)
- **Excel export** — cumulative log downloaded as `scale_suicide_log.xlsx` after every session; CSV fallback if offline

### Excel columns logged per session
Rating · Exercise · Type · Execution · Note Order · Box/Frets · PB time · vs PB · Date · Metro Mode · BPM · Increment · Meas/Step · Beats/Bar · Time · Time (ms)

## How to use

1. Select exercise type, scale/arpeggio type, and execution mode in the **Executed by** panel (or hit **💀 Random**)
2. Set metronome parameters; use standalone ▶ to test tempo; hit **Change** to get a new fret box if needed
3. Press **Start** — first random root note appears, metronome begins, screen stays on
4. Play in tempo, press **Next Note** (or **Spacebar** on desktop)
5. Repeat until **12/12** — the last **Next Note** becomes **Save**
6. Session is scored automatically and Excel file downloads

## Add to iPhone home screen

1. Open Safari and go to your GitHub Pages URL
2. Tap the **Share** button (square with arrow, bottom centre)
3. Tap **"Add to Home Screen"**
4. Name is pre-filled as "Scale Suicide" — tap **Add**

The app opens full-screen with no browser chrome, like a native app.

## Notation

Automatic enharmonic notation per scale type and root:
- **Major / Natural Minor** — standard key signatures
- **Dominant 7th** — one flat more than the corresponding major
- **Harmonic / Melodic Minor** — natural minor key signature base, raised degrees spelled correctly
- **Octatonic scales** — jazz-standard mixed notation, hardcoded per root
- **Arpeggios** — sharp or flat names based on root's key context

## Tech stack

Pure HTML + CSS + Vanilla JavaScript. Single file, no frameworks, no build step.

- Web Audio API — lookahead scheduler with pre-synthesized AudioBuffer clicks
- Screen Wake Lock API (iOS Safari 16.4+, all modern desktop browsers)
- ExcelJS from CDN on save (CSV fallback if unavailable)
- localStorage for session history
- PWA manifest + apple-touch-icon for home screen installation

## Files

| File | Purpose |
|---|---|
| `index.html` | Main app (rename from `scale_suicide.html`) |
| `apple-touch-icon.png` | Home screen icon for iOS (180×180) |
| `icon-512.png` | PWA icon (512×512) |
| `manifest.json` | PWA manifest for home screen install |

## Running locally

Open `index.html` in any modern browser. No server required.

## License

MIT License — see [LICENSE](LICENSE)
