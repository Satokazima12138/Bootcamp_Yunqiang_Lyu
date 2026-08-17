
# Predicting Short-Term Downside Risk in Bitcoin Using Market and Volatility Indicators

**Stage:** Problem Framing & Scoping (Stage 01)

## Problem Statement

Bitcoin is highly volatile and can experience sharp price declines over short periods. This project aims to investigate whether market and volatility indicators can be used to identify periods of elevated short-term downside risk in Bitcoin.

The purpose is to develop a simple and interpretable risk-assessment framework that can help market participants recognize changing risk conditions and make more informed decisions about portfolio exposure and risk management.

## Stakeholder & User

The primary stakeholder is a crypto portfolio manager or trader who is responsible for making portfolio allocation and risk-management decisions.

The main user of the output is a quantitative researcher or risk analyst who monitors market conditions, evaluates the risk signal, and communicates the results to the decision maker. The analysis would be used on a regular basis to assess short-term market risk before adjusting portfolio exposure.

## Useful Answer & Decision

This is primarily a predictive problem. A useful answer would be a quantitative risk indicator that estimates whether Bitcoin is currently in a low, moderate, or high short-term downside-risk environment.

The output could be presented as a risk score or probability measure, supported by a simple visualization. A portfolio manager or trader could use the signal to decide whether to maintain current exposure, reduce position size, or apply additional risk-management measures.

## Assumptions & Constraints

- Historical Bitcoin price, volume, and volatility-related data are available and sufficiently reliable for analysis.
- Market and volatility indicators contain useful information related to short-term downside risk.
- The project focuses primarily on market-based indicators and does not attempt to incorporate every macroeconomic, regulatory, or blockchain-specific factor.
- Results may depend on the selected time horizon, indicators, and definition of downside risk.
- Data quality, API availability, and computational resources may constrain the scope of the analysis.

## Known Unknowns / Risks

- It is uncertain which market and volatility indicators are most informative for predicting short-term Bitcoin downside risk.
- The relationship between indicators and future downside risk may change across different market regimes.
- Extreme market events may be difficult to predict because they can be driven by unexpected news, regulation, or liquidity shocks.
- Historical relationships may not generalize well to future market conditions.
- The project will evaluate these risks by comparing indicator behavior across different periods and monitoring predictive performance.

## Lifecycle Mapping

- Define a clear Bitcoin downside-risk prediction problem → Problem Framing & Scoping (Stage 01) → Project scoping statement
- Identify the decision maker and end user → Problem Framing & Scoping (Stage 01) → Stakeholder and user definition
- Define what constitutes a useful prediction → Problem Framing & Scoping (Stage 01) → Predictive objective, risk metric, and decision framework
- Identify assumptions, constraints, and uncertainties → Problem Framing & Scoping (Stage 01) → Documented project risks and assumptions

## Repo Plan

- `data/raw/` — original market data obtained from external sources
- `data/processed/` — cleaned and transformed datasets
- `src/` — reusable Python functions and utilities
- `notebooks/` — exploratory analysis and modeling notebooks
- `docs/` — stakeholder-facing documentation and project notes
- `reports/` — generated results, figures, and summaries
- `model/` — model outputs or saved model-related files

The repository will be updated throughout the bootcamp as new stages of the project are completed.


## Stakeholder Brief

**Audience:** Crypto Portfolio Manager / Trader  
**Cadence:** Daily or as needed during periods of elevated market volatility  
**Decision Supported:** Maintain exposure, reduce position size, or apply additional risk-management measures

### Context

Bitcoin can experience rapid and substantial price declines over short periods, making timely risk assessment important for portfolio management. This project focuses on identifying periods of elevated short-term downside risk using observable market and volatility indicators.

The goal is to provide a simple and interpretable signal that helps decision makers recognize changing market conditions before adjusting portfolio exposure.

### What You'll Receive

- A quantitative short-term downside-risk signal for Bitcoin
- A classification of market conditions as low, moderate, or high downside risk
- A risk score or probability measure supported by a simple visualization
- A plain-language summary of the main assumptions, limitations, and interpretation of the signal

### Assumptions & Constraints

- Historical Bitcoin price, volume, and volatility-related data are sufficiently reliable for analysis.
- Market and volatility indicators may contain useful information about short-term downside risk.
- The analysis does not incorporate every macroeconomic, regulatory, or blockchain-specific factor.
- Results may vary depending on the selected time horizon, indicators, and definition of downside risk.
- Data quality and API availability may constrain the scope of the analysis.

# Stage 02 — Tooling Setup

This homework practices setting up a reproducible Python project environment. It includes creating a project folder structure, configuring environment variables with `.env`, implementing a reusable configuration helper, verifying the Python environment and NumPy in Jupyter, and managing dependencies with `requirements.txt`. The project also follows Git and GitHub best practices, including keeping sensitive configuration files such as `.env` out of version control.


# Stage 05 - Data Storage

### Folder Structure

- `data/raw/` stores raw datasets in CSV format.
- `data/processed/` stores processed datasets in Parquet format.

### Storage Formats

CSV is used for raw data because it is simple, human-readable, and widely supported.

Parquet is used for processed data because it preserves data types more reliably, supports compression, and is more efficient for analytical workflows.

### Environment-Driven Paths

Storage paths are configured through the `.env` file:

```text
DATA_DIR_RAW=data/raw
DATA_DIR_PROCESSED=data/processed