# Interaktibong Reviewer (Grade 5)

A self-contained, offline-friendly **interactive reviewer** for Grade 5, built from DepEd-style
learning modules. Everything lives in a single file: [`index.html`](index.html) — no build step,
no dependencies, no internet required.

Pick a **subject** from the home screen, then a lesson. Currently:
- **Filipino 5** — 3 lessons (Kuwentong Kababalaghan, Metapora, Tekstong Impormatibo)
- **EPP · ICT** — 2 lessons (Digital Citizenship & Netiquette, Responsableng Paggamit ng Internet)
- **Math 5** — 5 lessons (12- & 24-Hour Clocks, World Time Zones, GMDAS / Order of Operations, Multiplying Fractions, Exploring Shapes)
- **Science 5** — 7 lessons (Simple Science Investigations, Scientific Units & Measurement, Classification of Plants, Classification of Animals, Microorganisms, Specialized Structures of Plants, Life Cycle of Plants)

> The Math and Science content is in **English**, matching their English-medium source modules
> (Philippine Grade 5 Math and Science are taught in English).

### Per-subject interface language

Each subject carries an optional `lang` field. With `lang:"en"` the whole interface for that
subject — lesson cards, activity tags, instructions, buttons, feedback, and the score screen —
renders in English; without it, the default Filipino strings are used. **Science 5** is set to
`en`; Filipino, EPP·ICT, and Math keep the Filipino interface. The strings live in the `STR`
table near the top of the app script, so flipping another subject is a one-line change.

## Paano gamitin (How to use)

- **Simplest:** double-click `index.html` to open it in any modern browser.
- **Under WAMP/Apache:** place the folder in `www/` and open `http://localhost/interative_quiz/`.

Student progress (best scores + completion) is saved automatically in the browser via
`localStorage` — no accounts, no server needed.

## Nilalaman (Content)

Three lessons (Aralin), each with a reading passage plus interactive practice:

| Aralin | Babasahin | Pagsasanay |
|--------|-----------|------------|
| **1 — Kuwentong Kababalaghan** | Kuwentong *"Ang Aswang ng San Andres"* | 10-item multiple choice · tugma-tugma (matching) · pagkakasunod-sunod · sariling-suri |
| **2 — Metapora / Pagwawangis** | Tulang *"Diwa ng Metapora o Pagwawangis"* | multiple choice · punan ang patlang · dalawang pinagtutulad · sariling-suri |
| **3 — Tekstong Impormatibo** | Resetang *"Tinolang Manok ni Ruthie"* | tama/mali (B/HB) · multiple choice · sariling-suri |

## Mga Tampok (Features)

- 📚 **Subject switcher** — one app, multiple subjects, each with its own lessons and progress
- ✅ **Auto-graded quizzes** with instant feedback and short explanations
- 🎯 **"Balikan ang mali"** — retry only the questions you missed, drilling down until all are correct
- ⏳ **Session answer-memory** — in-progress answers (and typed essays) are remembered until you submit
  or complete the activity, so leaving and coming back never loses your work
- ✍️ **Self-check items** (essays, reflections) reveal a model answer to compare against
- 🌟 Progress tracking, best scores, and star rewards — all saved locally
- 📱 Kid-friendly, mobile-responsive Filipino UI

## Paalala (Notes)

- The original scanned module pages (`IMG_*.jpg`) are **not** included in this repository, except for
  the Science scans under `img/science/`. The "Tingnan ang orihinal na pahina" links therefore work
  only where those scans are present locally.
- The scans contain no printed answer key; the correct answers were derived from the module content.
  A few interpretation-based items are marked in the data (`flag:true`) for a teacher to confirm.
- **Science coverage gap.** The supplied scans cover Chapter 2 (measurement, investigations),
  Chapter 4 Lesson 1 (plants), and Chapter 5 Lesson 2 (plant life cycle). They do **not** include
  Chapter 4 Lesson 2 (animals), Chapter 4 Lesson 3 (fungi and bacteria), or any pages on specialized
  plant structures. Aralin 4, 5, and 6 were therefore written from the standard MATATAG Grade 5
  Science competencies rather than from the scans, and carry no `orig` link. A teacher should check
  them against the actual module pages before use.
