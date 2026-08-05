<div align="center">

# Sanket Dangle

**Quantitative research · Market microstructure · Statistical validation**

<sub>M.S. Computer Science @ Columbia University (incoming) · ex-Quant Research @ Raise Financial Services</sub>

<br>

[![Email](https://img.shields.io/badge/Email-1e293b?style=flat-square&logo=gmail&logoColor=white)](mailto:sanket.dangle@columbia.edu)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-1e293b?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/sanketdangle)
[![Résumé](https://img.shields.io/badge/Résumé-1e293b?style=flat-square&logo=readthedocs&logoColor=white)](https://github.com/shanks1911/shanks1911/blob/main/resume.pdf)

</div>

---

I work on systematic strategy research and market microstructure — mostly the unglamorous parts. Point-in-time data. Look-ahead guards. Out-of-sample discipline. Finding out which results survive honest evaluation and which quietly fall apart.

Most of what I know came from watching promising backtests die under scrutiny.

> **Now** — Reading into fair value estimation and order flow in electronic futures markets. Reproducing Stoikov's microprice before trying to improve on it.

<br>

## Selected work

### Derivatives Pricing & Risk Engine

[![Live demo](https://img.shields.io/badge/▸_Live_demo-2563eb?style=flat-square)](https://huggingface.co/spaces/shanks1911/derivatives-pricer)

Black-Scholes-Merton pricing with full Greeks and implied-volatility root-solving, plus a Monte Carlo engine for path-dependent (Asian) options under GBM with a Mersenne Twister PRNG. Core simulation loop ported to C++ via `pybind11`.

```
100k paths × 252 steps      65.7s  →  1.66s        40× speedup
```

Plots the live implied-volatility smile from real options-chain data. Containerized and deployed.

<sub>`C++` · `pybind11` · `SciPy` · `Docker` · `Streamlit`</sub>

---

### Intraday Pairs-Trading Simulator

[![Live demo](https://img.shields.io/badge/▸_Live_demo-2563eb?style=flat-square)](https://intradaystatarbtradingsimulator.streamlit.app/)

Statistical-arbitrage research tool — rolling-OLS hedge ratio estimation, z-score entry/exit signals on the cointegrated spread, across 1m/5m/15m bars. Supports US and NSE ticker pairs with configurable lookback windows and thresholds.

<sub>`statsmodels` · `Pandas` · `Streamlit`</sub>

---

### Market Microstructure Research

![Status](https://img.shields.io/badge/status-in_progress-64748b?style=flat-square)

Short-term fair value estimation in CME E-mini futures. Reproducing Stoikov's microprice from the literature, then testing **where it degrades** and whether order flow information explains those failures.

Evaluated by information coefficient with block-bootstrap confidence intervals, stratified across volatility regimes. Design notes and results land here as they're produced.

<sub>`Databento` · `NumPy` · `statsmodels`</sub>

---

### Agentic AI Research Companion

[![Repo](https://img.shields.io/badge/▸_Repo-1e293b?style=flat-square&logo=github&logoColor=white)](https://github.com/shanks1911/Agentic_AI_Project_Companion)

Multi-agent system with a supervisor delegating to planning and research agents, plus a stateful RAG agent over persistent ChromaDB for context-aware Q&A on uploaded PDFs. Presented as a peer-reviewed paper at Hinweis NCCT 2025.

<sub>`LangGraph` · `LangChain` · `ChromaDB` · `Gemini`</sub>

<br>

<details>
<summary><b>More projects</b> — AQI forecasting, urban heat island detection</summary>

<br>

**AQI Forecasting & Health Advisory** — [repo](https://github.com/shanks1911/AQI_Health_Advisory)
End-to-end hourly air-quality forecasting over Google Air Quality API, OpenAQ, and OpenMeteo, with automated ingestion, model comparison, and a personalized advisory layer. Published at STAI 2026.

**Urban Heat Island Detection** — [repo](https://github.com/shanks1911/UHI)
Satellite-based UHI intensity modeling across Mumbai using Google Earth Engine — land surface temperature, NDVI, rainfall, humidity, wind, impervious surface area. Published at IEEE ICCCNT 2025.

</details>

<br>

## Research results — Raise Financial Services

<sub>Quantitative Research Intern · Feb 2026 – Jul 2026 · Systematic long-only NSE equity</sub>

Frozen holdout, walk-forward optimization, survivorship-bias audit. Test window spans the 2020 COVID crash.

|                         | In-sample | Holdout  |
| :---------------------- | :-------: | :------: |
| **Flagship Sharpe**     | **1.69**  | **1.96** |
| Strategies screened     |   250+    |     —    |
| Cleared deployable gate |    25     |    25    |

| Regime overlay impact | Before | After |
| :-------------------- | :----: | :---: |
| **Max drawdown**      | −53%   | **−26%** |

<details>
<summary><b>How it was built</b></summary>

<br>

- **1,700+ factor alpha library** — LODR-sourced quality/value/growth composites alongside sector-relative and technical signals, scored via cross-sectional and time-series operators.
- **34-plugin risk-overlay framework** (6-hook contract) with 3-tier regime detection — rule-based rulesets, seeded GMM/HMM/KMeans clustering, and passive allocators over **24 market-state signals**.
- **Decoupled backtesting engine** over **2,476 NSE trading days** — full Indian transaction-cost and slippage modelling, point-in-time look-ahead-free execution (signal-T / fill-T+1) enforced at the config parser.
- **5,000+ backtests** scaled via an agentic LLM loop mapping academic papers (arXiv, SSRN, OpenAlex) to auto-validated configs on a Dockerized AWS S3 pipeline, guarded by a deterministic config validator enforcing factor/unit/warm-up contracts against silent look-ahead.

</details>

<br>

## Publications

| Paper | Venue | Code |
| :---- | :---- | :--- |
| UHI Intensity Prediction via Satellite-Based AI Modeling | IEEE ICCCNT, IIT Indore · Jul 2025 | [↗](https://github.com/shanks1911/UHI) |
| AQI Forecasting with Personalized Health Advisory | STAI, ACM Fremont Chapter · Apr 2026 | [↗](https://github.com/shanks1911/AQI_Health_Advisory) |
| Agentic AI Project Companion: A Framework for Consultative R&D | Hinweis NCCT · Oct 2025 | [↗](https://github.com/shanks1911/Agentic_AI_Project_Companion) |
| Quote-to-Image Generation via Llama 3.2 | Hinweis RTET · Dec 2024 | [↗](https://github.com/shanks1911/ImageGeneration) |

<br>

## Stack

![Python](https://img.shields.io/badge/Python-1e293b?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-1e293b?style=flat-square&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-1e293b?style=flat-square&logo=postgresql&logoColor=white)
&nbsp;
![NumPy](https://img.shields.io/badge/NumPy-475569?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-475569?style=flat-square&logo=pandas&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-475569?style=flat-square&logo=scipy&logoColor=white)
![statsmodels](https://img.shields.io/badge/statsmodels-475569?style=flat-square)
![scikit-learn](https://img.shields.io/badge/scikit--learn-475569?style=flat-square&logo=scikitlearn&logoColor=white)
&nbsp;
![Docker](https://img.shields.io/badge/Docker-64748b?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_S3-64748b?style=flat-square&logo=amazons3&logoColor=white)
![Parquet](https://img.shields.io/badge/PyArrow-64748b?style=flat-square&logo=apacheparquet&logoColor=white)
![Postgres](https://img.shields.io/badge/PostgreSQL-64748b?style=flat-square&logo=postgresql&logoColor=white)

<br>

---

<div align="center">
<sub>Open to Summer 2027 quantitative research and trading internships.</sub>
</div>
