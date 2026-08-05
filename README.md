<div align="center">

<img src="hero.svg" alt="Sanket Dangle — M.S. Computer Science, Columbia University. Quantitative Research · Market Microstructure · Systematic Trading" width="100%">

[LinkedIn](https://www.linkedin.com/in/sanketdangle/) · [sanket1537@gmail.com](mailto:sanket1537@gmail.com) · Seeking Summer 2027 quantitative research internship

</div>

---

## Research Statement

I am interested in how electronic markets work beneath the charts. My work focuses on designing reproducible experiments, building research infrastructure, and validating quantitative ideas against real market data.

Most of what I know came from watching promising strategies fail under honest validation. That changed how I structure research: data integrity first, then evaluation, then models.

---

## Focus

| Area | Depth |
|:--|:--|
| Market Microstructure | `██████████` Researching |
| Financial Data Engineering | `█████████` Built |
| Derivatives & Volatility | `████████` Implementing |
| Statistical Learning | `███████` Applied |
| Market Making | `██████` Reading |

---

## Open Questions

| | |
|:--|:--|
| **Q1** | Can order flow imbalance improve on the microprice as a fair-value estimator? |
| **Q2** | Where does the microprice break down, and what regimes predict that failure? |
| **Q3** | How should fair value be defined when the book is thin and one-sided? |
| **Q4** | How much short-horizon return does queue imbalance actually explain? |

---

## Current Research

### Market Microstructure Research Platform

**Estimating fair value from high-frequency futures limit order books**

A research platform for constructing, testing and falsifying fair-value estimators on tick-level futures data — with the evaluation layer treated as the primary artifact, not an afterthought.

```
LOB snapshots → estimator → point-in-time replay → block bootstrap → significance test → accept / reject
```

| Estimators | Evaluation | Next |
|:--|:--|:--|
| Microprice | Point-in-time replay | Inventory-aware quoting |
| Weighted midprice | Walk-forward splits | Optimal execution |
| Order flow imbalance | Frozen holdout | Reinforcement learning |
| Queue imbalance | Significance testing | Low-latency C++ |

`Python` `NumPy` `Databento` `statsmodels` `C++`

---

## Research Systems

**Statistical Arbitrage Strategy Explorer**
Cointegration screening, spread construction and daily-horizon pair selection with configurable entry and exit bands.
[Live app](https://statarbstrategyexplorer.streamlit.app/)

**Intraday StatArb Trading Simulator**
Intraday simulation of mean-reverting pair trades, including position sizing, costs and realised PnL attribution.
[Live app](https://intradaystatarbtradingsimulator.streamlit.app/)

**Derivatives Pricing & Risk System**
Option pricing across analytic and numerical methods, with Greeks, scenario shocks and portfolio-level risk aggregation.
[Live app](https://huggingface.co/spaces/shanks1911/derivatives-pricer)

**AQI Forecasting & Health Advisory**
End-to-end hourly air-quality forecasting: automated collection, feature engineering, model benchmarking, deployment.
[Code](https://github.com/shanks1911/AQI_Health_Advisory) · [Live app](https://aqihealthadvisory.streamlit.app/)

**Urban Heat Island Detection**
Satellite-derived land surface temperature, NDVI and impervious-surface features clustered to locate heat islands across Mumbai.
[Code](https://github.com/shanks1911/UHI)

**Agentic Research Companion**
LangGraph supervisor coordinating planning and research agents over a persistent vector store with stateful sessions.
[Code](https://github.com/shanks1911/Agentic_AI_Project_Companion)

---

## Industry Research

### Raise Financial Services (Stratzy AI)

**Quantitative Research Intern** · February 2026 — July 2026

| 1,700+ | 250+ | 1000+ | 0 |
|:--:|:--:|:--:|:--:|
| financial datasets | raw fundamental & price feeds | strategies evaluated | look-ahead tolerated |

```
financial data → NLP preprocessing → factor engineering → strategy research
              → walk-forward validation → risk overlays → deployment
```

Built reusable research infrastructure rather than a single model: NLP preprocessing for corporate announcements, a modular factor library, a plugin-based risk-overlay framework, and point-in-time execution guarantees across the evaluation stack.

> Robust research starts with robust data.

**Research principles** — data before models · validation before optimization · reproducibility over complexity · honest negative results matter

---

## Timeline

| Year | | |
|:--|:--|:--|
| 2024 | Quote-to-Image Generation | Hinweis RTET |
| 2025 | Urban Heat Island Detection | IEEE ICCCNT |
| 2025 | Agentic Research Companion | Hinweis NCCT |
| 2026 | Quantitative Research Intern | Raise Financial (Stratzy AI) |
| 2026 | M.S. Computer Science | Columbia University |
| 2026 | Market Microstructure Research Platform | Flagship |

---

## Publications

| Paper | Venue |
|:--|:--|
| Urban Heat Island Prediction via Satellite-based AI Modeling | IEEE ICCCNT 2025 |
| AQI Forecasting with Personalized Health Advisory | STAI 2026 |
| Agentic AI Project Companion | Hinweis NCCT 2025 |
| Quote-to-Image Generation via Llama 3.2 | Hinweis RTET 2024 |

---

## Stack

| Languages | Libraries | Infrastructure |
|:--|:--|:--|
| Python · C++ · SQL | NumPy · Pandas · SciPy · statsmodels · PyTorch | Docker · Git · Postgres · AWS |

---

<div align="center">

**Most strategies fail. Most models fail. That is precisely why quantitative research exists.**

[sanket1537@gmail.com](mailto:sanket1537@gmail.com) · [LinkedIn](https://www.linkedin.com/in/sanketdangle/)

</div>
