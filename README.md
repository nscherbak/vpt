# Vocal Pitch Trainer

A browser-based ear-training and vocal intonation tool. Hear a note, sing it back, and see how close you were — measured in cents against the target pitch.

Created by **N. Scherbak**.

No build step, no dependencies, no server. One HTML file that runs entirely in your browser using the Web Audio API. Nothing is uploaded; the microphone audio never leaves your device.

## Modes

The tool is laid out as a few clear steps:

1. **Tones** — choose what you'll sing, via one of four modes (below).
2. **Settings** (collapsed by default) — sound, playback tempo, grading mode, singing time, microphone environment, and your vocal range. The defaults suit most people; the collapsed row shows a one-line summary.
3. **Play & sing** — **Play a tone** hears each tone on its own, one at a time; **Play a phrase** plays the whole sequence, then you sing it back.
4. **Results** — expected vs. sung for each tone, plus an overall summary once a full exercise is done.

### Tones: four modes

- **Manual** — pick tones one at a time with the dropdown and Add button (up to 9), drag to reorder, × to remove.
- **Scales** — pick a scale type (Major or Natural minor), a key (all 12, correctly spelled — see below), a starting octave, how many octaves to span, and a direction (Up / Down / Up and down). Generates the full scale automatically.
- **Arpeggios** — pick a chord type (major/minor triad, major/dominant/minor 7th), a key, octave, span, and direction. The chord tones (3 or 4 notes) are automatic — no need to count them yourself.
- **Sequences** — standard vocal-warmup patterns built on scale degrees: 3-note ascending run, 3-note turn, 4-note ascending run, thirds, and the 5-note turn. Pick a scale type, key, and starting octave; the pattern does the rest.

A **Clear** button lives in every mode, since the tones are one shared sequence regardless of which mode built them — no need to switch back to Manual just to reset.

### Correct key spelling

Every key is spelled correctly for its context — an F major scale reads F-G-A-**B♭**-C-D-E-F, not F-G-A-**A♯**-C-D-E-F. The two "black key" slots where major and minor conventionally disagree (C♯/D♭ and G♯/A♭) resolve to whichever spelling is standard for the scale type you've picked, automatically.

### Rounds

A generated exercise longer than a few notes is split into **rounds** of about 4 notes each, so you're never asked to sing 15 notes in one breath. Each round is practiced and graded on its own; a round indicator ("Round 2 of 4 · D3–D5") shows your place and the whole exercise's range. A **Next round →** button appears once a round is graded; once every round is done, a **Step up a semitone ↑** button appears too — a standard vocal-warmup move that repeats the same exercise transposed up one half-step, rather than making you re-pick a key each time.

### Up and down

**Play up and down** (next to the tone chips, for 2+ tones) mirrors whatever's selected on the fly — C-E-G plays as C-E-G-E-C, the peak note once, never repeated — without ever changing the chips themselves. It's the same mechanism whether the tones came from Manual, Scales, or Arpeggios (Sequences patterns are already complete shapes and don't use it).

## Getting started

The tool opens with no tones selected — build your phrase from scratch (add tones manually, or generate one via Scales, Arpeggios, or Sequences). The Play button stays disabled until at least one tone is chosen.

When a sung tone can't be graded, the feedback distinguishes two cases: **no sound detected** (nothing came through the mic) versus **tone too short** (sound was heard but not held long enough to read) — so you know whether to sing louder or hold longer.

## Profiles

A lightweight name-tag system — no login, no account, no server. A "Who's practicing?" switcher in the header lets more than one person share a device without mixing up settings. On first visit, a small welcome popup offers to save a nickname (skippable — you can always add one later via **+ New**). Everything is stored in your browser's local storage, tied to that nickname, on that device.

## Vocal range

In Settings, set your comfortable singing range — either by picking notes directly, or with **🎤 Detect**: a short guided tool that asks you to sing your highest comfortable note, then your lowest, each held for at least half a second, and lets you double-check or adjust the result before saving.

The range is **advisory only** — it never blocks anything. If a generated exercise goes outside it, you'll see a short note (e.g. "This exercise goes up to F5, which is 4 semitones above your stated range") and can still practice it, or adjust your range.

Once a range is set, the Scales/Arpeggios/Sequences panes show a **"Suggested for your range"** list — the top 3 keys ranked by how many of their notes actually fit your range, e.g. "C major — 8/8" — and picking a key also pre-fills the best-fitting octave. Both are just suggestions; every key and octave stays fully selectable.

## Feedback for beginners

- While singing, the **meter** is the live indicator — no text to read mid-note, just watch the needle. It glows and widens when you're on pitch, and pegs to the edge with a label (e.g. "≪ about two tones lower") if you're further off than it can show.
- After each tone, the **results card** shows the target, the note you actually sang (e.g. `D3 +12¢`), and a plain-English verdict — *"about one and a half tones lower"* rather than raw cents. No jargon required.
- Once a full exercise is done, a summary line gives the overall count — *"3/4 notes on pitch — see details below."*
- A collapsible **"New to this?"** panel explains notes, semitones, tones, sharp/flat, and cents in plain language.

An info panel beside the Play buttons narrates each step: an animated wave while a note plays, a **"Get ready"** cue with three calm dots counting down, a friendly **"Sing!"** prompt during your turn, and the summary at the end.

## Feedback

A **send feedback** link sits next to the author credit. It opens a small form (optional email + your message) that hands off to your own email app — nothing is sent anywhere else, and no address is stored in the page.

## Timing controls

**Singing time for each tone** (used in **On the clock** mode — it fades out in Follow me) sets how long you get to sing each tone:

- **Default** — adaptive: 3 seconds for a single tone, 2 seconds per tone when there are two or more.
- **1 sec / 2 sec / 3 sec** — a fixed time per tone for every tone in the sequence.

The dot timer adapts automatically to whatever the total window is: the final 5 seconds are shown as 10 fine dots (one every half-second), and everything before that as one dot per second, so long phrases stay readable.

**Playback tempo** (Default / Slow / Medium / High) sets how fast the app plays the reference tones to you — Slow is about one tone per second, up to High at three or four. It affects **playback only**; your singing time is governed entirely by the setting below, in On the clock mode.

## How singing is graded

Two ways to grade a sung phrase:

- **On the clock** — the classic mode. Each tone is expected during its highlighted slot on a fixed timer (the "Singing time for each tone" setting). Predictable and good for strict practice.
- **Follow me** — sing the phrase at your own pace and the app follows you. It records the whole take, finds the tones you actually *held* (a tone must be held for at least **half a second** to count, so an accidental sweep through the right pitch doesn't score), and matches them in order to the expected sequence. Timing no longer matters — only which tones you held, and in what order.

In **Follow me** mode the "Singing time for each tone" selector becomes an overall time *budget* per tone rather than a strict slot, with a floor that always leaves room to hold every tone for a full second. If the app detects a different number of held tones than expected, it tells you (e.g. "detected 4 held tones of 5"), which usually means two tones were slurred together or one wobbled into two.

Follow me is heuristic and works best for clear, deliberate singing with a small gap between tones; very legato phrases or heavy vibrato can confuse the tone-splitting. It's aimed at beginners and amateur singers who want natural practice rather than clock discipline.

## Recording environment

**Quiet room** (default) uses your raw microphone signal, which reads pitch most accurately. **Noisy room** turns on the browser's noise suppression and automatic gain control — it reduces background noise while recording your voice, but can slightly affect pitch accuracy. Switching this re-acquires the microphone, since the setting is applied when the mic starts.

## Mobile notes

The app works on phones, with a few browser-imposed limits worth knowing:

- **The microphone requires https.** Opening `index.html` from local storage on a phone will not work — use the GitHub Pages URL. The app now says so explicitly if it detects an insecure context.
- **On iOS every browser is Safari underneath**, so Safari's rules apply everywhere. Audio only starts from a tap (the Play buttons handle this), and the physical silent switch can mute playback.
- **Backgrounding the app** stops a recording in progress; the app detects this and aborts cleanly rather than grading noise.
- Pitch detection is throttled to ~30Hz to keep CPU use reasonable on phones.

## Headphones and microphones

The single biggest thing you control about accuracy is what you plug in.

Wired is best. 3.5 mm or USB-C headphones or earbuds, with your phone or laptop's own microphone, is the most reliable setup. No codec, no profile switching, low latency, full bandwidth.

Avoid Bluetooth headsets. Classic Bluetooth cannot carry high-quality audio and microphone input at the same time — it uses one profile or the other. The moment any app opens the microphone, the headset drops from A2DP (stereo, full quality) to HFP (mono, call quality: 8 kHz narrowband or 16 kHz wideband). Two consequences here:

The reference tone you are trying to match becomes muffled and mono. Your matching gets worse, and the app records that as your error.
Quiet room stops meaning what it says. That setting turns off the browser's noise suppression and gain control, but a Bluetooth headset and the operating system apply their own speech-tuned processing underneath, which a web page cannot reach.

Using Bluetooth headphones "only for listening" does not avoid this — opening the microphone switches the whole device. On iOS it is not possible to play via A2DP while capturing via HFP at all.

Bluetooth LE Audio devices avoid the tradeoff, but support is uneven across phones and headsets, so it is not something to count on.

Turn off noise cancelling and any "gaming mode" on your headset. Aggressive noise gates cut the quiet tail of a long note, so a perfectly steady hold gets measured as a short one — which matters in the Hold it steady lesson, where duration is part of the criterion.

A close boom microphone can clip. Excellent signal-to-noise, but with automatic gain control off (Quiet room), a loud singer very close to the mic can distort the waveform. Back off a few centimetres if readings look erratic on loud notes.

The app makes a best-effort guess at a Bluetooth capture path and shows a single dismissible line when it sees one. Detection relies on the browser reporting the capture sample rate, which Safari often does not, so treat the absence of a warning as no information rather than an all-clear. The same guidance is in the app under Settings → Microphone → "Which headphones or mic should I use?".

What is not affected

Band-limited audio does not cause octave errors here. Pitch detection uses the McLeod Pitch Method, which recovers the period from harmonic spacing, so a telephone-band path that strips everything below 300 Hz still reads low notes correctly — verified down to E2 at full clarity in the test suite.

## Sound: tone vs. piano

The **pure tone** is generated with the Web Audio oscillator and works fully offline.

The **piano** uses real recorded samples, with a three-step fallback so it works in every situation:

1. **Local samples** — if `samples/piano/` is present in the repo, the piano plays from your own copy with no external dependency. Samples are fetched individually as notes are played, not loaded as one package.
2. **CDN** — if there are no local samples but you're online, it loads a piano via [smplr](https://github.com/danigb/smplr).
3. **Synth tone** — if neither is available (e.g. `index.html` opened alone, offline), it falls back to the built-in synthesized tone.

### Adding the local piano samples

The app expects **Salamander Grand Piano V3** MP3 samples, velocity layer 8, in `samples/piano/`:

```bash
npm install @audio-samples/piano-mp3-velocity8
# copy node_modules/@audio-samples/piano-mp3-velocity8/audio/*.mp3 into samples/piano/
```

Filenames follow the pattern `C4v8.mp3`, `D#4v8.mp3`, `A2v8.mp3` — note name, then the `v8` velocity suffix. Salamander is sampled in minor thirds (C, D#, F#, A of each octave), and the app pitch-shifts by at most one semitone to fill the gaps, which is inaudible in practice. Only 16 files are needed to cover the app's E2–C6 range.

These samples are third-party content — see [NOTICES.md](NOTICES.md).


## Run locally

Just open `index.html` in a browser — or, because microphones need a secure context in some browsers, serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a new repository and push these files:

   ```bash
   git init
   git add .
   git commit -m "Pitch trainer"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/pitch-trainer.git
   git push -u origin main
   ```

2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick **main** / **`/root`**, and save.
4. After a minute your tool is live at `https://YOUR-USERNAME.github.io/pitch-trainer/`.

GitHub Pages serves over HTTPS, which is required for microphone access — so the deployed version will always be able to request the mic.

## Notes and limits

- Pitch detection uses the **McLeod Pitch Method** (MPM), via a bundled, adapted copy of [pitchy](https://github.com/ianprime0509/pitchy) — a refinement of autocorrelation specifically designed to avoid octave errors and stay robust on real (non-pristine) audio, including a per-reading confidence ("clarity") score. See [NOTICES.md](NOTICES.md) for attribution.
- Follow me's tone-segmentation is heuristic — very legato phrases (no gap between notes) or heavy vibrato can occasionally merge or split a tone incorrectly.
- Works in any modern browser. Requires microphone permission.

## Third-party content

The piano samples in `samples/piano/` are **Salamander Grand Piano V3**, recorded by Alexander Holm and packaged as MP3 by darosh (Jan Forst), used under the MIT license. The pitch detector bundles **pitchy** (0BSD) and **fft.js** (MIT). None of this is covered by this project's own license — see [NOTICES.md](NOTICES.md) for the full notices and attribution.

## License

Free for non-commercial use. Reproduction of the app, in whole or in part, is allowed with attribution to the creator and source — see [LICENSE](LICENSE). Bundled third-party components (piano samples, pitchy, fft.js) remain under their own separate licenses — see [NOTICES.md](NOTICES.md).
