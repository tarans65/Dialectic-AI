# ⚡ Dialectic AI

> Sharpen your argument. 

---

## Motivation

I enjoyed debate in high school and always felt it was one of the best ways to sharpen critical thinking. Most students don't have a sparring partner on demand, so I built one. Dialectic AI gives anyone an intelligent opponent to practice arguing any topic, anytime.

---

## What It Does

You enter any debate topic and pick whether you're arguing FOR or AGAINST it. The AI instantly takes the other side, delivers a structured opening argument, and rebuts everything you say. After every two rounds a live **Debate Scorecard** grades both sides on:

- **Logic** — are you building a real argument, or just making assertions?
- **Clarity** — is your reasoning organized and easy to follow?
- **Persuasiveness** — are you actually compelling, or just verbose?

---

## How the Code Works

The entire app lives in a single `ai-debate-arena.html` file.

### Response Engine
The AI opponent is powered by a rule-based response engine in JavaScript. It scans your text for keywords across 10 semantic clusters:

| Cluster | Example keywords |
|---|---|
| Freedom & rights | `freedom`, `liberty`, `rights` |
| Economy | `money`, `jobs`, `cost`, `growth` |
| Science & evidence | `data`, `research`, `studies`, `proven` |
| History | `historical`, `past`, `traditionally` |
| Morality & ethics | `moral`, `ethical`, `right`, `wrong` |
| Government & policy | `law`, `regulation`, `government` |
| Technology | `innovation`, `progress`, `technology` |
| Environment | `climate`, `nature`, `environment` |
| Society | `people`, `community`, `public` |
| Future generations | `children`, `future`, `generation` |

Each cluster maps to a targeted rebuttal. If no keyword matches, the engine accuses you of a named logical fallacy — slippery slope, false dichotomy, straw man, ad hominem, and others.

### Scoring System
Arguments are scored by lexical analysis across three word banks:

- **Evidence words**: `because`, `therefore`, `studies show`, `data suggests`, `research demonstrates`
- **Clarity markers**: `furthermore`, `however`, `specifically`, `for example`, `in contrast`
- **Persuasion signals**: `crucial`, `essential`, `fundamentally`, `undeniable`, `must`

Word count is factored in as a modifier. The live **Argument Strength Meter** updates in real time as you type.

### UI
Vanilla HTML/CSS/JS — no libraries. Key techniques: CSS custom properties for the full design token system, `@keyframes` for all animations (bubbles, typing indicator, scorecard reveals, title shimmer/glitch), and a CSS grid-line background rendered with `linear-gradient` on a pseudo-element.

---

## Running It
```bash
git clone https://github.com/tarans65/Dialectic-AI.git
cd Dialectic-AI
python3 -m http.server 8080
# Open http://localhost:8080
```

Or just double-click `ai-debate-arena.html` directly in your browser.

---

## Scoring Tips

- Lead with a **claim**, then support it with evidence (`because`, `studies show`)
- Use **transition words** to structure reasoning (`furthermore`, `however`, `in contrast`)
- **Longer, denser arguments** score higher on persuasiveness
- Anticipate the counterargument and address it preemptively

---

## Tech Stack

| Layer | Choice |
|---|---|
| UI | Vanilla HTML/CSS/JS |
| Fonts | Google Fonts (Bebas Neue, DM Sans, JetBrains Mono) |
| Response engine | Keyword detection + template filling |
| Scoring | Lexical analysis across three word banks |
| Dependencies | None |

---


---

*Built by Taran Srikonda — [github.com/tarans65](https://github.com/tarans65)*
