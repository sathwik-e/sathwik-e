<div align="center">

  <!-- 01 // UNIFIED MASTER ARCHITECTURE BANNER (WITH CONTINUOUS GERSTNER OCEAN WAVE GRID) -->
  <a href="https://sathwik-e-portfolio.vercel.app" target="_blank">
    <img src="assets/hero-banner.svg" alt="Sathwik Elaprolu // Systems & AI Engineer" width="100%"/>
  </a>

  <br/><br/>

  <!-- ACTION PILLS & DIRECT CONNECTORS -->
  <p align="center">
    <a href="https://sathwik-e-portfolio.vercel.app" target="_blank">
      <img src="https://img.shields.io/badge/PORTFOLIO_HUD-ONLINE-52e3a1?style=flat-square&logo=vercel&logoColor=white&labelColor=0a0b0e" alt="Launch Portfolio HUD"/>
    </a>
    &nbsp;
    <a href="mailto:sathwik.elaprolu@gmail.com">
      <img src="https://img.shields.io/badge/TRANSMIT_EMAIL-sathwik.elaprolu@gmail.com-38bdf8?style=flat-square&logo=gmail&logoColor=white&labelColor=0a0b0e" alt="Send Email"/>
    </a>
    &nbsp;
    <a href="https://www.linkedin.com/in/sathwik-elaprolu" target="_blank">
      <img src="https://img.shields.io/badge/LINKEDIN-sathwik--elaprolu-a78bfa?style=flat-square&logo=linkedin&logoColor=white&labelColor=0a0b0e" alt="LinkedIn"/>
    </a>
  </p>

  <!-- LIVE TELEMETRY STREAM -->
  <p align="center">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=2000&pause=800&color=52E3A1&background=07090E00&center=true&vCenter=true&width=780&height=28&lines=%3E+Ingesting+60Hz+Forza+Motorsport+raw+binary+UDP+telemetry...;%3E+Apex+AI%3A+Predicting+non-linear+Pirelli+F1+tire+degradation...;%3E+Pitwall%3A+Sub-150ms+Groq+voice+AI+crew+chief+radio+dispatch...;%3E+Explore+live+interactive+HUD+blueprints+on+sathwik-e-portfolio.vercel.app..." alt="Live Telemetry Stream"/>
  </p>

</div>

<br/>

### 01 // PRODUCTION SYSTEMS &amp; ARCHITECTURE

<table>
  <tr>
    <td width="50%" valign="top">
      <h4>🏎️ Pitwall — Real-Time Sim Telemetry</h4>
      <p>
        <code>60Hz UDP</code> &nbsp; <code>Voice AI &lt;150ms</code> &nbsp; <code>WebSockets</code>
      </p>
      <p style="font-size: 13.5px; color: #8b949e;">
        High-frequency telemetry engine for sim racing. Ingests raw UDP datagrams at 60Hz, executes zero-copy binary unpacking (<code>struct.unpack</code>), and dispatches race strategy via voice AI crew chief in &lt;150ms.
      </p>
      <p style="font-size: 12px;">
        <b>Stack:</b> Python · Flask · WebSockets · Groq LLM
      </p>
      <p>
        <a href="https://sathwik-e-portfolio.vercel.app" target="_blank"><b>Live HUD Demo ↗</b></a> &nbsp;|&nbsp; <a href="https://github.com/sathwik-e/pitwall" target="_blank"><b>Repository →</b></a>
      </p>
    </td>
    <td width="50%" valign="top">
      <h4>📈 Apex AI — F1 Tire Degradation ML</h4>
      <p>
        <code>FastF1 API</code> &nbsp; <code>Random Forest</code> &nbsp; <code>Scikit-Learn</code>
      </p>
      <p style="font-size: 13.5px; color: #8b949e;">
        Formula 1 analytics pipeline. Ingests telemetry streams via FastF1 API and predicts non-linear Pirelli tire compound thermal degradation and optimal pit windows using an ensemble Random Forest regressor.
      </p>
      <p style="font-size: 12px;">
        <b>Stack:</b> Python · FastF1 · Scikit-Learn · Pandas
      </p>
      <p>
        <a href="https://sathwik-e-portfolio.vercel.app" target="_blank"><b>Live HUD Demo ↗</b></a> &nbsp;|&nbsp; <a href="https://github.com/sathwik-e/apex-ai" target="_blank"><b>Repository →</b></a>
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h4>🩺 MedAssist AI — Local-First OCR &amp; SQLite</h4>
      <p>
        <code>Tesseract OCR</code> &nbsp; <code>Local SQLite</code> &nbsp; <code>Gemini API</code>
      </p>
      <p style="font-size: 13.5px; color: #8b949e;">
        100% on-device prescription entity parser and drug interaction safety check with zero cloud leakage, storing normalized medication schedules directly into client SQLite.
      </p>
      <p style="font-size: 12px;">
        <b>Stack:</b> Next.js · TypeScript · SQLite · Gemini API
      </p>
      <p>
        <a href="https://sathwik-e-portfolio.vercel.app" target="_blank"><b>Live HUD Demo ↗</b></a> &nbsp;|&nbsp; <a href="https://github.com/sathwik-e/MedAssist-AI" target="_blank"><b>Repository →</b></a>
      </p>
    </td>
    <td width="50%" valign="top">
      <h4>🛡️ Watchdog — VLM Self-Healing Scraper</h4>
      <p>
        <code>Playwright</code> &nbsp; <code>Local VLM</code> &nbsp; <code>Auto-Repair</code>
      </p>
      <p style="font-size: 13.5px; color: #8b949e;">
        Self-repairing web extraction engine recovering 85% of broken storefront queries autonomously via vision-language models when DOM class names obfuscate or shift.
      </p>
      <p style="font-size: 12px;">
        <b>Stack:</b> Python · Playwright · VLM · Bright Data
      </p>
      <p>
        <a href="https://sathwik-e-portfolio.vercel.app" target="_blank"><b>Live HUD Demo ↗</b></a> &nbsp;|&nbsp; <a href="https://github.com/sathwik-e/brightdata-watchdog" target="_blank"><b>Repository →</b></a>
      </p>
    </td>
  </tr>
</table>

<details open>
  <summary><b>📊 Pitwall Telemetry HUD Architecture View ▾</b></summary>
  <div align="center" style="margin-top: 10px;">
    <img src="assets/motorsport-telemetry-hud.svg" alt="Pitwall Simulation Telemetry HUD" width="100%"/>
  </div>
</details>

<br/>

### 02 // GITHUB ACTIVITY &amp; TELEMETRY

<div align="center">

  <!-- DYNAMIC CONTRIBUTION GRAPH SNAKE -->
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/sathwik-e/sathwik-e/output/github-snake-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/sathwik-e/sathwik-e/output/github-snake.svg">
    <img alt="GitHub Contribution Grid Snake" src="https://raw.githubusercontent.com/sathwik-e/sathwik-e/output/github-snake-dark.svg" width="100%" />
  </picture>

  <p align="center" style="margin-top: 14px; margin-bottom: 18px;">
    <a href="https://github.com/sathwik-e">
      <img src="https://streak-stats.demolab.com/?user=sathwik-e&theme=dark&background=0a0b0e&ring=22c55e&fire=22c55e&currStreakLabel=22c55e&currStreakNum=22c55e&sideNums=f0f6fc&sideLabels=8b949e&dates=8b949e&border=21262d&border_radius=6" alt="Sathwik's GitHub Streak" width="410"/>
    </a>
    &nbsp;
    <a href="https://github.com/sathwik-e">
      <img src="https://github-readme-stats-eight-theta.vercel.app/api?username=sathwik-e&show_icons=true&theme=dark&bg_color=0a0b0e&title_color=22c55e&text_color=8b949e&icon_color=22c55e&border_color=21262d&border_radius=6" alt="Sathwik's GitHub Stats" width="410"/>
    </a>
  </p>

  <br/>

  <sub style="color: #8b949e;">
    Sathwik Elaprolu · Systems &amp; AI Engineer · Hyderabad, India ■
  </sub>

</div>
