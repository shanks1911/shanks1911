<div align="center">
  <img src="./banner.svg" alt="Sanket Dangle — Quantitative Research · Market Microstructure" width="100%">
</div>

<br>

## Research statement

I'm interested in how electronic markets work beneath the charts.

My work is less about finding models that predict and more about designing experiments that can be trusted — point-in-time data, look-ahead guards, frozen holdouts, and evaluation honest enough to kill my own results. Most of what I know came from watching strategies that looked excellent fail once they were validated properly. That changed how I think about research more than any single technique did.

Currently moving from systematic equity research toward **electronic futures, market microstructure, and market making**.

<br>

## Currently investigating

Open questions I'm working through right now, not settled answers:

```
?  How should short-term fair value actually be defined —
   and is the midprice at t+h a defensible proxy for it?

?  Where does Stoikov's microprice break down, and can order
   flow information explain those specific failures?

?  Does queue imbalance carry information beyond
   top-of-book size imbalance?

?  How much of measured predictability survives block-bootstrap
   confidence intervals on overlapping observations?
```

<sub>Reading — Stoikov (microprice) · Cont, Kukanov & Stoikov (order flow imbalance) · Avellaneda & Stoikov (inventory-aware quoting) · Bouchaud, Bonart, Donier & Gould (*Trades, Quotes and Prices*)</sub>

<br>

## Research systems

I prefer building reusable research systems over isolated projects. Each follows the same cycle: **question → data → experiment → validation → what actually held up.**

---

### Market microstructure — fair value estimation

![Status](https://img.shields.io/badge/status-in_progress-64748b?style=flat-square)

> **Question.** Can order flow information produce a statistically superior estimate of short-term fair value in CME E-mini futures compared to classical microstructure estimators?

**Method.** Reproduce Stoikov's microprice from the literature first, then test where it degrades. Baselines: midprice, weighted midprice, microprice, OFI-linear. Evaluation by information coefficient with **block-bootstrap** confidence intervals (overlapping targets make the naive bootstrap invalid), stratified across volatility regimes and time of day.

**Status.** Experimental design frozen. Findings — including negative ones — will be published here.

<sub>`Databento` · `NumPy` · `statsmodels`</sub>

---

### Derivatives pricing & risk engine

[![Live demo](https://img.shields.io/badge/▸_Live_demo-2563eb?style=flat-square)](https://huggingface.co/spaces/shanks1911/derivatives-pricer)

> **Question.** How far can an analytical pricing engine be pushed before Monte Carlo becomes necessary — and what does that cost in wall-clock time?

Black-Scholes-Merton with full Greeks and implied-volatility root-solving, plus a Monte Carlo engine for path-dependent (Asian) options under GBM with a Mersenne Twister PRNG. Core simulation loop ported to C++ via `pybind11`.

```
100k paths × 252 steps        65.7s  →  1.66s        40× speedup
```

Plots the live implied-volatility smile from real options-chain data. Containerized and deployed.

<sub>`C++` · `pybind11` · `SciPy` · `Docker` · `Streamlit`</sub>

---

### Intraday pairs-trading simulator

[![Live demo](https://img.shields.io/badge/▸_Live_demo-2563eb?style=flat-square)](https://intradaystatarbtradingsimulator.streamlit.app/)

> **Question.** Do cointegrated relationships estimated on intraday bars stay stable long enough to trade?

Rolling-OLS hedge ratio estimation, z-score entry/exit signals on the spread, across 1m/5m/15m bars. Supports US and NSE ticker pairs with configurable lookback windows and thresholds — built to make the *instability* visible rather than hide it.

<sub>`statsmodels` · `Pandas` · `Streamlit`</sub>

---

### Agentic AI research companion

[![Repo](https://img.shields.io/badge/▸_Repo-1e293b?style=flat-square&logo=github&logoColor=white)](https://github.com/shanks1911/Agentic_AI_Project_Companion)

> **Question.** Can a multi-agent system meaningfully assist research workflows, or does orchestration overhead exceed the benefit?

Supervisor delegating to planning and research agents, with a stateful RAG agent over persistent ChromaDB for context-aware Q&A on uploaded PDFs. Peer-reviewed at Hinweis NCCT 2025.

<sub>`LangGraph` · `LangChain` · `ChromaDB` · `Gemini`</sub>

<details>
<summary><b>Earlier research systems</b> — AQI forecasting, urban heat island detection</summary>

<br>

**AQI forecasting & health advisory** — [repo](https://github.com/shanks1911/AQI_Health_Advisory)
End-to-end hourly air-quality forecasting over Google Air Quality API, OpenAQ, and OpenMeteo. Automated ingestion, model comparison, personalized advisory layer. Published at STAI 2026.

**Urban heat island detection** — [repo](https://github.com/shanks1911/UHI)
Satellite-based UHI intensity modeling across Mumbai using Google Earth Engine — land surface temperature, NDVI, rainfall, humidity, wind, impervious surface area. Published at IEEE ICCCNT 2025.

</details>

<br>

## Industry research

**Quantitative Research Intern** · Raise Financial Services (Stratzy) · Feb 2026 – Jul 2026

Systematic long-only NSE equity research under frozen holdout, walk-forward optimization, and survivorship-bias audit. Test window spans the 2020 COVID crash.

|                             | In-sample | Holdout  |
| :-------------------------- | :-------: | :------: |
| **Flagship strategy Sharpe**|  **1.69** | **1.96** |
| Strategies screened         |   250+    |     —    |
| Cleared deployable gate     |    25     |    25    |

| Regime overlay, quality-value base | Before |  After   |
| :--------------------------------- | :----: | :------: |
| **Max drawdown**                   |  −53%  | **−26%** |

<details>
<summary><b>Research infrastructure behind it</b></summary>

<br>

- **1,700+ factor alpha library** — LODR-sourced quality/value/growth composites alongside sector-relative and technical signals, scored via cross-sectional and time-series operators.
- **34-plugin risk-overlay framework** (6-hook contract) with 3-tier regime detection — rule-based rulesets, seeded GMM/HMM/KMeans clustering, and passive allocators over **24 market-state signals**.
- **Decoupled backtesting engine** over **2,476 NSE trading days** — full Indian transaction-cost and slippage modelling, point-in-time look-ahead-free execution (signal-T / fill-T+1) enforced at the config parser.
- **5,000+ backtests** via an agentic LLM loop mapping academic papers (arXiv, SSRN, OpenAlex) to auto-validated configs on a Dockerized AWS S3 pipeline, guarded by a deterministic config validator enforcing factor, unit, and warm-up contracts against silent look-ahead.

</details>

<br>

## Research principles

These aren't aspirations — they're the things that cost me results I wanted to keep.

**Point-in-time or nothing.** A signal that quietly uses tomorrow's data isn't a weak signal, it's a broken experiment.
**Frozen holdouts stay frozen.** If a threshold gets tuned against it once, it stops being out-of-sample forever.
**Report the negative result.** A method that fails under honest evaluation is a finding, not a failure to hide.
**Statistics before conclusions.** Overlapping windows, autocorrelation, and multiple comparisons break naive confidence intervals — most impressive-looking results die here.

<br>

## Publications

| | Venue | Code |
| :--- | :--- | :---: |
| UHI Intensity Prediction via Satellite-Based AI Modeling | IEEE ICCCNT, IIT Indore · Jul 2025 | [↗](https://github.com/shanks1911/UHI) |
| AQI Forecasting with Personalized Health Advisory | STAI, ACM Fremont Chapter · Apr 2026 | [↗](https://github.com/shanks1911/AQI_Health_Advisory) |
| Agentic AI Project Companion: A Framework for Consultative R&D | Hinweis NCCT · Oct 2025 | [↗](https://github.com/shanks1911/Agentic_AI_Project_Companion) |
| Quote-to-Image Generation via Llama 3.2 | Hinweis RTET · Dec 2024 | [↗](https://github.com/shanks1911/ImageGeneration) |

<br>

## Stack

**Languages** — Python · C++ · SQL
**Quantitative** — NumPy · Pandas · SciPy · statsmodels · scikit-learn
**Infrastructure** — Docker · AWS S3 · PyArrow/Parquet · PostgreSQL · Git

<br>

---

<div align="center">
<sub>Most strategies fail. Most models fail. That's exactly why quantitative research exists.</sub>
<br><br>
<a href="mailto:sanket.dangle@columbia.edu">Email</a> · <a href="https://linkedin.com/in/sanketdangle">LinkedIn</a> · <a href="https://github.com/shanks1911/shanks1911/blob/main/resume.pdf">Résumé</a>
<br><br>
<sub>Open to Summer 2027 quantitative research and trading internships.</sub>
</div>
