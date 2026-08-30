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
Vocal Pitch Trainer License

Copyright (c) 2026 Nikolai Scherbak

This license applies to the original source code and documentation of this
project (the "Software"), written by Nikolai Scherbak. It does NOT cover
bundled third-party components — see the "NOTE ON SCOPE" section below.

Permission is granted, free of charge, to use, copy, modify, and redistribute
the Software, in whole or in part, subject to the following conditions:

1. NON-COMMERCIAL USE ONLY. The Software, and any copy, modification, or
   derivative of it, may be used only for non-commercial purposes. Any use
   intended for or directed toward commercial advantage or monetary
   compensation is not permitted without prior written permission from the
   copyright holder.

2. ATTRIBUTION REQUIRED. Any reproduction or redistribution of the Software,
   in whole or in part, must give clear attribution to the original creator
   (Nikolai Scherbak) and the source of the project. This applies whether the
   Software is shared unmodified, modified, or incorporated into a larger
   work.

3. NO WARRANTY. THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY
   KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
   MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN
   NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
   LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
   FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
   DEALINGS IN THE SOFTWARE.

For commercial licensing inquiries, contact the copyright holder directly.

---

NOTE ON SCOPE: This license covers only the original source code and
documentation of this project. It does NOT cover:

- The third-party piano samples in samples/piano/
- The bundled pitchy (pitch detection) library
- The bundled fft.js library

These remain under their own original licenses — see NOTICES.md for full
attribution and license text for each.


## Author

N. Scherbak
