# Mindful Ones — Roadmap and Vision

Frequency Studio is only the foundation. The full platform will include:

- Interactive human anatomy and wellness information (a more detailed body map)
- Chakra and spiritual practice libraries (traditional meanings kept distinct
  from modern additions)
- A scientific research and evidence library (specific citations per claim)
- Western and Vedic astrology (natal charts, transits, moon phases)
- Human Design BodyGraph calculations (Type, Strategy, Authority, Profile,
  centers, gates, channels)
- Meditation, breathing, and sound experiences
- Journaling, moon phases, and dream exploration
- A personal wellness garden / sanctuary dashboard

Astrology and Human Design already have their places designed into the website;
their calculations are implemented in a later phase.

Structure (Phase 2, decided 2026-11-09): move from the single long scrolling
page to page-style views — each section opens like its own page inside the same
self-contained file, with the Sanctuary as home. Triggered by first-visitor
feedback and the owner's own preference (the same pattern as her Phasmophobia
Field Guide). Design decision to settle when building: behavior for a tone
that is playing while the visitor switches views, consistent with the site's
sound-safety rules.

Phase 2 progress (2026-11-15): the page-style structure shipped (V9; the
playing tone keeps playing across views, with a mini player bar — the
owner's choice) and was owner-verified. The Earth view with the live
Schumann chart shipped (V11). The Human Design BodyGraph calculator shipped
(V12), was accuracy-fixed (V13), and is verified against Swiss Ephemeris —
see the testing record. The owner chose BodyGraph before Astrology
(2026-11-15): its answers come from a bounded set that is easier to narrow
down and verify. Astrology calculations (Western and Vedic) remain the next
major piece, on the owner's timing.

Phase 2 completion (2026-11-15): the Astrology calculator shipped (V16) —
Western (Placidus chart wheel, placements, major aspects) and Vedic
(Lahiri sidereal positions, nakshatras, Vimshottari dashas) — and was
verified against Swiss Ephemeris and the owner's own reference chart; see
the testing record. A Feedback view (V15) also shipped, relaying visitor
messages to the owner's inbox via FormSubmit; it activates with the
owner's one-time test message. All eight areas of the site are now open.
From the vision list, transits and moon phases remain future ideas, not
yet scheduled.

Follow-on (2026-11-15): at the owner's word, Transits and Moon phases —
the two remaining items from the vision list's astrology line — shipped
inside the Astrology view (V18), were checked against Swiss Ephemeris
fixtures with disclosed residuals, and were verified by the owner the
same evening (V19); see the testing record. The Earth view's owner
verification was recorded the same evening (V18). Still ahead, in the
owner's chosen order: the comprehensive frequency reference, then the
biofield-scan question.

Principles that do not change:

- Free access. No required account, no subscription, no advertising.
- Science and spirituality side by side, clearly labeled.
- No unsupported medical healing claims. Education, relaxation, and spiritual
  exploration only.
- Personal data stays private/local where possible.
- Knowledge should be accessible. Wellness should not depend on wealth.

Future hosting goals (discuss before changing anything): a public website of
its own, and an installable, offline-capable PWA.

Ideas added 2026-11-13 (owner; phase to be decided — Phase 2 or later):

- A comprehensive frequency reference: scientific information about
  frequencies across the whole body, our surroundings and environment, and
  the Earth itself (for example brainwave bands and the Schumann resonance),
  all labeled with the site's evidence levels — measured science, still being
  studied, and tradition kept clearly separate.
- A live Schumann resonance chart on the site — the continuously updating
  spectrogram published by the Tomsk State University Space Observing System
  (the feed behind most live Schumann charts), shown as an updating image or
  a clearly credited link, labeled as live external scientific data. The
  core site must keep working if the feed is ever down. (Corrected
  2026-11-13: this is the feature the owner meant by "the scan that's
  constantly going.") **Built 2026-11-15 (V11): the Earth view embeds the
  live image from the station's current home, sos70.ru, with credit, a
  "Live external data" label, 10-minute refresh, and an honest
  feed-unavailable fallback. Confirmed live the same day; the owner's own
  verification is recorded separately in the testing record.**
- Separately, the owner asked whether a biometric / biofield scan could be
  added at all. Answer on record: possible in principle via embed or link,
  but only after identifying a specific tool and reviewing it against this
  project's principles — visitor data must stay private, no account
  required, and the core site must not depend on an outside service.
