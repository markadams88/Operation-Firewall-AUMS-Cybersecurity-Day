# Operation Firewall

> An interactive 60-minute cybersecurity-maths classroom puzzle for Year 9 students. Built for the Aston University Mathematics School (AUMS) Maths & Cybersecurity Day.

**The setup:** the (fictional) Cipher Syndicate is trying to exfiltrate years of confidential research from the Aston University database. Your team has been temporarily commissioned as a Junior Cyber Mathematician. You have one hour and five mathematical defence layers between you and disaster.

Each layer is a real branch of cryptography — Caesar ciphers, primality, hash functions, RSA, post-quantum schemes. Each maps onto a real-world hack (TalkTalk, WannaCry, LinkedIn, Equifax, SolarWinds, Shor's algorithm). And each unlocks the next.

---

## What's in here

- **`index.html`** — the entire app, single self-contained file. Drop it on any web server.

That's it. No build step, no dependencies to install. Open the file in a browser and play.

The app uses React + Tailwind + Babel via CDN. It is ~96 KB of HTML/CSS/JSX with all five sections, popups, warnings, well-done screens, a Caesar wheel, a frequency analyser, a hash-table builder, a binary primality forensics grid, an RSA factorisation puzzle, a composite cipher decoder, a Mission Control terminal log, and a 3-rung hint ladder on every task.

---

## The five sections

| # | Section | Maths | Real-world hook | Codeword |
|---|---------|-------|-----------------|----------|
| **A** | Authentication Layer | Caesar cipher · frequency analysis · modular arithmetic | Bletchley Park · Enigma | `JHLZHY` |
| **B** | The Firewall | Binary place value · primality testing · trial division | WannaCry · network forensics | `S3 (137)` |
| **C** | The Hash Function | Function notation · inverse functions · mod 26 | LinkedIn 2012 · unsalted SHA-1 | `TROJAN` |
| **D** | The Prime Vault | Prime factorisation · Euler's totient | RSA Challenge · banking crypto | `1517 = 37 × 41, φ = 1440` |
| **E** | The Quantum Gauntlet | Composition of inverses · post-quantum reasoning | Shor's algorithm · CRYSTALS-Kyber | `ASTON IS SAFE` |

The full puzzle progression is gated: students cannot enter Section B until they have completed Section A, and so on. Section E ends with an open-ended cipher-design task explicitly framed as "no team is expected to finish."

---

## Running it

### Option 1 — open the file locally

Double-click `index.html`. Done.

### Option 2 — host it on GitHub Pages (recommended for classroom)

1. Create a new GitHub repository (e.g. `operation-firewall`)
2. Upload `index.html` (and these other files) to the root
3. Go to **Settings → Pages**
4. Source: **Deploy from a branch**, Branch: **main**, Folder: **/ (root)**
5. Click **Save**
6. Wait ~1 minute. Your URL will be:
   `https://YOUR-USERNAME.github.io/operation-firewall/`
7. Share that link with students on the day.

### Option 3 — any other static host

Netlify, Vercel, Cloudflare Pages, your school server — drop the file anywhere static files are served.

---

## Customising

Open `index.html` in a text editor. Everything is documented at the top.

- **Colours** — search for `:root {` near the top of the `<style>` block. The AUMS palette is defined as CSS variables.
- **Puzzle answers** — the ciphertexts and answers are hardcoded in each `Section*` component. Search for e.g. `A1_CIPHER`, `A2_CIPHER`, `D3_N`, etc.
- **Hints** — each task has a `<HintLadder>` with three escalating hints. Search for `HintLadder` to find them.
- **Real-world flavour text** — search for `realWorld:` in the `onComplete` calls in each section.
- **School / event branding** — the title bar shows "OPERATION FIREWALL // ASTON CYBER COMMAND". Search for "ASTON" to retheme.

If you change a puzzle answer, also update the corresponding hint and the section's `realWorld` callback so things stay coherent.

---

## On the day — how it's meant to run

1. Project the [`Operation Firewall PowerPoint deck`](https://github.com/<your-username>/operation-firewall) on the big screen up front. (Or use the slides PDF — both are designed to mirror the app.)
2. Students work in teams of four at laptops or tablets, each team on `index.html` via the link.
3. Each team enters their school name + a team callsign at the start. The app then walks them through Briefing → 5 Sections → Debrief.
4. At the end of each section the app shows a big "REPORT IN" pop-up with the codeword. Students raise their hand and call out: *"School ___ — Section A complete. Codeword: JHLZHY!"*
5. You mark them off on a board at the front. The team that breaches all five layers — and ideally drafts a post-quantum cipher design in Section E — wins.

The full 60 minutes:

| Time | Stage |
|------|-------|
| 0–3 min | Intro · briefing · team setup |
| 3–13 min | Section A (Caesar) |
| 13–23 min | Section B (Firewall) |
| 23–35 min | Section C (Hash) |
| 35–47 min | Section D (RSA) |
| 47–57 min | Section E (Quantum) |
| 57–60 min | Debrief |

---

## Why this exists

Most "cyber-for-schools" content stops at "isn't crypto cool". This goes the other way: every layer is a piece of GCSE-touching maths the students are *already* learning (modular arithmetic, place value, primality, function inverses, factorisation), wrapped in a real-world threat the students have heard of (WannaCry, LinkedIn, etc.), and explicitly named so the maths-cyber bridge is unmissable. The aim is that by the time a Year 9 student finishes Section E, they have personally cracked a hash, factored a semi-prime by trial division, and reasoned about why a quantum computer changes everything.

It's the kind of session that a maths department can run once a year, and the same students will come back two years later asking to do A-level Further Maths "because of the RSA thing."

---

## Credits

Built for Aston University Mathematics School (AUMS) · part of the Aston University STEM Education Academy Trust · Maths & Cybersecurity Day. Free to use, modify, share, and adapt under the MIT licence (see `LICENSE`).

The puzzles' mathematical content is original. The framing (Caesar, RSA, Shor, etc.) is standard cryptography curriculum. The real-world hack summaries are based on public reporting.

---

## File structure

```
operation-firewall/
├── index.html       # the entire app
├── README.md        # this file
├── LICENSE          # MIT
└── .gitignore
```
