# Mindful Ones — Healing Universe

A free wellness, science, and spirituality exploration platform.

**Founding principle: Knowledge should be accessible. Wellness should not depend on wealth.**

Mindful Ones is built so people can explore scientific knowledge and spiritual traditions
side by side — clearly labeled, honestly presented, and without being forced to choose
one or the other. It makes no unsupported medical healing claims.

## What's in Phase 1

- **Sanctuary** — a peaceful homepage with a feeling-check that suggests where to explore.
- **Frequency Studio** — a real sound generator (Web Audio): Solfeggio presets 174–963 Hz
  including 432 and 528, custom frequency input, sine/triangle waveforms, volume control,
  session timers, and true binaural beats (a different tone in each ear; headphones required).
- **Interactive Body Map** — seven starter regions with anatomy information, a wellness
  practice, and the traditional chakra association for each region.
- **Chakra Library** — the seven main chakras with traditional meanings, colors, practices,
  and play buttons for their associated tones. Frequency pairings are labeled as modern
  spiritual associations, not scientific fact.
- **Research & Evidence system** — claims are labeled *Supported*, *Still being studied*,
  or *Spiritual tradition*.
- **Sound Safety & Responsible Use** — hearing protection, conservative starting volume
  with fade-in/out, a plain-language medical disclaimer (education, relaxation, and
  spiritual exploration only), and accessibility guidance.
- **Astrology & Human Design** — sections designed into the architecture now; their
  calculations arrive in a later phase.

No required account. No subscription. No advertising.

## Run it locally

The current working build is a single self-contained page.

Option 1: just open `index.html` in a browser.

Option 2 (closer to how it behaves on a phone): serve the folder with any static server, e.g.

```sh
python3 -m http.server 8000
```

then open http://localhost:8000 in your browser or on your phone on the same network.

## Testing status (honest labels only)

User-performed checks that have **passed** are recorded in `docs/testing-record.md`
and in the Testing Status section of the site itself. As of November 8, 2026,
**Phase 1 testing is complete**: functional checks, the ten-preset phyphox sweep,
custom frequency testing (corrected readings within ~1 Hz), error handling,
Android background behavior, the local-copy check, and electronic binaural
channel verification (523.000 Hz left / 533.000 Hz right, measured from a WASAPI
recording) have all been verified. Preliminary phyphox acoustic measurements
are labeled preliminary, not laboratory-grade certification.

## Project layout

- `index.html` — the current working site (single-file build; a modular refactor
  into components is a future step, to be done carefully without breaking verified audio)
- `docs/` — testing record, research notes, and the roadmap
- `assets/` — images and media for the site (added as they are created)
- `future-features/` — design notes for astrology, Human Design BodyGraph,
  meditation/breathwork, journaling, moon phases, and the personal garden

## Checkpoints

The Muse artifact keeps restorable versions (V1 original baseline, V2 safety
version, V3 diagnostics, and later). This repository is the long-term home of the
source; Git history here serves the same protect-what-works purpose.

## License

License not yet chosen. Until the project owner decides on an open-source license
and this section is updated, all rights are reserved. Mindful Ones will remain free
for people to use; the license discussion is about ownership, attribution, and reuse
terms before the repository becomes public.
