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
