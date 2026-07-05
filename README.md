# Interaktibong Reviewer sa Filipino 5

A self-contained, offline-friendly **interactive reviewer for Grade 5 Filipino**, built from a
DepEd-style learning module. Everything lives in a single file: [`index.html`](index.html) —
no build step, no dependencies, no internet required.

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

- ✅ **Auto-graded quizzes** with instant feedback and short explanations
- 🎯 **"Balikan ang mali"** — retry only the questions you missed, drilling down until all are correct
- ✍️ **Self-check items** (essays, reflections) reveal a model answer to compare against
- 🌟 Progress tracking, best scores, and star rewards — all saved locally
- 📱 Kid-friendly, mobile-responsive Filipino UI

## Paalala (Notes)

- The original scanned module pages (`IMG_*.jpg`) are **not** included in this repository. The
  "Tingnan ang orihinal na pahina" links therefore work only where those scans are present locally.
- The scans contain no printed answer key; the correct answers were derived from the module content.
  A few interpretation-based items are marked in the data (`flag:true`) for a teacher to confirm.
