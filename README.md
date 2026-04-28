# Reasoning_UPP
Reasoning Mastery UPSI &amp; Constable Examination Prep
# Reasoning Mastery — Chapter 1: Analogy Quiz

An interactive, beautifully-designed quiz website built for students preparing for the **Uttar Pradesh UPSI & Constable** examinations. This project covers **Chapter 1: Analogy** with 100 hand-curated questions sourced from the official Rakesh Yadav Readers Publication study material.

## 🎯 Project Goals

- Provide an engaging, distraction-free practice platform for reasoning aspirants
- Offer instant feedback and detailed solutions to maximize learning
- Deliver a modern, mobile-friendly experience that works offline (single-file static site)

## ✅ Currently Completed Features

| Feature | Status | Description |
|---------|--------|-------------|
| **Chapter Selection Screen** | ✅ | Clean home screen showing Chapter 1 (active) and upcoming chapters |
| **Interactive Quiz** | ✅ | All 100 Analogy questions with 4 multiple-choice options each |
| **Instant Feedback** | ✅ | Immediate visual confirmation (green/red) on answer selection |
| **Detailed Solutions** | ✅ | Every question includes a step-by-step explanation |
| **Progress Tracking** | ✅ | Animated gradient progress bar showing position in the quiz |
| **Live Score Display** | ✅ | Real-time score pill in the quiz header |
| **Final Results Screen** | ✅ | Animated circular accuracy meter, correct/wrong/skipped breakdown |
| **Performance Feedback** | ✅ | 4-tier personalized message system (Outstanding / Great / Good / Keep Practicing) |
| **Modern Gradient UI** | ✅ | Purple-pink gradient theme with glassmorphism card |
| **Smooth Animations** | ✅ | Fade-ins, bounce-ins, shakes, pulse effects on key interactions |
| **Keyboard Shortcuts** | ✅ | Press **1-4** to choose options, **Enter** for next |
| **Mobile Responsive** | ✅ | Optimized layout for phones, tablets, and desktops |
| **Quit Confirmation** | ✅ | Prevents accidental loss of progress |

## 🌐 Functional Entry URIs

This is a **single-page static website**. All functionality is contained within `index.html`.

| Path | Purpose |
|------|---------|
| `/` or `/index.html` | Main application — loads the start screen |

The app uses three internal "screens" managed via JavaScript (no URL routing):

1. **Start Screen** (`#screen-start`) — Chapter selection + Start button
2. **Quiz Screen** (`#screen-quiz`) — Active question + options + feedback
3. **Result Screen** (`#screen-result`) — Final score + performance summary

### User Flow Parameters

- **Click** any unlocked chapter card → highlights it as active selection
- **Click "Start Quiz"** → begins the 100-question quiz from Q1
- **Click any option (A/B/C/D)** OR press keys `1`–`4` → submits answer, reveals correct answer + solution
- **Click "Next"** OR press `Enter` → advances to the next question (or to results on the last question)
- **Click "Quit"** → returns to home (with confirmation)
- **Click "Try Again"** on results → restarts the same quiz from Q1
- **Click "Home"** on results → returns to the chapter selection screen

## 📦 Tech Stack

- **HTML5** — Semantic markup (`<header>`, `<main>`, `<section>`)
- **CSS3** — Custom properties, gradients, flexbox, grid, animations (no framework)
- **Vanilla JavaScript** — No build step, no dependencies
- **Google Fonts** — Poppins typeface (via CDN)
- **Font Awesome 6.4** — Icon library (via jsDelivr CDN)

## 📊 Data Model

All quiz data is **embedded directly inside `index.html`** as a JavaScript constant. No external database or API is used.

```js
const QUESTIONS = [
  {
    q:  "Mother : Child :: Cloud : ?",   // Question text
    o:  ["Weather","Loud","Rain","Shine"], // 4 options (A,B,C,D)
    a:  2,                                  // Index (0-3) of correct option
    s:  "A mother gives birth..."           // Solution / explanation
  },
  // ... 99 more
];
```

### Runtime State (in-memory only)

```js
state = {
  current: 0,        // Current question index
  score: 0,          // Live score
  correct: 0,        // Correct answers count
  wrong: 0,          // Wrong answers count
  skipped: 0,        // Skipped count
  answered: false,   // Has user answered current question
  answers: []        // Detailed log of every answer
}
```

> **Note:** State resets on page reload — there is no persistence layer (no localStorage, no backend). This was a deliberate design choice for a clean, lightweight static deployment.

## 🚀 Deployment

This site is 100% static. To deploy and make it live, please use the **Publish tab** — it will handle the deployment process automatically and provide you with a live URL.

## 🚧 Features Not Yet Implemented

- [ ] **Additional Chapters** — Classification, Series, Coding-Decoding, etc. (currently locked)
- [ ] **Persistent Progress** — Save scores to `localStorage` across sessions
- [ ] **Question Shuffle Mode** — Randomize question order on each attempt
- [ ] **Timed Mode** — Optional countdown timer per question
- [ ] **Bookmarking** — Mark hard questions for later review
- [ ] **Review Screen** — Browse all answers after completing the quiz
- [ ] **Hindi Language Toggle** — Original PDF is bilingual; currently English only
- [ ] **Difficulty Filtering** — Easy / Medium / Hard categorization
- [ ] **Leaderboard / Stats** — Compare performance across attempts
- [ ] **Export Results** — Download score report as PDF/PNG

## 🎯 Recommended Next Steps for Development

1. **Add localStorage persistence** so users can resume mid-quiz and see historical best scores
2. **Build out Chapter 2 (Classification)** following the same `QUESTIONS` array pattern
3. **Add a "Review Answers" screen** accessible from the result page, listing every Q with the user's answer vs. the correct answer
4. **Introduce a Practice Mode vs. Test Mode** — practice shows solutions immediately; test mode shows them only at the end
5. **Migrate questions to the RESTful Table API** if multi-chapter, multi-user, or admin editing becomes needed
6. **Add a settings panel** for font size, dark mode, and language toggle (Hindi/English)
7. **Implement question shuffling and option randomization** to prevent rote memorization of position

## 📁 Project Structure

```
.
├── index.html      # Complete self-contained quiz application
└── README.md       # This file
```

## 📝 Source Material

Questions and solutions are derived from:
> **Uttar Pradesh UPSI & Constable Reasoning** — Rakesh Yadav Readers Publication Pvt. Ltd. (Chapter 01: Analogy, Questions 1–100 with official answer key)
