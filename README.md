# Operation Firewall

> An interactive 60-minute cybersecurity-maths classroom puzzle for Year 9 students. Built for the Aston University Mathematics School (AUMS) Maths & Cybersecurity Day.

**The setup:** the (fictional) Cipher Syndicate is trying to exfiltrate years of confidential research from the Aston University database. Your team has been temporarily commissioned as a Junior Cyber Mathematician. You have one hour and five mathematical defence layers between you and disaster.

Each layer is a real branch of cryptography — Caesar ciphers, primality, hash functions, RSA, post-quantum schemes. Each maps onto a real-world hack (TalkTalk, WannaCry, LinkedIn, Equifax, SolarWinds, Shor's algorithm). And each unlocks the next.

---

## What's in here

- **`index.html`** — the entire app, single self-contained file. Drop it on any web server, or open locally.

That's it. No build step, no dependencies to install. The JSX is pre-compiled; the file just needs React + Tailwind from public CDNs on first load.

The app is ~108 KB of HTML/CSS/JS with all five sections, popups, warnings, well-done screens, a Caesar wheel, a frequency analyser, a hash-table builder, a binary primality forensics grid, an RSA factorisation puzzle, a composite cipher decoder, a Mission Control terminal log, and a 3-rung hint ladder on every task.

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

Double-click `index.html`. Your browser opens it. Needs internet on first load to fetch React + Tailwind from CDN.

### Option 2 — host on GitHub Pages (recommended for classroom)

1. Create a new GitHub repository (e.g. `operation-firewall`)
2. Upload these files to the root
3. Go to **Settings → Pages**
4. Source: **Deploy from a branch**, Branch: **main**, Folder: **/ (root)**
5. Click **Save**
6. Wait ~1 minute. Your URL will be:
   `https://YOUR-USERNAME.github.io/operation-firewall/`
7. Share that link with students on the day.

### Option 3 — any other static host

Netlify, Vercel, Cloudflare Pages, your school's own web space — drop the file anywhere static files are served.

---

## Customising

Open `index.html` in a text editor. The structure is:

1. `<head>` — CSS variables (AUMS palette), animations, fonts
2. `<body>` — empty `<div id="root">` for React to mount into
3. `<script src="https://unpkg.com/react@18.2.0/...">` — React from CDN
4. `<script src="https://unpkg.com/react-dom@18.2.0/...">` — ReactDOM from CDN
5. `<script src="https://cdn.tailwindcss.com">` — Tailwind from CDN
6. `<script>...compiled app code...</script>` — the whole app, pre-compiled JavaScript

To change colours, edit the `:root { --astonorange: ...; }` block near the top.

To change puzzle answers, search for the constants in each `Section*` function (e.g. `A1_CIPHER`, `A3_TARGET`, `D3_N`). Be aware the inline script is pre-compiled — there's no JSX to edit; you'd be editing `React.createElement` calls.

---

## Why this exists

Most "cyber-for-schools" content stops at "isn't crypto cool". This goes the other way: every layer is a piece of GCSE-touching maths the students are *already* learning (modular arithmetic, place value, primality, function inverses, factorisation), wrapped in a real-world threat they've heard of, with the maths-cyber bridge made unmissable. The aim is that by the time a Year 9 student finishes Section E, they have personally cracked a hash, factored a semi-prime by trial division, and reasoned about why a quantum computer changes everything.

---

## Credits

Built for Aston University Mathematics School (AUMS), part of the Aston University STEM Education Academy Trust. Free to use, modify, share, and adapt under the MIT licence (see `LICENSE`). The mathematical content is original; the framing is standard cryptography curriculum; the real-world hack summaries are based on public reporting.
