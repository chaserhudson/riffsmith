# Linesmith

**Draw a shape, choose how it travels.** Linesmith generates guitar practice lines: you give it a chord progression and a melodic shape, and it writes the shape through every chord as standard notation, with playback. Everything lives in one file — open `Linesmith.html` in a browser (Chrome recommended). No install, no server, works offline. Songs save to the browser's local storage.

---

## Quick start

1. Open `Linesmith.html`.
2. Pick a song: search the **Songbook** (1,461 jazz tunes), hit the 🎲 for a random one, or build your own bars.
3. Pick a figure from the Pattern **Preset** menu, or draw one on the grid.
4. Hit **▶ Play**.

The score re-generates instantly on every change.

---

## The Song card

Three ways to enter changes, via the tabs top-left:

- **Build** — the bar strip. Click any bar to edit it: pick a root + quality, set beats, add a second chord in the bar, duplicate / insert / move / delete bars. **N.C.** quality = rest bar. **Start from** drops in a common progression (ii–V–I, blues, etc.) written in your key.
- **Type** — the same progression as text. Bars split with `|`, two chords in a bar share it (or set beats like `Dm7:2`), `%` repeats the previous bar, `T34` switches meter, `N.C.` = no chord. Hit **Apply**.
- **Import iReal** — drop an iReal Pro export (.html) on the drop zone or paste an `irealb://` link. Only the chords come across.

Also in the card head:

- **Songbook** — type a few letters, pick a tune; its changes load ready for a pattern.
- **Key** — key signature and note spelling. **Play in** transposes the whole exercise.
- **Repeat all** — loop the progression up to 32×.
- **Cycle all 12 keys by** — repeat the exercise through every key, moving by half steps, 4ths, whatever you choose. The classic "all keys" workout.

## The Pattern card

The shape walks a **pool** of notes — the chord tones or the chord scale. On the grid: row **1** is home, rows above step up the pool, rows below dip under it; each column is one step in time. Click a cell to place a note; click again to cycle it: pool note → ‹ half-step-below approach → › half-step-above → « scale-step-below → » scale-step-above → rest. Bottom row = rest. Faint ghost dots preview where Travel takes the shape next.

- **Preset** loads a figure (replaces the whole pattern). **+ rotate** appends it as a new bar-shape instead; **↳ shape** swaps only the selected shape.
- **🎲 Random** rolls 1–4 patterns from presets and/or your saved ones.
- **Shape tabs (A, B, …)** — multiple shapes rotate bar by bar. Each shape can carry its own **pool** and **travel** (the small selects above the grid).
- **− / + steps** changes the shape length; transforms: **⇆ Reverse**, **⤁ There & back** (appends the mirror), **↕ Flip** (upside-down around home), **Clear**.
- **as text** — the grid and the text box are the same thing, two-way synced. `1 2 3 4` = pool steps, `-1` dips below, `0`/`r` = rest, `<n`/`>n` = chromatic approach, `<<n`/`>>n` = scale-step approach, `;` starts the next bar-shape, `chord:`/`scale:` sets a shape's pool, `@up2 @down1 @stay @z2:1` gives a shape its own travel. **☆ Save** adds the pattern to your list.

### Travel — how the shape moves

After each pass the shape slides through the pool: **↓ Down / • Stay / ↑ Up / ⇅ Up & down**, by 1–4 steps, bouncing at the register edges. Up & down gets a ratio slider (e.g. ↑2:↓1 = two steps up, one back — the classic sequence). **Turn the shape around at the register edges** plays it upside-down on the way back.

### Context controls (right column)

- **Notes from** — chord tones, chord scale, or **alternate** between them bar by bar (slider sets the ratio, e.g. 2 chord bars : 1 scale bar).
- **Scale** — auto (each chord's recommended scale), pentatonic (matches chord), major/minor pentatonic, blues, harmonic or melodic minor.
- **Start each chord on** — which pool note home lands on at a chord change: root, 2nd–4th tone, or **closest to last note** for seamless voice-leading (with a no-repeat variant).
- **Register** — guitar position presets, a custom written range, or a **fret window** (only notes playable between two frets, standard tuning, enter the pool).
- **Rhythm** — quarters / eighths / triplet 8ths / sixteenths, plus per-bar rhythm-group figures.
- **Connect chords smoothly** — keeps the line from jumping at changes.

## Bars — per-bar overrides

Below the score, open **Bars** and click a chip: that bar can get its own pattern, travel, rhythm, start note (with ▲▼ nudge), notes-from, register, and rhythm group. A bar's own override beats the shape's `@` tag. **Use song defaults** clears one bar; **Reset all bars** clears everything.

## Score & playback

- The score is engraved live (abcjs). **☾ dark score** draws it light-on-dark; print/PDF always stay black on white.
- Transport: **▶ Play**, tempo 40–240 bpm, **Loop**, **Count-in**, instrument sound (guitars, piano, voice), **Backing** chords on/off. The cursor tracks the score during playback.

## Library, versions, sharing, export

- **Save version** stores the current setup as a new version of the song (V1, V2, …) — pick versions from the top-bar dropdown. **Delete** removes the version (or the whole song if it's the last one). Everything is in browser localStorage, so it's per-browser and per-machine.
- **🔗** copies a share link that reopens the exact exercise — song, pattern, and all settings — on any machine.
- **Export**: **PDF**, **Print**, **XML** (MusicXML — opens in MuseScore / Guitar Pro), **MIDI**.

---

## Files in this folder

| File | What it is |
|---|---|
| `Linesmith.html` | **The app** — the current production version. Everything above describes this file. |
| `Index.html` | Byte-identical copy of `Linesmith.html`, named for web hosting (servers serve `index.html` as the homepage). Keep the two in sync when updating. |
| `Linesmith Ultimate_Guitar_Beta.html` | Beta with one addition: **Ultimate Guitar import** in the Import tab. Paste a UG song URL and Import — chords, title, artist, and key come across, one chord per bar (chord sheets carry no timing; tidy up in the bar strip). Works with community **Chords** pages; **Official** tabs contain no chord text, so it auto-searches and imports the top community Chords version. If fetching is blocked, select-all-copy the UG page and paste into the text box — saved UG pages (.html) also work in the drop zone. |
| `Linesmith Launch Plan.md` | Roadmap for taking Linesmith public (naming, hosting, pricing, marketing). |
| `Tab Integration Options.md` | Research doc on adding guitar tablature (abcjs native tabs vs. alphaTab vs. VexFlow vs. OSMD), with a recommended path. |
| `README.md` | This file. |

---

## Tips

- The fastest workflow: Songbook 🎲 → Pattern 🎲 Roll → Play. Endless material.
- Pattern text is the power tool — e.g. `1 2 3 4 @down1 ; scale: 1 3 2 4 @up2` = shape A on chord tones falling by 1, alternating bar-by-bar with shape B on the scale climbing by 2.
- Since songs live in localStorage, use the 🔗 share link or XML export to move an exercise between machines or back it up.
