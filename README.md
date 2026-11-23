# GATE Pulse AI: Smart PYQ Analyzer and Pareto Prep Strategist

A single-page web app for GATE CSE aspirants. Upload previous year question (PYQ) PDFs and it finds which topics give the most marks for the least study (80/20), which questions repeat across years, and how to study each topic.

Everything runs in your browser. No server, no sign-up, and your PDFs are never uploaded.

## Features

- **Pareto 80/20 overview**: ROI ranking (`frequency x repeat multiplier / syllabus effort`), cumulative curve, subject donut, and a target-score slider that shows how many topics you need.
- **PDF parser**: multi-file drag and drop, per-file progress, question splitting (`Q1.`, `Q.1`, `Question 1`), MCQ/MSQ/NAT/Subjective tags, answer key extraction, and a warning for scanned PDFs.
- **Paste PYQ text**: import questions without a PDF.
- **Weightage matrix**: subject filter, chapter and topic drill-down, year badges, trend, and a year-by-subject heatmap.
- **Repeat radar**: groups questions that return in different years (numbers are ignored when comparing) and shows the typical exam twist.
- **Study strategy**: four buckets (practice-heavy, conceptual, quick win, skip if short on time) with notes and a PYQ checklist.
- **Progress and readiness**: stage per topic, solved counter, confidence, 14-day log, streak.
- **Question bank**: search, subject/topic/type filters, repeated-only toggle, detail modal.
- **Export**: Markdown study plan (copy or print) and CSV topic table (copy).
- Auto-saves to `localStorage`.

## Run locally

No build step. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

An internet connection is needed once per load for the CDN scripts (pdf.js, Chart.js, Google Fonts).

## Deploy on GitHub Pages

1. Create a new repository and push these files to the `main` branch.
2. In the repository, go to **Settings > Pages** and set **Source** to **GitHub Actions**.
3. Push any commit. The workflow in `.github/workflows/pages.yml` publishes the site at `https://<your-username>.github.io/<repo-name>/`.

## Tips for best results

- Put the exam year in each PDF file name (for example `GATE-2019.pdf`) so repeats can be matched across years.
- Use text-based PDFs. Scanned or image-only PDFs have no selectable text and need OCR first.

## Known limitations

- Topic mapping is keyword-based, so some questions land in "Unclassified".
- Question count is used as a stand-in for marks.
- The "Estimated score" is a rough guide (85 technical marks plus an assumed 11.5 aptitude marks), not a prediction.
- The built-in sample dataset is generated from template questions for demonstration. It is not official GATE paper text.
- No AI/Gemini mode yet; analysis is rule-based.

## Tech

Plain HTML, CSS and JavaScript with [pdf.js](https://mozilla.github.io/pdf.js/) 3.11.174 and [Chart.js](https://www.chartjs.org/) 4.4.1 from cdnjs.

## License

MIT. See `LICENSE`.
