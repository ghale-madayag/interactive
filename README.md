# Interaktibong Reviewer (Grade 5)

A self-contained, offline-friendly **interactive reviewer** for Grade 5, built from DepEd-style
learning modules. Everything lives in a single file: [`index.html`](index.html) — no build step,
no dependencies, no internet required.

Pick a **subject** from the home screen, then a lesson. Currently:
- **Filipino 5** — 5 lessons (Kuwentong Kababalaghan, Metapora, Tekstong Impormatibo, Pang-abay na Panang-ayon at Pagsalungat, Elemento ng Maikling Kuwento)
- **EPP · ICT** — 2 lessons (Digital Citizenship & Netiquette, Responsableng Paggamit ng Internet)
- **Math 5** — 5 lessons (12- & 24-Hour Clocks, World Time Zones, GMDAS / Order of Operations, Multiplying Fractions, Exploring Shapes)
- **Science 5** — 7 lessons (Simple Science Investigations, Scientific Units & Measurement, Classification of Plants, Classification of Animals, Microorganisms, Specialized Structures of Plants, Life Cycle of Plants)
- **Araling Panlipunan 5** — 3 lessons (Sinaunang Paniniwala at Kaugalian, Pagdating at Paglaganap ng Islam, Ugnayang Asyano at Impluwensiya)

> The Math and Science content is in **English**, matching their English-medium source modules
> (Philippine Grade 5 Math and Science are taught in English).

### Per-subject interface language

Each subject carries an optional `lang` field. With `lang:"en"` the whole interface for that
subject — lesson cards, activity tags, instructions, buttons, feedback, and the score screen —
renders in English; without it, the default Filipino strings are used. **Math 5** and **Science 5**
are set to `en`; Filipino 5, EPP·ICT and Araling Panlipunan 5 keep the Filipino interface. The strings live in the `STR`
table near the top of the app script, so flipping another subject is a one-line change.

## Paano gamitin (How to use)

- **Simplest:** double-click `index.html` to open it in any modern browser.
- **Under WAMP/Apache:** place the folder in `www/` and open `http://localhost/interative_quiz/`.

Student progress (best scores + completion) is saved automatically in the browser via
`localStorage` — no accounts, no server needed.

## Nilalaman (Content)

The Filipino lessons, each with a reading passage plus interactive practice:

| Aralin | Babasahin | Pagsasanay |
|--------|-----------|------------|
| **1 — Kuwentong Kababalaghan** | Kuwentong *"Ang Aswang ng San Andres"* | pagkilala (identification) × 3 · sariling-suri |
| **2 — Metapora / Pagwawangis** | Tulang *"Diwa ng Metapora o Pagwawangis"* | multiple choice · punan ang patlang · dalawang pinagtutulad · sariling-suri |
| **3 — Tekstong Impormatibo** | Resetang *"Tinolang Manok ni Ruthie"* | tama/mali (B/HB) · multiple choice · sariling-suri |
| **4 — Pang-abay na Panang-ayon at Pagsalungat** | Palaging Tandaan (Aralin 6, p. 48) | panang-ayon/pagsalungat · multiple choice · tugma-tugma · punan ang patlang · sariling-suri |
| **5 — Elemento ng Maikling Kuwento** | Alamin (Aralin 1, pp. 5-8) | tugma-tugma · tama/mali · multiple choice · punan ang patlang · sariling-suri |

## Mga Tampok (Features)

- 📚 **Subject switcher** — one app, multiple subjects, each with its own lessons and progress
- ✅ **Identification quizzes** — every quiz asks the learner to type the term; answers are matched
  ignoring case, spacing, accents and trailing punctuation, and each item may accept alternates
- 🎯 **"Balikan ang mali"** — retry only the questions you missed, drilling down until all are correct
- ⏳ **Session answer-memory** — in-progress answers (and typed essays) are remembered until you submit
  or complete the activity, so leaving and coming back never loses your work
- ✍️ **Self-check items** (essays, reflections) reveal a model answer to compare against
- 🌟 Progress tracking, best scores, and star rewards — all saved locally
- 🌐 **Per-subject interface language** — Filipino subjects render in Filipino, Math and Science in English
- 📱 Kid-friendly, mobile-responsive UI

## Disenyo (Design)

**Every screen** follows the Claude Design project *"Interactive app redesign for students"*
(`Homepage.dc.html`, `Reading Page.dc.html`): a purple gradient hero, Baloo 2 + Nunito typography,
and rounded white cards on a lavender page.

Each screen opens with the same full-bleed hero — brand on top, breadcrumb chips below — built by
`heroBar()`. Subject, lesson, quiz, and result screens then lay out a centred column of cards.

- The canvas-only constructs in those files (`<x-dc>`, `<helmet>`, `<sc-if>`, `{{ }}` bindings,
  `style-hover`, the `DCLogic` script) are design-runtime syntax from `support.js`. They are
  translated here into ordinary CSS classes and app code.
- The home and reading screens manage their own full-bleed layout via `body.home-theme` /
  `body.read-theme`; every other screen uses the shared `#app` column and `.pg-hero`.
- Fonts load from Google Fonts. Offline, the pages fall back to the system sans stack and stay
  fully usable.
- A reading page gets the step-by-step layout — sticky progress bar, numbered step cards, per-step
  "I've read this step" buttons, and a completion celebration — when its activity defines `steps`.
  Science Aralin 1 carries hand-authored `steps`; 17 other readings label ranges of their own body
  paragraphs with `sections` and the cards are derived from those, so no module text is duplicated.
  The Filipino story, poem and recipe keep their flowing layout. Per-step progress is remembered
  like any other in-progress answer.

## Paalala (Notes)

- The original scanned module pages (`IMG_*.jpg`) are **not** included in this repository, except for
  the Science scans under `img/science/`, the Filipino scans under `img/filipino/`, and the
  Araling Panlipunan scans under `img/araling_panlipunan/`. The
  "Tingnan ang orihinal na pahina" links therefore work only where those scans are present locally.
- The scans contain no printed answer key; the correct answers were derived from the module content.
  A few interpretation-based items are marked in the data (`flag:true`) for a teacher to confirm.
- **Araling Panlipunan source.** This subject was built from a two-page *"AP — Pointers to Review
  for Term 1 Exam"* sheet rather than from module pages, so it is revision material: the reviewer's
  own answers are preserved, and the three lessons follow its own grouping (sinaunang paniniwala,
  Islam, ugnayang Asyano). A teacher should check it against the full module before use.
- **Science coverage gap.** The supplied scans cover Chapter 2 (measurement, investigations),
  Chapter 4 Lesson 1 (plants), and Chapter 5 Lesson 2 (plant life cycle). They do **not** include
  Chapter 4 Lesson 2 (animals), Chapter 4 Lesson 3 (fungi and bacteria), or any pages on specialized
  plant structures. Aralin 4, 5, and 6 were therefore written from the standard MATATAG Grade 5
  Science competencies rather than from the scans, and carry no `orig` link. A teacher should check
  them against the actual module pages before use.
