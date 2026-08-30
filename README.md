# Vocal Pitch Trainer (VPT)

Train vocal pitch accuracy in the browser — guided lessons for beginners, or build your own
exercise once you know what you want to work on. No install, no account, no server: it's a single
HTML file that listens to your microphone and gives you real-time pitch feedback.

![Vocal Pitch Trainer — landing screen](screenshot.png)

**[Try it live →](#)** <!-- replace with your GitHub Pages / hosting URL -->

## What it does

- **Guided lessons** — a step-by-step path from basic pitch matching (higher/lower, find the
  note) up through holding a steady note and moving between notes, so a first-time visitor always
  has one obvious next thing to do.
- **Free Practice** — build your own exercise from hand-picked tones, or generate a scale,
  arpeggio, or sequence in the key, octave, and shape you choose.
- **Real-time pitch feedback** — a live meter shows how close you are to the target note as you
  sing, color-coded so you can tell "on pitch" from "close" from "off" at a glance.
- **Post-attempt analysis** — a stability trace for held notes (how steady you stayed) and a
  glide trajectory for pitch-slide exercises (the path you actually sang vs. the ideal one).
- **Vocal range setup** — sing your highest and lowest comfortable notes once, and exercises can
  stay inside a range that fits your voice.
- **Multiple sounds** — reference notes play back as a pure tone, piano, or guitar.
- **Multiple profiles** — separate progress, range, and stats for each person using the same
  device, with the option to delete a profile (with confirmation and a few seconds to undo).
- **Progress tracking** — a "My Progress" view surfaces patterns in your practice (like a
  tendency to sing flat or sharp) once you've sung enough notes for it to say something useful.
- **Built-in diagnostics** — a microphone check panel for troubleshooting audio input, plus a
  guided tutorial ("Finding Your Pitch") covering the basics for new users.
- **English and Ukrainian**, switchable at any time.

## Running it

This is a single self-contained `index.html` — there's no build step and no dependencies to
install.

- **Quickest:** open `index.html` directly in a modern browser to try the interface. Note that
  browsers restrict microphone access (`getUserMedia`) to **secure contexts** — pages served over
  HTTPS, or `http://localhost` — so opening the file directly (a `file://` URL) may let you
  browse the app but block the microphone in some browsers.
- **For full functionality locally**, serve the folder instead of opening the file directly, e.g.:
  ```bash
  python3 -m http.server 8000
  # then open http://localhost:8000 in your browser
  ```
- **To host it for others**, any static host works (GitHub Pages, Netlify, a plain web server) —
  just make sure it's served over HTTPS.

A working microphone is required for singing exercises. Wired headphones or earbuds are
recommended; your phone or laptop's own mic is fine alongside them. A Bluetooth headset's own
microphone *can* drop to call-quality audio once any app opens it for recording, but this isn't
universal — it depends on your device and OS, and doesn't apply to Bluetooth used for output only.
If it happens, sing into your phone or laptop's own mic (or a wired mic) while still listening
through your Bluetooth headphones.

## Browser support

Built and tested against current Chrome/Edge, Firefox, and Safari. Microphone permission
handling varies slightly by browser (Firefox and Safari, for example, don't support querying
permission state in advance the way Chrome does) — the app detects and messages around these
differences rather than assuming one browser's behavior.

## Tech

Plain HTML, CSS, and JavaScript — no framework, no build tooling, no backend. Progress and
settings are stored locally in the browser (`localStorage`); nothing is uploaded anywhere. Piano
and guitar playback use bundled/CDN sample instruments where available, with a synthesized
fallback so sound options still work offline.

## License

<!-- Add a license (e.g. MIT) and update this section — none is currently declared. -->

## Author

N. Scherbak
