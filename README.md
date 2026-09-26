# Scale Suicide 🎸💀

A practice tool for scales and arpeggios in all 12 keys. Inspired by the basketball conditioning drill of the same name: sprint through the 12 keys, survive. It runs a precise Web Audio metronome, times each session, scores it against your Personal Best and keeps a cumulative Excel log. No install, no server. On iPhone it works as a home-screen app.

**Current version: 2.0.0** (shown at the top right of the app)

## How a session works

Pick an exercise, set the metronome, press **Start**. The app shows the 12 roots one at a time following the circle of fifths or fourths; play the scale or arpeggio on each root and press **Next note**. At 12/12 the button becomes **Save**: the session is scored and the Excel log downloads.

## Metronome (top card)

- **Tempo**: tap the big BPM number and type the value (numeric keypad on iPhone). The value is applied when you leave the field, so the tempo never jumps while typing. Range 20 to 280, default 80.
- **▶ / ⏹** runs the metronome on its own, without a session.
- **Beats/bar** (1 to 8). Beat buttons cycle normal ● → accent △ → silent −. Accents on 2 and 4 by default.
- **Mute bars**: 0 means off, every bar plays and Play bars shows ALL. With Mute bars above 0 the metronome plays *Play bars* bars, then stays silent for *Mute bars* bars, and repeats: a drill for your internal pulse.
- **Eye**: open, the beat buttons keep flashing during the silent bars; closed, full blackout.
- **Ramp**: a second row appears with Start BPM, End BPM, Step BPM and Bars/step. The big number then shows the live tempo. Mute bars are not available in Ramp.
- Audio plays even with the iPhone silent switch on, and the screen stays awake while the metronome or a session runs.

## Choosing the exercise

**Executed by: Scales / Arpeggios**, then tap the options to turn them on or off:

| Row | Scales | Arpeggios |
|---|---|---|
| Type | Major, Major Bebop, Dominant 7th, Dominant Bebop, Natural Minor, Minor Bebop, Harmonic Minor, Melodic Minor, Chromatic Jazz, Whole-Half, Half-Whole | Maj7, 7, min7, min7b5, dim7, minMaj7, Maj7♯5, 7sus4, Maj6, min6 |
| Exec | 3, 2 or 4 notes/string, Box | Chromatic approach ↑, CA + Triplet & landing, Diatonic approach ↓, Enclosure 4 notes, Pivot |
| Position | | Box, Along a string |

- One option on per row defines the exercise directly. With several options on, the big **💀 Generate Exercise** button at the bottom of the card draws one combination among them, never the same one twice in a row.
- **All / None** at the end of a row switches the whole row.
- Exec and Position are guitar-specific and can all be off: the exercise is then just the scale or arpeggio type, useful on any instrument.
- For scales, Box is an alternative fingering to 2/3/4 notes per string. For arpeggios, Box and Along a string combine with the technique (e.g. Enclosure 4 notes in a box). Generate Exercise also draws the box.
- The selection is locked while a timed session runs.

## The note card

- The exercise is written in large yellow text at the top, one line each for type, execution and position; when a box is in play, its frets appear right below with a **Change** button (e.g. *min7b5 arpeggio*, *Enclosure 4 notes*, *Box: frets 5–9 [Change]*).
- **Cr.5ths / Cr.4ths** set the order of the 12 roots for the timed session (default Cr.5ths).
- **Random note** shows a random root with its notes for free practice anywhere on the neck. It does not start the timer and is not saved.
- **Progress** counts 0/12 to 12/12.
- Theory rows (the eye hides them for self-testing):
  - Scales: **COF** lists the accidentals in circle-of-fifths order (for Chromatic Jazz, the key signature of the major key); **Scale** lists the notes; **Maj. Rel.** shows the relative major for minor scales, the parent major for Dominant 7th and Dominant Bebop (a fourth up) and for Minor Bebop (a whole step down).
  - Arpeggios: **Formula** (e.g. 1 b3 5 b7) and **Chord** (the chord tones).

## Notation

Rigorous spelling: every scale degree and chord tone keeps its own letter, so Cm7 is C Eb G Bb and C°7 is C Eb Gb Bbb. The root name follows the family of the exercise, so no theoretical keys appear:

| Family | Roots |
|---|---|
| Major, dominant, Maj7, 7, Maj6, Maj7♯5, 7sus4 | C Db D Eb E F F# G Ab A Bb B |
| Minor scales, min7, minMaj7, min6 | C C# D Eb E F F# G G# A Bb B |
| min7b5 | C C# D D# E F F# G G# A Bb B |
| dim7 | C C# D D# E F F# G G# A A# B |

Double accidentals (x = double sharp, bb = double flat) remain only where theory requires them: C°7 (Bbb), F°7 (Ebb), G# harmonic, melodic and bebop minor (Fx), G#minMaj7 (Fx), Major Bebop and Maj7♯5 on F# and B (Cx, Fx).

Scale definitions, in C:

| Scale | Notes |
|---|---|
| Major Bebop | C D E F G G# A B |
| Dominant Bebop | C D E F G A Bb B |
| Minor Bebop (dorian with major 7th) | C D Eb F G A Bb B |
| Chromatic Jazz | C C# D D# E G F F# G G# A A# B D C |
| Whole-Half | C D Eb F Gb Ab A B |
| Half-Whole | C Db Eb E F# G A Bb |

Chromatic Jazz climbs chromatically and reaches the 4th and the octave through the diatonic note above (E G F, B D C). Its passing notes use the simplest name, as in the C example; the octatonic scales use the standard jazz spelling.

## Scoring (Personal Best)

- Metric: total session time, compared with your best time for the same scale or arpeggio type.
- **Whooohooo** within 110% of your PB, **OK** up to 140%, **Slow Study** beyond. The first session of a type sets the PB.
- The message after each session shows time, PB and percentage, and stays visible until the next Start.

## Session log

- History is stored in the browser (localStorage) and the full log downloads as `scale_suicide_log.xlsx` after every session (CSV if Excel is unavailable).
- Columns: Rating · Exercise · Type · Execution · Position · Note Order · Box/Frets · PB time · vs PB · Date · Metro Mode · BPM · Increment · Meas/Step · Beats/Bar · Play/Mute bars · Time · Time (ms)
- **Import history** loads an Excel log and replaces the current history (after confirmation). Missing PB time and vs PB values are rebuilt in chronological order.
- **Clear log** deletes the history.

## Updating and installing on iPhone

- **Update app** (top right) reloads the latest version from GitHub, bypassing the cache. It asks for confirmation during a session.
- To install: open the GitHub Pages URL in Safari → Share → **Add to Home Screen** → Add. The app opens full screen.

## Files

| File | Purpose |
|---|---|
| `index.html` | The app |
| `apple-touch-icon.png` | iOS home-screen icon (180×180) |
| `icon-512.png` | PWA icon (512×512) |
| `manifest.json` | PWA manifest |

## Tech

Single HTML file, vanilla JavaScript, no build step. Web Audio look-ahead scheduler with pre-synthesized clicks, Screen Wake Lock, ExcelJS loaded from a CDN when saving, localStorage for history.

## Version history

**2.0.0** (September 2026)
- Metronome moved to the top; sliders replaced by numeric fields; tempo typed on the big BPM number; single row with Beats/bar, Mute bars, Play bars and an eye for visual beats; Ramp settings on a second row.
- Exercise options shown as on/off buttons with All/None, drawn by a large **Generate Exercise** button; the box detail and its Change button moved to the note card, next to the exercise you look at while playing.
- New scales: Major Bebop, Dominant Bebop, Minor Bebop, Chromatic Jazz. New arpeggio executions and positions (Box, Along a string).
- Note card rebuilt: full exercise description in large text, Random note, circle of fifths or fourths only for timed sessions, formula row for arpeggios.
- Notation fixed: arpeggios spelled by chord degree (46 of 120 spellings were wrong), Half-Whole on F# and B corrected, minor roots spelled C# and G# instead of Db and Ab.
- Log: new Position and Play/Mute bars columns; import now keeps PB time and rebuilds it when missing; dates typed in Excel are read correctly.
- Version number and Update app button; layout clears the iPhone status bar in full-screen mode.

**1.x**
- Random 12-key sessions, Web Audio metronome with static and ramp modes, beat accents, mute bars, automatic Personal Best scoring, Excel log with import, iPhone home-screen support.

## License

MIT License. See [LICENSE](LICENSE).
