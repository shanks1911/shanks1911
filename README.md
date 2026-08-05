# Sanket Dangle

**Quantitative research · market microstructure · statistical validation**

M.S. Computer Science, Columbia University · Previously quantitative research at Raise Financial Services (Stratzy)

[Email](mailto:sanket.dangle@columbia.edu) · [LinkedIn](https://linkedin.com/in/sanketdangle) · [Résumé](https://github.com/shanks1911/shanks1911/blob/main/resume.pdf)

---

I work on systematic strategy research and market microstructure — mostly the unglamorous parts: point-in-time data, look-ahead guards, out-of-sample discipline, and finding out which results survive honest evaluation. Most of what I've learned came from watching promising backtests fall apart under scrutiny.

Currently reading into fair value estimation and order flow in electronic futures markets.

---

## Selected work

### Derivatives Pricing & Risk Engine — [live demo](https://huggingface.co/spaces/shanks1911/derivatives-pricer)
Black-Scholes-Merton pricing with full Greeks and implied-volatility root-solving, plus a Monte Carlo engine for path-dependent (Asian) options under GBM with a Mersenne Twister PRNG. Core simulation loop ported to C++ via `pybind11` for a **40× speedup** — 65.7s → 1.66s on 100k paths × 252 steps. Plots the live implied-volatility smile from real options-chain data; containerized and deployed.

`C++` `pybind11` `SciPy` `Docker` `Streamlit`

### Intraday Pairs-Trading Simulator — [live demo](https://intradaystatarbtradingsimulator.streamlit.app/)
Statistical-arbitrage research tool: rolling-OLS hedge ratio estimation, z-score entry/exit signals on the cointegrated spread, across 1m/5m/15m bars. Supports both US and NSE ticker pairs with configurable lookback windows and thresholds.

`statsmodels` `Pandas` `Streamlit`

### Market Microstructure Research *(in progress — started Aug 2026)*
A study of short-term fair value estimation in CME E-mini futures: reproducing Stoikov's microprice from the literature, then testing where it degrades and whether order flow information explains those failures. Evaluation by information coefficient with block-bootstrap confidence intervals, stratified across volatility regimes.

Design notes and results will land here as they're produced.

### Agentic AI Research Companion — [repo](https://github.com/shanks1911/Agentic_AI_Project_Companion)
Multi-agent system (LangGraph + Gemini) with a supervisor delegating to planning and research agents, plus a stateful RAG agent over persistent ChromaDB for context-aware Q&A on user-uploaded PDFs. Presented as a peer-reviewed paper at Hinweis NCCT 2025.

`LangGraph` `LangChain` `ChromaDB` `Gemini`

### AQI Forecasting & Health Advisory — [repo](https://github.com/shanks1911/AQI_Health_Advisory)
End-to-end hourly air-quality forecasting pipeline over Google Air Quality API, OpenAQ, and OpenMeteo data, with automated ingestion, multiple model comparison, and a personalized advisory layer. Published at STAI 2026 (ACM Fremont Chapter).

### Urban Heat Island Detection — [repo](https://github.com/shanks1911/UHI)
Satellite-based UHI intensity modeling across Mumbai using Google Earth Engine — land surface temperature, NDVI, rainfall, humidity, wind, and impervious surface area. Published at IEEE ICCCNT 2025 (IIT Indore).

---

## Experience

**Quantitative Research Intern — Raise Financial Services (Stratzy)** · Feb 2026 – Jul 2026

Systematic long-only NSE equity research under strict out-of-sample discipline — frozen holdout, walk-forward optimization, survivorship-bias auditing.

- Screened **250+ strategies** to a Sharpe > 1.0 / <30% drawdown bar; **25** cleared the full in-sample *and* holdout deployable gate. Flagship strategy: **1.71 overall Sharpe (1.69 in-sample / 1.96 holdout)** across a window spanning the 2020 COVID crash.
- Built a **1,700+ factor** alpha library — LODR-sourced quality/value/growth composites alongside sector-relative and technical signals, scored via cross-sectional and time-series operators.
- Layered a **34-plugin** risk-overlay framework (6-hook contract) with 3-tier regime detection — rule-based rulesets, seeded GMM/HMM/KMeans clustering, and passive allocators over **24 market-state signals**. On a quality-value base strategy, breadth-driven exposure allocation roughly **halved max drawdown (−53% → −26%)**.
- Engineered a decoupled backtesting engine over **2,476 NSE trading days** with full Indian transaction-cost and slippage modelling, and point-in-time, look-ahead-free execution (signal-T / fill-T+1) enforced at the config parser.
- Scaled research to **5,000+ backtests** via an agentic LLM loop mapping academic papers (arXiv, SSRN, OpenAlex) to auto-validated configs on a Dockerized AWS S3 pipeline, guarded by a deterministic config validator enforcing factor/unit/warm-up contracts against silent look-ahead.

---

## Publications

- **"UHI Intensity Prediction via Satellite-Based AI Modeling"** — IEEE ICCCNT, IIT Indore, Jul 2025 · [code](https://github.com/shanks1911/UHI)
- **"AQI Forecasting with Personalized Health Advisory"** — STAI, ACM Fremont Chapter, Apr 2026 · [code](https://github.com/shanks1911/AQI_Health_Advisory)
- **"Quote-to-Image Generation via Llama 3.2"** — Hinweis RTET, Dec 2024 · [code](https://github.com/shanks1911/ImageGeneration)
- **"Agentic AI Project Companion: A Framework for Consultative, Adaptive and Proactive R&D"** — Hinweis NCCT, Oct 2025 · [code](https://github.com/shanks1911/Agentic_AI_Project_Companion)

---

## Stack

**Languages** Python · C++ · SQL
**Quantitative** NumPy · Pandas · SciPy · statsmodels · scikit-learn
**Infrastructure** Docker · AWS S3 · PyArrow/Parquet · PostgreSQL · Git

---

<sub>Open to Summer 2027 quantitative research and trading internships.</sub>
