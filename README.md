<div align="center">

<img src="https://img.shields.io/badge/made%20with-GLM%20%2B%20Gemini%20Pro%203.1-7c3aed?style=for-the-badge&labelColor=1e1b4b" alt="made with GLM + Gemini Pro 3.1">

# Mastery OS — Tri-Core Edition

**One learning system. Three personalities. Zero excuses.**

[**Live Demo**](https://structured-learning.netlify.app) · [Report Bug](#) · [Suggest Feature](#)

<img src="https://img.shields.io/badge/HTML5-single%20file-e34f26?style=flat-square&logo=html5&logoColor=white" alt="HTML5">
<img src="https://img.shields.io/badge/Tailwind_CSS-CDN-06b6d4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind">
<img src="https://img.shields.io/badge/Vanilla_JS-zero%20deps-f7df1e?style=flat-square&logo=javascript&logoColor=black" alt="JS">
<img src="https://img.shields.io/badge/GLM-AI%20Powered-8b5cf6?style=flat-square&logoColor=white" alt="GLM">
<img src="https://img.shields.io/badge/Gemini_Pro_3.1-AI%20Powered-4285f4?style=flat-square&logo=google&logoColor=white" alt="Gemini Pro 3.1">

</div>

---

## what is this

Mastery OS is a **single-file learning operating system** that runs entirely in your browser. No build steps. No backend. No npm install. Just open the HTML file and start learning.

It combines four science-backed learning tools into one place:

| Tool | What It Does |
|---|---|
| **Blueprint** | Define exactly what you're learning and how you'll prove you learned it |
| **Curriculum** | Break your goal into modules, track completion, interleave with shuffle |
| **Feynman AI** | Explain concepts in your own words — Gemini calls out your gaps ruthlessly |
| **Recall Vault** | SM-2 spaced repetition flashcards that actually schedule your reviews |

Plus a **Pomodoro timer** with streak tracking that persists across sessions.

---

## the three editions

This is the part I'm most proud of. Same data, same features — completely different vibe.

### 🪟 Standard

Clean. Rounded. macOS-energy. Glassmorphism panels and blue accents. If you like things pretty and intuitive, this is your home.

### 💚 Hacker

Terminal aesthetic. CRT scanline overlay. Square-wave keystroke sounds on every keypress. A cinematic boot sequence. Built-in terminal emulator. File paths as navigation. Green-on-black everything. It feels like you're hacking into your own brain.

### 📜 Zen (Academic)

Paper and ink. Serif typography. Minimal borders. No visual noise. Designed for one thing — **deep focus**. Every pixel exists to get out of your way.

> **Your data is shared across all three.** Switch anytime from Settings. Your flashcards, curriculum, and goals follow you.

---

## quick start

```bash
# 1. Clone or download the HTML file
git clone https://github.com/YOUR_USERNAME/MasteryOS.git

# 2. Open it. That's it.
open index.html        # macOS
xdg-open index.html    # linux
start index.html       # windows
```

No server needed. `localStorage` handles all persistence.

---

## setting up Feynman AI (optional but recommended)

The AI feature uses Google's Gemini 1.5 Flash. It's free-tier friendly.

1. Go to [Google AI Studio](https://aistudio.google.com/apikey)
2. Generate an API key
3. Open Mastery OS → Settings → Paste the key
4. Start explaining concepts and get called out on your BS

> Without an API key, everything else works perfectly. Only the Feynman chat requires it.

---

## how the SM-2 vault works

The flashcard system implements the **SuperMemo SM-2 algorithm** — the same one Anki uses:

```
After each review, you grade yourself:
  1 → Again    → Reset to day 1
  3 → Hard     → Small interval increase
  5 → Easy     → Full interval increase (× ease factor)

Cards sort by next review date. Due cards show first.
```

Your ease factor adjusts based on performance. Struggle too much and intervals shrink. Recall effortlessly and they stretch.

---

## project structure

```
MasteryOS/
└── index.html          ← the entire app. yes, really.
```

Single file. ~500 lines of HTML/CSS/JS. No frameworks. No build tools. No node_modules black hole.

---

## the honest part

I'm a 4th semester IT student. I understand code conceptually — I know what a function does, what an API is, how state works. But sitting down and writing it from scratch? That's where I hit a wall.

So I use **GLM** and **Gemini Pro 3.1** to write code for me. And I'm not hiding it.

**Here's what I actually did:**

- Designed the entire UX — the three-edition concept, the layout, the flow
- Understood every system (SM-2 algorithm, Pomodoro logic, Gemini API integration)
- Decided what features matter and what doesn't
- Tested, iterated, and refined the output
- Wrote this README myself

**Here's what AI did:**

- Translated my ideas into syntax
- Handled the CSS gymnastics (flip cards, CRT effects, theme switching)
- Wrote the DOM manipulation logic
- Caught edge cases I'd have spent hours debugging

If you want to call this "not real code" — fair enough. But the **product** is real. The **system design** is real. And honestly? This approach is faster than most people think. Way faster.

I'm open to every improvement. If you see messy code, refactor it. If you see a missing feature, add it. If you think the SM-2 implementation is wrong, fix it. I'll learn from your PR.

---

## features I want to add

- [ ] Export/import data as JSON (so you don't lose everything clearing cookies)
- [ ] Custom Pomodoro durations (currently hardcoded to 25 min)
- [ ] Dark mode for Standard edition
- [ ] Keyboard shortcuts (the Hacker edition has Alt+1-4 partially wired)
- [ ] Statistics dashboard (cards reviewed, accuracy trend, study hours)
- [ ] Markdown support in Feynman responses
- [ ] PWA support — install it as an app on your phone
- [ ] Sound toggle for Hacker mode (some people hate the keystrokes lol)

---

## contributing

I'm genuinely new to open source. But I know the rules:

1. **Fork** the repo
2. **Branch** off `main` (`git checkout -b feature/your-thing`)
3. **Commit** with clear messages
4. **PR** with a short description of what changed

Don't ask permission. If it makes the app better, I'll merge it.

---

## tech details for the curious

| Aspect | Implementation |
|---|---|
| **Styling** | Tailwind CSS via CDN + custom CSS for animations and theme-specific styles |
| **Fonts** | Inter (Standard), Fira Code (Hacker), Merriweather (Zen) |
| **State** | `localStorage` — single JSON object with goals, curriculum, flashcards, pomodoro data |
| **AI** | Gemini 1.5 Flash via REST API, streaming simulation with token-by-token DOM injection |
| **Audio** | Web Audio API — oscillator-based square wave at 400-600Hz, 40ms decay |
| **Spaced Repetition** | SM-2 algorithm with ease factor floor at 1.3 |
| **Animations** | CSS `transform: rotateY(180deg)` for flip cards, `@keyframes` for fade-ins |
| **Theme Switching** | Class-based — `hacker-theme`, `normal-theme`, `zen-theme` on `<body>` |

---

## license

MIT — do whatever you want with it. Learn from it, break it, rebuild it better.

---

<div align="center">

**built by a student who asked AI the right questions**

if this helped you study even once, it was worth making.

</div>
```
