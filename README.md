<div align="center">

  <!-- HERO BANNER (ANIMATED SVG HUD) -->
  <img src="assets/hero-banner.svg" alt="Sathwik Elaprolu // Systems & Software Engineer" width="100%"/>

  <br/>

  <!-- QUICK ACCESS TELEMETRY / ACTION BAR -->
  <p align="center">
    <a href="https://sathwik-e-portfolio.vercel.app" target="_blank">
      <img src="https://img.shields.io/badge/HUD_PORTFOLIO-sathwik--e--portfolio.vercel.app-22c55e?style=for-the-badge&logo=vercel&logoColor=white&labelColor=08090d" alt="Live Portfolio"/>
    </a>
    <a href="https://www.linkedin.com/in/sathwik-elaprolu" target="_blank">
      <img src="https://img.shields.io/badge/CONNECT-LINKEDIN-0077b5?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=08090d" alt="LinkedIn Profile"/>
    </a>
    <a href="mailto:sathwik.elaprolu@gmail.com">
      <img src="https://img.shields.io/badge/TRANSMIT-sathwik.elaprolu@gmail.com-ea4335?style=for-the-badge&logo=gmail&logoColor=white&labelColor=08090d" alt="Email Direct"/>
    </a>
    <img src="https://img.shields.io/badge/STATUS-AVAILABLE_FOR_ROLES-22c55e?style=for-the-badge&logo=statuspal&logoColor=white&labelColor=08090d" alt="Status: Open for Roles"/>
  </p>

  <!-- LIVE MOTORSPORT TELEMETRY STREAM TYPING ANIMATION -->
  <p align="center">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=15&duration=2600&pause=1200&color=4ADE80&background=07090E00&center=true&vCenter=true&width=780&height=34&lines=%3E+Specialized+in+Motorsport+Telemetry+%26+Simulation+Engineering;%3E+Ingesting+60Hz+Forza+Motorsport+raw+UDP+telemetry+streams...;%3E+Apex+AI%3A+Predicting+non-linear+Pirelli+F1+tire+degradation+curves...;%3E+Pitwall%3A+Sub-150ms+Groq+voice+AI+crew+chief+radio+dispatch...;%3E+Analyzing+live+lap+deltas%2C+apex+speeds+%26+braking+friction+circles...;%3E+Eliminating+synthetic+latency+across+low-level+sockets..." alt="Live Motorsport Telemetry Stream"/>
  </p>

  <img src="assets/divider.svg" alt="Separator" width="100%"/>

</div>

```
┌── HOST SYSTEM SPECS ────────────────────────────────────────────────────────────────────────┐
│  USER: sathwik-e             LOCATION: Hyderabad, IN [17.3850° N, 78.4867° E]               │
│  AFFILIATION: St Mary's EC   DEGREE: B.Tech Computer Science & Engineering (Class of 2028)  │
│  SPECIALIZATION:             Motorsport Telemetry · Sim Racing Engines · Low-Latency UDP    │
│  ACTIVE RUNTIME:             60Hz Binary Sockets · F1 Wear Modeling · Sub-150ms Voice Loops │
└─────────────────────────────────────────────────────────────────────────────────────────────┘
```

> **Systems & Motorsport Software Engineer** specialized in high-frequency racing telemetry, simulation physics streams, and machine learning models for motorsport strategy. I build close to sockets, protocols, and raw data buffers—handling live mechanical and network stress from parsing raw 60Hz UDP vehicle dynamics in racing simulators to predicting non-linear tire thermal degradation on Formula 1 circuits.

<br/>

---

## 🏎️ 00 // LIVE MOTORSPORT TELEMETRY & SIMULATION HUD

> Real-time sim racing telemetry engine, 60Hz UDP packet parsing, live tire degradation thermals, and conversational voice AI crew chief dispatch.

<div align="center">
  <img src="assets/motorsport-telemetry-hud.svg" alt="MoTeC / Pitwall Simulation Telemetry HUD" width="100%"/>
</div>

<details>
<summary><b>[VIEW MOTORSPORT DATA PIPELINE &amp; TELEMETRY DICTIONARY]</b></summary>

<br/>

```
┌── PACKET INGEST SPECIFICATION // FORZA MOTORSPORT & F1 TELEMETRY ────────────────────────────┐
│                                                                                              │
│  INGESTION PROTOCOL:      Raw UDP Datagram (Zero Handshake Overhead)                         │
│  PAYLOAD ARCHITECTURE:    324-Byte Binary C-Struct Unpack (struct.unpack)                    │
│  SAMPLING FREQUENCY:      60.0 Hz (16.66ms hard real-time packet deadline)                   │
│                                                                                              │
│  TRACKED CHANNELS:                                                                           │
│  ▸ KINEMATICS:   Wheel Slip Ratio (FL, FR, RL, RR) · Suspension Travel · Angular Pitch/Roll  │
│  ▸ POWERTRAIN:   Engine RPM · Gearbox State · Throttle/Brake Pedal Trace · Turbo Boost       │
│  ▸ DYNAMICS:     Friction Circle (Lateral/Longitudinal G) · Slip Angles · Yaw Velocity       │
│  ▸ THERMALS:     Tire Core & Surface Temperatures (°C) · Dynamic Compound Wear Index         │
│  ▸ DISPATCH:     Bidirectional Groq LLM + Edge-TTS AI Crew Chief Audio Loop (<150ms)        │
└──────────────────────────────────────────────────────────────────────────────────────────────┘
```

</details>

<br/>

<div align="center">
  <img src="assets/telemetry-bar.svg" alt="Real-Time Telemetry Feed" width="100%"/>
</div>

<br/>

---

## ■ 01 // SYSTEM BLUEPRINT & CODE ARCHITECTURE

> High-frequency telemetry ingestion, zero-copy packet deserialization, and real-time audio dispatch.

<div align="center">
  <img src="assets/system-blueprint.svg" alt="System Blueprint & Code Architecture" width="100%"/>
</div>

<details>
<summary><b>[VIEW RUNTIME SPECIFICATION &amp; DATA PIPELINE BREAKDOWN]</b></summary>

<br/>

```
  ┌─────────────────┐       ┌─────────────────┐       ┌──────────────────┐       ┌─────────────────┐
  │   RAW UDP IN    │ ───>  │  DESERIALIZER   │ ───>  │  IN-MEM RING BUF │ ───>  │  HUD / VOICE AI │
  │ Forza Sim 60Hz  │       │ struct.unpack() │       │ Drop Stale Frames│       │ Groq + Edge-TTS │
  │ 324 Bytes/pkt   │       │ <0.08ms latency │       │ Zero Buffer Bloat│       │ <150ms Callout  │
  └─────────────────┘       └─────────────────┘       └──────────────────┘       └─────────────────┘
```

- **Zero-Copy Ingestion**: Raw binary UDP datagrams are intercepted directly over localhost socket port `20777` without TCP handshake or retransmission overhead.
- **Strict Frame Budgeting**: Operates within a `16.6ms` window (60Hz). If socket buffers experience backpressure, stale frames are discarded immediately in favor of current vehicle physics state.
- **Sub-150ms Voice Feedback**: Low-latency token generation via Groq inference engine piped directly into Microsoft Edge-TTS streaming synthesis for live conversational race engineering.

</details>

<br/>

---

## ■ 02 // MOTORSPORT & PRODUCTION SYSTEMS WORK

<table>
  <thead>
    <tr>
      <th align="left" width="30%">SYSTEM</th>
      <th align="left" width="15%">TAG</th>
      <th align="left" width="35%">ENGINEERING FOCUS</th>
      <th align="center" width="20%">SPECS & LINKS</th>
    </tr>
  </thead>
  <tbody>
    <!-- Project 1: Pitwall -->
    <tr>
      <td>
        <b>01. Pitwall</b><br/>
        <sub>2026 // Production</sub>
      </td>
      <td>
        <code>MOTORSPORT</code><br/>
        <img src="https://img.shields.io/badge/60Hz-UDP-22c55e?style=flat-square&labelColor=08090d" alt="60Hz UDP"/>
      </td>
      <td>
        Live telemetry dashboard for sim racing. Reads raw UDP telemetry from Forza at 60Hz, executes zero-copy binary unpacking, and narrates live race telemetry back through a conversational voice AI pit crew chief mid-race (<150ms loop).
        <br/><br/>
        <sub><b>Stack:</b> Python, Flask, WebSockets, Groq API, Edge-TTS</sub>
      </td>
      <td align="center">
        <a href="https://github.com/sathwik-e/pitwall" target="_blank">
          <img src="https://img.shields.io/badge/REPO-06_COMMITS-1f2937?style=flat-square&logo=github&logoColor=4ade80" alt="Repo"/>
        </a><br/>
        <a href="https://sathwik-e-portfolio.vercel.app" target="_blank">
          <img src="https://img.shields.io/badge/VIEW-LIVE_HUD-22c55e?style=flat-square" alt="Live HUD"/>
        </a>
      </td>
    </tr>
    <!-- Project 2: Apex AI -->
    <tr>
      <td>
        <b>02. Apex AI</b><br/>
        <sub>2026 // Research</sub>
      </td>
      <td>
        <code>MOTORSPORT ML</code><br/>
        <img src="https://img.shields.io/badge/ML-REGRESSOR-38bdf8?style=flat-square&labelColor=08090d" alt="ML Regressor"/>
      </td>
      <td>
        Formula 1 motorsport analytics engine utilizing FastF1 telemetry streams. Predicts non-linear Pirelli tire compound degradation curves using an ensemble Random Forest Regressor trained on lap deltas, compound age, sector speeds, and dynamic track temperatures.
        <br/><br/>
        <sub><b>Stack:</b> Python, FastF1 API, Scikit-Learn, Random Forest, Flask</sub>
      </td>
      <td align="center">
        <a href="https://github.com/sathwik-e/apex-ai" target="_blank">
          <img src="https://img.shields.io/badge/REPO-02_COMMITS-1f2937?style=flat-square&logo=github&logoColor=4ade80" alt="Repo"/>
        </a><br/>
        <img src="https://img.shields.io/badge/PAPER-RESEARCH-6366f1?style=flat-square" alt="Research"/>
      </td>
    </tr>
    <!-- Project 3: MedAssist AI -->
    <tr>
      <td>
        <b>03. MedAssist AI</b><br/>
        <sub>2025 // Production</sub>
      </td>
      <td>
        <code>AI &amp; VISION</code><br/>
        <img src="https://img.shields.io/badge/LOCAL-SQLITE-a7f3d0?style=flat-square&labelColor=08090d" alt="Local SQLite"/>
      </td>
      <td>
        Local-first health companion. Extracts structured medication schedules from handwritten doctor prescriptions via client-side Tesseract OCR and Gemini structured verification. Zero cloud leakage with 100% on-device SQLite database storage.
        <br/><br/>
        <sub><b>Stack:</b> JavaScript, Node.js, SQLite, Tesseract OCR, Gemini API</sub>
      </td>
      <td align="center">
        <a href="https://github.com/sathwik-e/medassist-ai" target="_blank">
          <img src="https://img.shields.io/badge/REPO-★_01_STAR-1f2937?style=flat-square&logo=github&logoColor=4ade80" alt="Repo"/>
        </a><br/>
        <img src="https://img.shields.io/badge/100%25-PRIVATE-10b981?style=flat-square" alt="Private"/>
      </td>
    </tr>
    <!-- Project 4: Watchdog -->
    <tr>
      <td>
        <b>04. Watchdog</b><br/>
        <sub>2026 // Hackathon</sub>
      </td>
      <td>
        <code>SCRAPING</code><br/>
        <img src="https://img.shields.io/badge/HACKATHON-BRIGHT_DATA-f59e0b?style=flat-square&labelColor=08090d" alt="Bright Data"/>
      </td>
      <td>
        Built for the Bright Data Web Scraping Hackathon. Anti-price-gouging automated monitor with resilient scraper pipelines, dynamic proxy mesh rotation, and automated selector failure recovery routines.
        <br/><br/>
        <sub><b>Stack:</b> Next.js, TypeScript, Bright Data Scraper Studio, Tailwind CSS</sub>
      </td>
      <td align="center">
        <a href="https://github.com/sathwik-e/watchdog" target="_blank">
          <img src="https://img.shields.io/badge/REPO-05_COMMITS-1f2937?style=flat-square&logo=github&logoColor=4ade80" alt="Repo"/>
        </a><br/>
        <img src="https://img.shields.io/badge/STATUS-SHIPPED-22c55e?style=flat-square" alt="Shipped"/>
      </td>
    </tr>
    <!-- Project 5: Blindfold -->
    <tr>
      <td>
        <b>05. Blindfold</b><br/>
        <sub>2026 // Automation</sub>
      </td>
      <td>
        <code>AUTOMATION</code><br/>
        <img src="https://img.shields.io/badge/LOCAL-VLM-c084fc?style=flat-square&labelColor=08090d" alt="Local VLM"/>
      </td>
      <td>
        Autonomous DOM selector self-healing agent. When HTML class trees or obfuscated shadow roots break traditional scrapers, Blindfold captures viewport frames, queries a local Vision-Language Model to re-anchor targets, and patches selector logic on the fly.
        <br/><br/>
        <sub><b>Stack:</b> Python, Playwright, Local VLM, FastAPI</sub>
      </td>
      <td align="center">
        <a href="https://github.com/sathwik-e/blindfold" target="_blank">
          <img src="https://img.shields.io/badge/REPO-★_01_STAR-1f2937?style=flat-square&logo=github&logoColor=4ade80" alt="Repo"/>
        </a><br/>
        <img src="https://img.shields.io/badge/94%25%2B-RECOVERY-22c55e?style=flat-square" alt="Recovery"/>
      </td>
    </tr>
  </tbody>
</table>

<br/>

---

## ■ 03 // ENGINEERING DECISION LOG

> *"Every system has a trade-off — the log shows how I decide."*

<details>
<summary><b>#001 // Why UDP over TCP for Pitwall?</b> <code>[MOTORSPORT NETWORKING]</code> <code>Pitwall</code></summary>

<br/>

```ini
[CONTEXT]   60Hz telemetry = 16.6ms per packet window. Forza sends continuous physics data that expires immediately.
[TRADEOFF]  TCP retransmissions add 3-12ms of synthetic latency. A retransmitted stale frame is worse than no frame at all.
[DECISION]  Raw UDP socket with zero-copy struct.unpack(). Drop stale packets immediately, never buffer backlog.
[RESULT]    Zero synthetic latency at 60fps. Sub-150ms end-to-end voice callout loop.
```

</details>

<details>
<summary><b>#002 // Random Forest over Deep Neural Nets for tire degradation?</b> <code>[MOTORSPORT ML]</code> <code>Apex AI</code></summary>

<br/>

```ini
[CONTEXT]   F1 Pirelli tire wear accelerates non-linearly due to thermal degradation and dirty air vortex shedding.
[TRADEOFF]  Linear regression underfits the thermal drop-off cliff; deep neural networks overfit on sparse stint telemetry.
[DECISION]  Ensemble Random Forest Regressor trained on lap deltas, compound age, sector speeds, and surface temperatures.
[RESULT]    Robust R² prediction on pit-stop windows with zero GPU requirement for real-time race simulations.
```

</details>

<details>
<summary><b>#003 // Why local-first storage for MedAssist?</b> <code>[STORAGE &amp; PRIVACY]</code> <code>MedAssist AI</code></summary>

<br/>

```ini
[CONTEXT]   Medical prescriptions contain sensitive PII. Users frequently need access in clinics with spotty connectivity.
[TRADEOFF]  Cloud databases make multi-device syncing trivial, but introduce attack surfaces, compliance overhead, and latency.
[DECISION]  Client-side Tesseract OCR with an embedded offline-first SQLite database. Zero unencrypted network hops.
[RESULT]    100% offline access, instantaneous local queries, and complete zero-knowledge privacy guarantees.
```

</details>

<details>
<summary><b>#004 // Local VLM fallback for broken DOM selectors?</b> <code>[AUTOMATION]</code> <code>Blindfold</code></summary>

<br/>

```ini
[CONTEXT]   Dynamic SPAs, obfuscated CSS classes, and shadow DOMs break hardcoded XPath/CSS selectors unpredictably.
[TRADEOFF]  Heuristic fuzzy text-matching fails when UI layout labels change; cloud vision APIs are cost-prohibitive at scale.
[DECISION]  Viewport screenshot capture dispatched to an optimized local Vision-Language Model (VLM) for bounding box re-anchoring.
[RESULT]    94%+ self-healing recovery rate on broken DOM nodes without stopping production crawler runs.
```

</details>

<br/>

<div align="center">
  <img src="assets/divider.svg" alt="Separator" width="100%"/>
</div>

<br/>

---

## ■ 04 // TECHNICAL STACK MATRIX

<table>
  <tr>
    <td width="50%" valign="top">
      <h4>🏎️ MOTORSPORT &amp; LOW-LATENCY</h4>
      <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
      <img src="https://img.shields.io/badge/FastF1_API-E10600?style=flat-square&logo=formula1&logoColor=white"/>
      <img src="https://img.shields.io/badge/UDP_Sockets-22C55E?style=flat-square&logo=gnubash&logoColor=white"/>
      <img src="https://img.shields.io/badge/Forza_Telemetry-E10600?style=flat-square&logo=xbox&logoColor=white"/>
      <img src="https://img.shields.io/badge/WebSockets-010101?style=flat-square&logo=socketdotio&logoColor=white"/>
      <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>
      <img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white"/>
      <br/><br/>
      <sub>Binary struct unpacking, ring buffers, vehicle kinematics, friction circles, and live telemetry feeds.</sub>
    </td>
    <td width="50%" valign="top">
      <h4>🌐 WEB &amp; FRONTEND</h4>
      <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white"/>
      <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black"/>
      <img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white"/>
      <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white"/>
      <img src="https://img.shields.io/badge/HTML5_Canvas-E34F26?style=flat-square&logo=html5&logoColor=white"/>
      <br/><br/>
      <sub>High-density racing HUD dashboards, terminal-inspired design systems, and responsive SVG telemetry.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4>🧠 MACHINE LEARNING &amp; MOTORSPORT AI</h4>
      <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white"/>
      <img src="https://img.shields.io/badge/Random_Forest-22C55E?style=flat-square&logo=databricks&logoColor=white"/>
      <img src="https://img.shields.io/badge/Local_VLM-8B5CF6?style=flat-square&logo=huggingface&logoColor=white"/>
      <img src="https://img.shields.io/badge/Tesseract_OCR-5C6BC0?style=flat-square&logo=google&logoColor=white"/>
      <img src="https://img.shields.io/badge/Groq_API_(<150ms)-F05032?style=flat-square&logo=speedtest&logoColor=white"/>
      <img src="https://img.shields.io/badge/Gemini_API-4285F4?style=flat-square&logo=google&logoColor=white"/>
      <br/><br/>
      <sub>Tire wear regressors, delta sector modeling, streaming voice inference loops, and on-device vision.</sub>
    </td>
    <td width="50%" valign="top">
      <h4>💾 DATABASES &amp; AUTOMATION</h4>
      <img src="https://img.shields.io/badge/SQLite_(Local--First)-003B57?style=flat-square&logo=sqlite&logoColor=white"/>
      <img src="https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white"/>
      <img src="https://img.shields.io/badge/Headless_Scraping-333333?style=flat-square&logo=googlechrome&logoColor=white"/>
      <img src="https://img.shields.io/badge/Bright_Data-FF6B00?style=flat-square&logo=databricks&logoColor=white"/>
      <img src="https://img.shields.io/badge/Git_&_GitHub-F05032?style=flat-square&logo=git&logoColor=white"/>
      <br/><br/>
      <sub>Embedded offline relational storage, browser orchestration, and resilient self-healing crawlers.</sub>
    </td>
  </tr>
</table>

<br/>

---

## ■ 05 // MOTORSPORT & ENGINEERING MILESTONES

```
2024 ───────► [ENROLLMENT] B.Tech in Computer Science & Engineering
              St Mary's Engineering College, Deshmukhi · Focus: Protocols & Distributed Systems

2025 ───────► [SHIPPED] MedAssist AI
              Local-first health records with client-side OCR & offline SQLite engine

2026 ───────► [RESEARCH] Apex AI Motorsport Telemetry
              Non-linear tire degradation prediction using FastF1 API & Random Forest

2026 ───────► [SYSTEMS] Pitwall Sim Telemetry HUD
              60Hz UDP Forza telemetry parser with sub-150ms Groq LLM voice loop

2026 ───────► [HACKATHON & AUTOMATION] Watchdog & Blindfold
              Bright Data Web Scraping Hackathon + Autonomous VLM selector self-repair
```

<br/>

<div align="center">
  <img src="assets/divider.svg" alt="Separator" width="100%"/>
</div>

<br/>

---

## ■ 06 // TELEMETRY & GITHUB ACTIVITY

<div align="center">

  <!-- DYNAMIC CONTRIBUTION GRAPH SNAKE (AUTOMATED VIA GITHUB ACTION) -->
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/sathwik-e/sathwik-e/output/github-snake-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/sathwik-e/sathwik-e/output/github-snake.svg">
    <img alt="GitHub Contribution Grid Snake" src="https://raw.githubusercontent.com/sathwik-e/sathwik-e/output/github-snake-dark.svg" width="100%" />
  </picture>

  <br/><br/>

  <table border="0" cellspacing="0" cellpadding="0">
    <tr align="center">
      <td>
        <a href="https://github.com/sathwik-e">
          <img src="https://streak-stats.demolab.com/?user=sathwik-e&theme=dark&background=08090d&ring=22c55e&fire=4ade80&currStreakLabel=4ade80&border=1e293b&border_radius=6" alt="Sathwik's GitHub Streak" width="400"/>
        </a>
      </td>
      <td>
        <a href="https://github.com/sathwik-e">
          <img src="https://github-readme-stats-eight-theta.vercel.app/api?username=sathwik-e&show_icons=true&theme=dark&bg_color=08090d&title_color=4ade80&text_color=94a3b8&icon_color=22c55e&border_color=1e293b&border_radius=6" alt="Sathwik's GitHub Stats" width="400"/>
        </a>
      </td>
    </tr>
    <tr align="center">
      <td colspan="2">
        <br/>
        <a href="https://github.com/sathwik-e">
          <img src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=sathwik-e&layout=compact&theme=dark&bg_color=08090d&title_color=4ade80&text_color=94a3b8&border_color=1e293b&border_radius=6" alt="Top Languages" width="420"/>
        </a>
      </td>
    </tr>
  </table>

</div>

<br/>

---

## ■ 07 // TRANSMISSION TERMINAL // CONTACT

> Open for motorsport telemetry roles, low-latency simulation infrastructure, and real-time AI pipelines. Reach out with technical problems, timelines, or collaboration proposals.

```
┌── SECURE TRANSMISSION CHANNELS ────────────────────────────────────────────────────────┐
│                                                                                        │
│  DIRECT EMAIL:      sathwik.elaprolu@gmail.com                                         │
│  PORTFOLIO HUD:     https://sathwik-e-portfolio.vercel.app                             │
│  LINKEDIN:          https://www.linkedin.com/in/sathwik-elaprolu                       │
│  GITHUB:            https://github.com/sathwik-e                                       │
│                                                                                        │
│  STATUS DISPATCH:   [● ONLINE] // OPEN FOR MOTORSPORT & SYSTEMS ROLES                  │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

<div align="center">

  <p>
    <a href="mailto:sathwik.elaprolu@gmail.com">
      <img src="https://img.shields.io/badge/DISPATCH_TRANSMISSION-sathwik.elaprolu@gmail.com-22c55e?style=for-the-badge&logo=gmail&logoColor=white&labelColor=08090d" alt="Send Email"/>
    </a>
    &nbsp;
    <a href="https://sathwik-e-portfolio.vercel.app" target="_blank">
      <img src="https://img.shields.io/badge/LAUNCH_PORTFOLIO_HUD-22c55e?style=for-the-badge&logo=vercel&logoColor=white&labelColor=08090d" alt="Launch Portfolio"/>
    </a>
  </p>

  <br/>

  <sub>
    DESIGNED WITH PRECISION // MOTORSPORT TELEMETRY &amp; LOW-LATENCY SYSTEMS // RUNTIME NOMINAL ■
  </sub>

</div>
