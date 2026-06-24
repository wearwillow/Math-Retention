# 📐 MathDeck — G7 to G10 Retention App

A spaced repetition study app for DepEd Math modules, Grade 7–10. Built as a single HTML file — no installation, no internet required, runs in any browser.

## Features

- **Spaced repetition (SM-2)** — topics resurface at the right time based on how well you know them. Rate each question Easy / OK / Hard and the app auto-schedules the next review.
- **53 modules** from DepEd self-learning modules (Q1–Q4, G7–G10)
- **Concept summary** shown before each topic's questions
- **60-second timer** per question
- **Mastery tracker** — each topic has a 0–100% score that goes up/down based on your answers
- **Mistake journal** — every wrong answer is saved with what you answered vs the correct answer
- **Daily streak tracker**
- **Progress dashboard** — see mastery per topic, filter by grade
- **Export / Import save** — download your progress as a `.json` file and load it back anytime (useful if you clear browser data or switch devices)
- **Reset progress** — start fresh anytime

## How to Use

1. Download `math_retention_app.html`
2. Open it in any browser (Chrome, Edge, Firefox)
3. Hit **Start Session** — it will show you topics due for review
4. Answer questions, rate difficulty, and let the app schedule your next review
5. **Export your save** regularly from the sidebar so you don't lose progress

## Save System

Progress is stored in your browser's `localStorage` automatically after every session.

To back it up or transfer to another device:
- Sidebar → **Export Save** → downloads `mathdeck-save-YYYY-MM-DD.json`
- On the other device → Sidebar → **Import Save** → select the `.json` file

## Topics Covered

| Grade | Strands |
|-------|---------|
| G7 | Sets, Integers, Rational Numbers, Real Numbers, Scientific Notation, Measurements, Algebra, Exponents, Equations & Inequalities |
| G8 | Factoring, Coordinate System, Linear Equations, Systems of Equations, Functions, Logic & Reasoning |
| G9 | Quadratic Equations, Quadratic Functions, Quadratic Inequalities, Variations, Radicals, Exponents |
| G10 | Sequences (Arithmetic & Geometric), Polynomials, Rational Expressions, Circles, Distance Formula, Equation of a Circle |

## Algorithm

Uses the **SM-2 spaced repetition algorithm**:
- Each topic starts with `interval = 1 day`, `ease_factor = 2.5`
- **Easy** → interval multiplied by ease factor, ease factor increases
- **OK** → interval multiplied by ease factor, ease factor unchanged
- **Hard** → interval resets to 1 day, ease factor decreases (min 1.3)
- Max interval capped at 30 days
- Mastery score adjusts +12 for correct, −8 for wrong answers

## Tech Stack

Pure HTML + CSS + vanilla JS. Zero dependencies. Zero build step. One file.

---

Based on DepEd Region XI Official Self-Learning Modules, First Edition 2020/2021.
