# 🧠 NEURAL PONG

**An AI opponent that learns your patterns in real-time and adapts its strategy.**

### [▶ Play Now](https://saleha13.github.io/adaptive-ai-game/)

---

## What is this?

Neural Pong looks like classic Pong — but the AI opponent is watching everything you do. Where you hit, how you react, your positioning tendencies. It builds a model of your play style and adapts in real-time.

Watch the AI's brain on screen as it learns. See what patterns it's detected, what strategy it's using against you, and what it thinks you'll do next.

## Features

- **Real-time adaptive AI** — Uses Q-learning + pattern recognition that genuinely learns
- **Visible AI brain** — Live strategy display, confidence meter, prediction accuracy, position heatmap
- **AI personalities** — Shifts between Calibrating → Defensive → Aggressive → Predictive → Adaptive
- **10 adaptation levels** — AI gets progressively smarter as it plays you
- **Visual polish** — Particle effects, ball trails, screen shake, speed-reactive glow colors
- **Synth sound effects** — Web Audio API generated sounds, no external files
- **Stats dashboard** — Rallies, longest rally, top speed, reaction time, win rate over time
- **Zero dependencies** — Single HTML file, no build step, no framework

## How the AI Works

### Pattern Recognition
The AI tracks your paddle positions in a 10-segment heatmap and maintains a sliding window of your last 8 hit positions. It detects:
- **Alternating patterns** (top-bottom-top) and counter-predicts
- **Drift patterns** (consistently moving one direction) and pre-positions
- **Zone tendencies** (top/center/bottom preference) weighted by recency

### Q-Learning
A tabular Q-learning agent maps discretized game states (ball position, ball velocity, paddle position) to actions (move up, stay, move down). It receives:
- +2.0 reward when it scores
- -2.0 penalty when the player scores  
- +0.5 for successful returns
- Epsilon-greedy exploration that decays from 30% → 5%

### Strategy Engine
Based on accumulated data and prediction accuracy, the AI shifts between strategies:
- **Calibrating** (0-5 hits) — Gathering initial data
- **Defensive** (5-15 hits) — Center-biased, conservative
- **Predictive** (>50% accuracy) — Pre-positions based on predictions
- **Aggressive** (edge play detected) — Aims away from predicted player position
- **Adaptive** (default) — Blended approach

## Tech Stack

Pure HTML/CSS/JS. Single file. No build. No dependencies.

- Canvas 2D for game rendering
- Web Audio API for synthesized sound effects
- CSS animations + Canvas particles for visual effects
- JetBrains Mono + Inter fonts

## Run Locally

Just open `index.html` in a browser. That's it.

---

Built as a demo of real-time adaptive game AI.
