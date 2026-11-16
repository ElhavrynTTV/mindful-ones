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

Scope at that check: the Earth view's own owner verification had not been
separately recorded yet.

Owner verification (user-verified, reported 2026-11-15, on the owner's
laptop in Chrome on the live Pages site; owner's screenshots show the
chart rendering with the dates 14, 15 and 16 November 2026 along its top,
the "Live external data" badge, the source credit and link, the
how-to-read section and the labeled tradition section):

- Owner's verdict: "it looks okay."
- The owner noted the chart appears almost still — correct behavior for a
  three-day spectrogram: it visibly changes over hours, not seconds,
  which the owner already knew about this chart.

With the owner's verification recorded, the Testing Status note for the
Earth view was flipped from "Pending verification" to "Verified" (V18,
text-only).

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

## Phase 2 Astrology calculator (V16) — verification, 2026-11-15

V16 filled in the Astrology view with a full natal-chart calculator: one
birth form (date, time, timezone; birthplace coordinates via an
OpenStreetMap place-name lookup — only the place name is sent — or manual
entry) producing a Western chart (SVG wheel, Placidus houses, placements,
major aspects) and a Vedic chart (Lahiri sidereal positions, nakshatras
and padas, whole-sign houses, Vimshottari dashas) — all calculated in the
visitor's browser.

Reference computation (2026-11-15): the owner's chart (2 February 1991,
06:55, Charleston WV, 38.3498 / −81.6326) was computed independently with
Swiss Ephemeris 2.10. That reference also matches the owner's own chart
list from her astrology app (kept since 2026-11-07) almost exactly —
Rising Aquarius 0°16′ against her listed 0°17′, Saturn Capricorn 29°30′
exact — and it settled an open choice: the Lilith her tradition uses is
the MEAN lunar apogee (Sagittarius 20°50′, exactly her handwritten
value), not the true/osculating apogee.

Live-site run (checked on the live Pages site, 2026-11-15, same birth
data, manual coordinates):

- Every sign, Placidus house, nakshatra, pada and retrograde mark matched
  the Swiss reference, in both the Western and Vedic panels.
- Most positions matched within 1–2 arcminutes (Moon 25°28′ Virgo,
  Ascendant 0°16′ Aquarius, North Node 27°58′ Capricorn exact to the
  minute). Known residuals: Jupiter ~5′, Lilith ~6′, Pluto ~8′ (0.13° —
  a known limit of the compact fixed-element Pluto formula). None of the
  residuals changes any sign, house or nakshatra in this chart.
- Vimshottari dashas: all nine mahadasha boundaries within one day of the
  reference (Rahu 2011-10-23 → 2029-10-22 on the site; current antardasha
  Rahu/Sun to 2027-04-05). The site states its 365.25-day-year
  convention.
- Degraded modes behave honestly: with no birth time or no coordinates,
  the Ascendant, houses and Lagna are hidden rather than guessed, and
  the Moon sign is flagged as able to shift.

With the owner's approval, the Testing Status note for the calculator was
flipped from "Pending verification" to "Verified" (V17, text-only; all
seven script blocks verified byte-for-byte identical).

## Phase 2 follow-on: Transits + Moon phases (V18) — built 2026-11-15

V18 added, inside the Astrology view, a "Sky right now" card driven by a
pick-a-moment control: a Moon phases section (phase name, illumination,
Moon age, tropical and sidereal Moon signs, a drawn moon disc, the next
New and Full Moons, and the four quarter events of the current lunation)
and a Transits section (the moment's sky, and every transit aspect within
3° of the visitor's natal points, tightest first). All computed in the
browser; a Testing Status note marks the addition "Pending verification."

Phase-name convention (chosen for coherence with the listed event times):
the four quarter names apply for about ±12° of elongation around the exact
quarter moment; crescent and gibbous names fill the spans between. So the
evening of 2026-11-15 reads Waxing Crescent (elongation 74.03°,
illumination 36.2%) with the First Quarter event listed at its exact
moment, 2026-11-17 11:47 UTC.

Builder fixture results against Swiss Ephemeris 2.10 (run at build time):
the Moon fixture reproduced (Sun exact, Moon within 1′, illumination
exact, ayanamsa within 0.001°); quarter events within 1–2 minutes except
the two Full Moons (2026-11-24: 15:02 vs 14:53 UTC; 2026-12-24: 01:34 vs
01:28 UTC — the compact lunar series' limit near full). Transit
positions: 10 of 12 within 0.02°; Lilith within 0.116° (the known
mean-apogee limit); transit Pluto within 0.38° at 2026 dates — the
two-body Pluto orbit drifts against Swiss over decades (its residual was
+0.13° at 1991, −0.38° at 2026) and no compact published correction
exists; an empirical fit was considered and rejected as indefensible.
Consequence: 15 of the 16 fixture transit aspects reproduce with orbs
within ~0.11°; the Pluto–Mars trine's orb reads 0.45° instead of 0.07°,
and a borderline Pluto–Ascendant conjunction (2.63°) can appear that
exact positions place just outside the 3° limit. These residuals are
recorded here rather than smoothed over; the owner's verification is
still to come.
