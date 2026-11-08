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

## Still Pending

- Custom frequency verification (e.g. 250, 500, 777 Hz) and invalid-input handling
- Electronic binaural channel verification (measured left/right output frequencies)
- Error handling: rapid Play/Stop, preset switching mid-play, Bluetooth
  interruptions, audio errors, timer recovery
