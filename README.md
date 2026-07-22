# Interaktibong Reviewer (Grade 5)

A self-contained, offline-friendly **interactive reviewer** for Grade 5, built from DepEd-style
learning modules. Everything lives in a single file: [`index.html`](index.html) — no build step,
no dependencies, no internet required.

Pick a **subject** from the home screen, then a lesson. Currently:
- **Filipino 5** — 3 lessons (Kuwentong Kababalaghan, Metapora, Tekstong Impormatibo)
- **EPP · ICT** — 2 lessons (Digital Citizenship & Netiquette, Responsableng Paggamit ng Internet)
- **Math 5** — 5 lessons (12- & 24-Hour Clocks, World Time Zones, GMDAS / Order of Operations, Multiplying Fractions, Exploring Shapes)

> The Math content is in **English**, matching its English-medium source module (Philippine Grade 5
> Math is taught in English). The app's navigation labels stay in Filipino.

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

- The original scanned module pages (`IMG_*.jpg`) are **not** included in this repository. The
  "Tingnan ang orihinal na pahina" links therefore work only where those scans are present locally.
- The scans contain no printed answer key; the correct answers were derived from the module content.
  A few interpretation-based items are marked in the data (`flag:true`) for a teacher to confirm.
