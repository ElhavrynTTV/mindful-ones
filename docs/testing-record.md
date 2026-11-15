# Mindful Ones — Testing Record

Only verified results are marked Passed. Implemented-but-untested stays Pending.
User-performed tests are credited as user-verified.

## Laptop functional checks (user-performed, 2026-11-08)

7/7 passed: 528 Hz audible/steady; volume slider works and silences at 0%;
432 Hz noticeably lower than 528; 1-minute timer stopped playback automatically;
binaural plays through both headphones; left/right tones sound slightly different
per ear; Stop silences both channels. V2 round: 9/9 checks passed (adds gentle
fades and the conservative 20% starting volume).

## Frequency preset sweep — preliminary acoustic verification (2026-11-08)

Method: phyphox Audio Spectrum analyzer on the user's phone, measurements
recorded by hand. Analyzer resolution approximately 2.93 Hz.
These are preliminary acoustic measurements, not laboratory-grade certifications.

| Selected | Measured | Difference |
|---|---|---|
| 174 Hz | 172.85 Hz | 1.15 Hz |
| 285 Hz | 284.18 Hz | 0.82 Hz |
| 396 Hz | 395.51 Hz | 0.49 Hz |
| 417 Hz | 416.02 Hz | 0.98 Hz |
| 432 Hz | 430.66 Hz | 1.34 Hz |
| 528 Hz | 527.34 Hz | 0.66 Hz |
| 639 Hz | 638.67 Hz | 0.33 Hz |
| 741 Hz | 741.21 Hz | 0.21 Hz |
| 852 Hz | 852.54 Hz | 0.54 Hz |
| 963 Hz | 963.87 Hz | 0.87 Hz |

Result: 10/10 presets consistent with targets within approximately half an
analyzer frequency bin. Largest absolute difference: 1.34 Hz.

## Android Chrome background tests (user-verified, V3, 2026-11-08)

3/3 passed: pressing Home — audio continued through headphones; locking the
phone — audio continued with screen locked; timer expiration — after the
1-minute session expired, playback stopped and remained stopped on return.

Interpretation (careful wording): this strongly suggests the earlier background
silence inside the Muse app was associated with Muse's embedded viewing
environment rather than an inherent limitation of the sound generator; the exact
cause has not been technically proven.

## Custom frequency testing (user-verified, 2026-11-08)

Custom entry works. An above-range value safely clamped to the Studio maximum
of 2000 Hz and displayed cleanly ("2000 Hz · custom frequency"; diagnostics at
the time read Audio engine: running · Page: visible · Session: stopped).

Corrected phyphox measurements (analyzer at 16384 samples, ~2.93 Hz resolution,
same settings as the preset sweep):

| Selected | Measured | Difference |
|---|---|---|
| 250 Hz | 249.02 Hz | 0.98 Hz |
| 500 Hz | 500.98 Hz | 0.98 Hz |
| 777 Hz | 776.37 Hz | 0.63 Hz |

All three within about 1 Hz of target, consistent with the preset sweep.
Preliminary acoustic measurements, not laboratory-grade certification.

Superseded attempt: an earlier round of the same three values (257.81 / 492.19 /
773.44 Hz) was discarded after the tester found the analyzer's sample-size
setting was wrong; she corrected the setting, re-measured, and crossed the old
values out. Kept here only as a labeled superseded attempt.

## Error handling (user-verified, 2026-11-08)

Passed: rapid Play/Stop about ten times and preset switching produced no
stacked tones and no volume jumps; nothing played when it should not have.
Note: the headphone-disconnect sub-test is not directly equivalent on the
tester's setup (headphones run through an external audio card), so that
sub-item is recorded as setup-different — neither passed nor failed.

## Local copy check (user-verified, 2026-11-08)

The exported `index.html` was opened from the tester's own computer
(D:\Download\mindful-ones-app) in Chrome; all checks passed as before. The
site runs correctly as a local file with no hosting involved.

## Electronic binaural channel verification (passed, 2026-11-08)

Method: saved stereo WAV recorded through Windows WASAPI using the
Elgato-routed website audio, analyzed independently by channel.

In both the 10–15-second and 12–17-second sections:

| Channel | Measured |
|---|---|
| Left | 523.000 Hz |
| Right | 533.000 Hz |

A 10.000 Hz separation centered on 528.000 Hz. Opposite-tone content was
negligible in the analyzed sections. This verifies the captured digital
channel frequencies and separation for this setup.

Evidence file: `mindful-ones-binaural-528-10.wav` — stereo, 48 kHz, 16-bit
PCM, 21.05 seconds (kept by the tester; identified here by name and spec).

## Still Pending

None. With the binaural verification above, every Phase 1 test item has been
verified: laptop functional checks, the ten-preset phyphox sweep, custom
frequency testing, Android background behavior, error handling, the local-copy
check, and electronic binaural channel verification. **Phase 1 testing is
complete.**

## GitHub Pages host confirmation — 2026-11-08

After the repository went public (owner's decision) and the GPL-3.0 license was
added, the site was published on GitHub Pages at
https://elhavrynttv.github.io/mindful-ones/ — the same `index.html` from this
repository. A later navigation-only update (V8: mobile hamburger menu;
audio code verified byte-for-byte identical to V7) was confirmed live on Pages
from the tester's phone screenshots.

Host-confirmation checks on the Pages site, on the tester's Android phone
(user-verified, reported 2026-11-08):

- **Audio plays** on the Pages host.
- **Timer** stops playback as expected.
- **Lock screen** — playback continues with the phone locked.
- **Concurrent audio** — the frequencies remain listenable even while other
  audio is playing in the background (observed by the tester).
- **Menu navigation** — opening the hamburger menu and tapping "Frequency
  Studio" scrolls to the section and closes the menu.

These are confirmations that the new host serves the identical, already-tested
file correctly — not a repeat of the Phase 1 test list.

## Phase 2 structure (V9) — owner verification, 2026-11-15

V9 restructured the site into page-style views (Sanctuary home; each section
opens as its own view) and added a mini player bar, under the owner's chosen
rule: a playing tone keeps playing across view switches, with the bar visible
on every view. The original audio/playback script was verified byte-for-byte
identical to V8 before release; all view and mini-bar logic lives in a
separate script, and the bar's Stop button activates the Studio's existing
Stop control.

Owner verification (user-verified, reported 2026-11-15, on the owner's
laptop in Chrome on the live Pages site):

- **View switching** — the Chakras view opened as its own page (#chakras),
  with the Chakras nav item highlighted.
- **Tone keeps playing across views** — a 528 Hz tone started in the Studio
  was still playing after switching to the Chakras view.
- **Mini player bar** — visible at the bottom of the Chakras view showing
  "Now playing: a pure 528 Hz sine tone — the Transformation tone", a live
  countdown ("0:48 left" in the owner's screenshot), and a Stop button.
- Owner's verdict on the check: "it worked fine."

Scope: verified on the owner's laptop Chrome setup. The screenshot captures
the bar mid-countdown; the timer-expiry bar-hide was part of the owner's
check as reported, and phone verification of the new structure has not been
separately recorded.

## Phase 2 Earth view (V11) — live confirmation, 2026-11-15

V11 added an Earth view embedding the live Schumann resonance spectrogram
from the Tomsk State University Space Observing System (sos70.ru), credited
and labeled "Live external data", refreshing every 10 minutes, with an
honest fallback message if the feed is unreachable (the feed's old address
has been frozen since 2025-09-01 and is not used).

Live confirmation (checked on the live Pages site, 2026-11-15):

- **Earth in navigation** — present on desktop nav and mobile menu.
- **Chart rendering** — the spectrogram loaded and displayed, showing the
  dates 14, 15 and 16 November 2026 along its top (current data, not the
  frozen legacy feed), with the source credit and "View the chart at the
  source" link present.
- **Fallback not triggered** — the feed was up at check time, so no
  fallback message was shown.

Scope: the Earth view's own owner verification has not been separately
recorded yet; the Testing Status note for this addition remains "Pending
verification" until it is.

## Phase 2 BodyGraph calculator (V12–V13) — verification, 2026-11-15

V12 added a full Human Design BodyGraph calculator to the BodyGraph view:
birth date, time, place and timezone in; Type, Strategy, Authority, Profile,
Definition, Incarnation Cross, defined channels and centers, an SVG body
graph, and all 26 Personality/Design activations out — calculated entirely
in the visitor's browser (no data leaves the device).

Owner's live run (user-performed, 2026-11-15, owner's laptop Chrome on the
live Pages site; birth data: 2 February 1991, 06:55, Charleston WV,
America/New_York): Generator; Sacral authority; Profile 6/3; Single
definition; Left Angle Cross (gates 19·33·1·2); one defined channel (2–14);
defined centers G and Sacral. The Design moment resolved to 7 November
1990, 86.7 days before birth.

Independent cross-check (2026-11-15): the same birth data was computed with
Swiss Ephemeris 2.10 (apparent longitudes, true node) — the library most
Human Design software uses — and compared activation by activation.

- 20 of 26 activations matched the site to the exact gate and line, and the
  derived chart (Type, Authority, Profile, Definition, channel, centers,
  Cross) was identical under both ephemerides.
- 6 differed, all in Neptune (~3–4°) and the lunar Nodes (~1–2°). In this
  chart none of those gates completes a channel in either version, so no
  derived result changed; the errors were still treated as real defects.
- Root causes: Neptune's epoch mean anomaly had been transcribed as
  256.2285 instead of the published 260.2471; the Node's main correction
  term had been applied to the wrong argument. V13 corrected the element
  and replaced the Node formula (standard mean-node polynomial plus a
  22-term periodic series).
- Fix validation: at five fixture moments spanning 1980–2015, the fixed
  code matches Swiss Ephemeris within 0.009° (Neptune) and 0.022° (Node);
  across 600 random moments from 1800–2100 the worst error was 0.040°.
- Live re-check (2026-11-15): the same chart rebuilt on the live Pages
  site (V13) reproduced all 26 Swiss Ephemeris activations exactly, with
  derived results unchanged.

With the owner's approval, the Testing Status note for the calculator was
flipped from "Pending verification" to "Verified" (V14, text-only; all
script blocks verified byte-for-byte identical, including the calculator's
own).
