# Third-party notices

This project bundles third-party content that is **not** covered by this
project's own [LICENSE](LICENSE). The components below retain their original
licenses and copyright.

---

## Piano samples — `samples/piano/*.mp3`

**Salamander Grand Piano V3** — a Yamaha C5 grand piano, recorded by
**Alexander Holm** and released free of charge in 2012.

The MP3 packaging of these samples is by **darosh (Jan Forst)**, from
<https://github.com/darosh/samples-piano-mp3>, distributed under the MIT
license reproduced verbatim below.

Only a single velocity layer (`v8`) is included here, covering the note range
used by this application.

```
MIT License

Copyright (c) 2019 Jan Forst

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

**Sources**

- Salamander Grand Piano V3 (original): <https://archive.org/details/SalamanderGrandPianoV3>
- MP3 packaging: <https://github.com/darosh/samples-piano-mp3>

---

## Pitch detection — `pitchy` (bundled, adapted)

The pitch-detection algorithm (McLeod Pitch Method) is from **pitchy** by
**Ian Johnson** (`ianprime0509`), <https://github.com/ianprime0509/pitchy>,
version 4.1.0. The source has been adapted from an ES module to a plain
script (the `export` keywords removed and the `fft.js` import replaced with
a direct reference — see the comment at the top of the adapted code in
`index.html` for the exact change), but is otherwise unmodified.

Distributed under the Zero-Clause BSD License, reproduced verbatim below.

```
BSD Zero Clause License

Permission to use, copy, modify, and/or distribute this software for any
purpose with or without fee is hereby granted.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH
REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY
AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT,
INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM
LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR
OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
PERFORMANCE OF THIS SOFTWARE.
```

**Source**: <https://github.com/ianprime0509/pitchy>

---

## FFT — `fft.js` (bundled)

`pitchy` depends on **fft.js** by **Fedor Indutny**,
<https://github.com/indutny/fft.js>, to compute the Fourier transform used
internally by the pitch detector. The pre-built distribution bundle is
included verbatim.

```
MIT License

Copyright (c) 2017 Fedor Indutny

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

**Source**: <https://github.com/indutny/fft.js>

---

## Fonts

**Inter** and **JetBrains Mono** are loaded at runtime from Google Fonts and
are not redistributed with this project. Both are licensed under the
SIL Open Font License.

---

## smplr (optional, loaded at runtime)

When no local piano samples are present, the application may load
[smplr](https://github.com/danigb/smplr) from a CDN to provide a piano sound.
It is not redistributed with this project.
