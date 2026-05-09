# scale-suicide general desciption
A web-based chromatic scale practice tool for guitarists. Randomizes all 12 keys, runs a precision Web Audio metronome (static or BPM-ramp mode), tracks session time, and logs progress to Excel. Built for daily practice. No install, no server — open and play.


# Scale Suicide 🎸
A web-based chromatic scale practice tool for guitarists. Randomizes all 12 keys, runs a precision Web Audio metronome (static or BPM-ramp mode), tracks session time, and logs progress to Excel. Built for daily practice. No install, no server — open and play.


## What it does
Each session presents all 12 notes in random order. For each note, you play the selected scale type at the metronome tempo, then press **Next Note** to advance. The stopwatch tracks your total session time. When all 12 scales are done, you rate the session and save a cumulative Excel log.

## Features
- **Randomized 12-key rotation** — sharp or flat notation selectable
- **7 scale types** — Major, Dominant 7th, Natural Minor, Harmonic Minor, Melodic Minor, Whole-Half, Half-Whole
- **Precision Web Audio metronome** — lookahead scheduler for accurate timing
  - Static mode: fixed BPM (20–280)
  - Ramp mode: gradual BPM increase from start to end tempo, configurable increment and measures per step
- **Configurable time signature** — 1 to 8 beats per bar
- **Beat buttons** — click to cycle each beat between normal, accented (higher pitch), and silent
- **Stopwatch** — pause/resume supported
- **Session rating** — Whooohooo / OK / Nah, logged with color coding
- **Excel export** — cumulative log with all session parameters and colored rating column (CSV fallback if offline)
- **Persistent history** — sessions stored in browser localStorage

## How to use
1. Select accidentals (# or ♭) and scale type
2. Set your metronome parameters
3. Press **Start** — the first random note appears and the metronome begins
4. Play that scale in tempo, then press **Next Note**
5. Repeat until **12/12** — press **Finish**
6. Rate your session and press **Save** to download the updated Excel log

## Tech stack
Pure HTML + CSS + Vanilla JavaScript. No frameworks, no build step. Single file.

- Web Audio API (metronome engine with lookahead scheduling)
- ExcelJS (loaded from CDN on save, CSV fallback if unavailable)
- localStorage (session history persistence)

## Running locally
Just open `index.html` in any modern browser. No server required.

## License
MIT License — see [LICENSE](LICENSE)
