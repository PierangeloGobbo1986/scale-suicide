# Scale Suicide 🎸

A web-based scale and arpeggio practice tool for guitarists. Inspired by the basketball conditioning drill of the same name — sprint through all 12 keys, survive. Randomizes root notes, runs a precision Web Audio metronome, tracks session time, and logs progress to a cumulative Excel file. No install, no server — open and play.

## What it does

Each session presents all 12 root notes (in random order, or following the circle of fifths/fourths). For each root, you play the assigned scale or arpeggio type at the metronome tempo in the selected execution style, then press **Next Note** to advance. When all 12 are done, a modal asks how it went — rate the session and save to the Excel log.

## Features

### Exercise configuration
- **"Executed by"** — select Scales or Arpeggios before each session
- **Scale types** — Major, Dominant 7th, Natural Minor, Harmonic Minor, Melodic Minor, Whole-Half, Half-Whole
- **Arpeggio types (4-voice)** — Maj7, 7, min7, min7b5, dim7, minMaj7, Maj7♯5, 7sus4, Maj6, min6
- **Execution modes for scales** — Box, 3 notes/string, 2 notes/string, 4 notes/string
- **Execution modes for arpeggios** — Box, Diatonic approach ↓/↑, Diatonic enclosure, Chromatic approach ↓/↑, Chromatic enclosure, Pivot, Triplet
- **Box/fret position** — shown automatically when Box is selected (scales) or always (arpeggios); 13 positions from 0-4 (open) to 12-16; randomized with the **Change** button
- **⚤ Random** — randomizes exercise type and execution mode in one click

### Note ordering
- Random (default), Circle of 5ths, Circle of 4ths
- Automatic enharmonic notation — the app picks sharps or flats based on the correct key signature for each scale type and root, no manual selection needed

### Accidentals display
- Shows the scale's altered notes in two orderings: circle-of-fifths order and scale-degree order
- Eye toggle to hide/reveal (useful for ear training)
- Automatically hidden for arpeggios

### Metronome
- Precision Web Audio engine with lookahead scheduling and pre-synthesized AudioBuffer clicks — accurate at any tempo and over long sessions
- **Static mode** — fixed BPM (20–280), default 80
- **Ramp mode** — gradual BPM increase from start to end tempo, configurable increment and measures per step
- Configurable time signature (1–8 beats per bar), all beats equal by default
- Beat buttons — click to cycle each beat: normal → accented (higher pitch) → silent

### Session tracking
- Stopwatch with pause/resume support
- Screen Wake Lock — prevents the screen from turning off during practice (Safari iOS 16.4+, all modern desktop browsers)
- Session rating modal on Save — "Did you survive?": Whooohooo / OK / Nah
- Persistent history via browser localStorage (separate per browser/device)
- **Excel export** — cumulative log with color-coded rating column (green/orange/red) and all session parameters; CSV fallback if offline

### Excel columns logged per session
Rating · Exercise (Scales/Arpeggios) · Type · Execution · Box/Frets · Date · Scale · Metro Mode · BPM · Increment · Meas/Step · Beats/Bar · Time · Time (ms)

## How to use

1. Select exercise type, scale/arpeggio type, and execution mode in the **Executed by** panel (or hit **⚤ Random**)
2. Set metronome parameters; hit **Change** to get a new fret box if needed
3. Press **Start** — first random note appears, metronome begins, screen stays on
4. Play in tempo, press **Next Note** (or **Spacebar** on desktop)
5. Repeat until **12/12**, press **Finish**
6. Rate the session in the modal, press **Save** → Excel file downloads

## Notation

Automatic enharmonic notation per scale type and root:
- **Major / Natural Minor** — standard key signatures
- **Dominant 7th** — one flat more than the corresponding major
- **Harmonic / Melodic Minor** — natural minor key signature base with raised degrees spelled correctly
- **Octatonic scales** — jazz-standard mixed notation, hardcoded per root

## Tech stack

Pure HTML + CSS + Vanilla JavaScript. Single file, no frameworks, no build step.

- Web Audio API — lookahead scheduler with pre-synthesized AudioBuffer clicks
- Screen Wake Lock API (iOS Safari 16.4+, all modern desktop browsers)
- ExcelJS from CDN on save (CSV fallback if unavailable)
- localStorage for session history

## Running locally

Open `index.html` in any modern browser. No server required.

## License

MIT License — see [LICENSE](LICENSE)
