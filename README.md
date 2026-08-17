# Bootcamp Repository

This repository contains my completed coursework and project setup for Bootcamp Stages 00–05.

The current project theme is:

**Predicting Short-Term Downside Risk in Bitcoin Using Market and Volatility Indicators**

---

## Repository Structure

- `homework/` — completed homework submissions for each stage
- `project/` — project-related work developed throughout the bootcamp
- `class_materials/` — local course materials; excluded from GitHub
- `.gitignore` — excludes local class materials, environment files, Python cache files, and other unnecessary files

Each homework stage is stored in its own subfolder under `homework/`.

---

## Stage 00 — Pre-Class Setup

Stage 00 focused on preparing the development environment required for the bootcamp.

Completed setup included:

- Installed and configured Python through Conda
- Created a dedicated Python environment
- Installed JupyterLab and required Python packages
- Installed and configured Git
- Created and cloned the GitHub repository
- Created the repository folder structure
- Configured `.gitignore`
- Created and tested a basic Jupyter notebook
- Installed Visual Studio Code

The Stage 00 notebook is stored under:

`homework/homework0/`

---

## Stage 01 — Problem Framing & Scoping

### Project Title

**Predicting Short-Term Downside Risk in Bitcoin Using Market and Volatility Indicators**

### Problem Statement

Bitcoin is highly volatile and can experience sharp price declines over short periods. This project aims to investigate whether market and volatility indicators can be used to identify periods of elevated short-term downside risk in Bitcoin.

The purpose is to develop a simple and interpretable risk-assessment framework that can help market participants recognize changing risk conditions and make more informed decisions about portfolio exposure and risk management.

### Stakeholder & User

The primary stakeholder is a crypto portfolio manager or trader who is responsible for making portfolio allocation and risk-management decisions.

The main user of the output is a quantitative researcher or risk analyst who monitors market conditions, evaluates the risk signal, and communicates the results to the decision maker.

The analysis would be used on a regular basis to assess short-term market risk before adjusting portfolio exposure.

### Useful Answer & Decision

This is primarily a predictive problem.

A useful answer would be a quantitative risk indicator that estimates whether Bitcoin is currently in a:

- low downside-risk environment
- moderate downside-risk environment
- high downside-risk environment

The output could be presented as a risk score or probability measure supported by a simple visualization.

A portfolio manager or trader could use the signal to decide whether to:

- maintain current exposure
- reduce position size
- apply additional risk-management measures

### Assumptions & Constraints

- Historical Bitcoin price, volume, and volatility-related data are sufficiently reliable for analysis.
- Market and volatility indicators may contain useful information related to short-term downside risk.
- The project focuses primarily on market-based indicators.
- The analysis does not incorporate every macroeconomic, regulatory, or blockchain-specific factor.
- Results may depend on the selected time horizon, indicators, and definition of downside risk.
- Data quality, API availability, and computational resources may constrain the analysis.

### Known Unknowns / Risks

- It is uncertain which indicators are most informative for predicting short-term Bitcoin downside risk.
- Relationships between indicators and downside risk may change across market regimes.
- Extreme market events may be driven by unexpected news, regulation, or liquidity shocks.
- Historical relationships may not generalize well to future conditions.
- Predictive performance should therefore be monitored across different market periods.

### Lifecycle Mapping

- Define the Bitcoin downside-risk problem → Problem Framing & Scoping → Project scoping statement
- Identify stakeholder and end user → Problem Framing & Scoping → Stakeholder definition
- Define a useful prediction → Problem Framing & Scoping → Risk metric and decision framework
- Identify assumptions and risks → Problem Framing & Scoping → Documented constraints and uncertainties

### Stakeholder Brief

**Audience:** Crypto Portfolio Manager / Trader  
**Cadence:** Daily or during periods of elevated volatility  
**Decision Supported:** Maintain exposure, reduce position size, or apply additional risk-management measures

The intended deliverable is a simple quantitative short-term downside-risk signal supported by a visualization and a plain-language interpretation of assumptions and limitations.

Stage 01 files are stored under:

`homework/homework01/`

---

## Stage 02 — Tooling Setup

Stage 02 focused on building a reproducible Python project environment and practicing project configuration.

The work included:

- verifying the Python interpreter and version
- configuring environment variables through `.env`
- using dummy API values for safe configuration testing
- implementing a reusable configuration helper
- verifying that environment variables can be loaded correctly
- creating and testing NumPy arrays in Jupyter
- creating the project folder structure
- generating `requirements.txt`
- following Git and GitHub best practices
- ensuring `.env` is excluded from version control

The configuration helper includes functions such as:

```python
load_env()
get_key()
```

Sensitive configuration is stored locally in `.env`, while `.env.example` is included in the repository as a public template.

Stage 02 files are stored under:

`homework/homework02/`

---

## Stage 03 — Python Fundamentals

Stage 03 focused on applying core Python, NumPy, and pandas concepts to a dataset.

The work included:

- creating NumPy arrays
- performing elementwise operations
- comparing Python loops with NumPy vectorized execution
- loading a CSV dataset using pandas
- inspecting data with `.head()` and `.info()`
- calculating descriptive statistics with `.describe()`
- performing category-based aggregation with `.groupby()`
- saving summary statistics to `data/processed/`
- creating reusable utility functions

A major concept demonstrated in this stage was the performance difference between:

```text
Python loops
vs.
NumPy vectorization
```

Vectorized operations are generally more efficient for numerical workflows.

The dataset workflow followed:

```text
Load Data
    ↓
Inspect Data
    ↓
Summarize Data
    ↓
Group and Aggregate
    ↓
Save Processed Output
```

Stage 03 files are stored under:

`homework/homework03/`

---

## Stage 04 — Data Acquisition & Ingestion

Stage 04 focused on acquiring external market-related data through both an API-style source and web scraping.

### API Ingestion

The API ingestion workflow used:

**Ticker:** AAPL  
**Source:** Yahoo Finance through `yfinance`

The workflow included:

- downloading historical AAPL market data
- converting the result into a pandas DataFrame
- parsing dates and numeric values
- validating required columns
- checking shape and missing values
- saving the raw dataset to `data/raw/`

The validation output confirmed that:

- required columns were present
- the dataset contained valid observations
- no missing values were present in the required fields

### Web Scraping

A public HTML table containing S&P 500 constituent information was scraped using:

```python
requests
BeautifulSoup
```

The resulting DataFrame included fields such as:

- Symbol
- Security
- GICS Sector
- GICS Sub-Industry
- Headquarters Location
- Date Added
- CIK
- Founded

The scraped data was validated for:

- required columns
- shape
- missing values

The resulting dataset contained more than 500 S&P 500 constituent records.

### Reproducibility and Risks

- API and webpage availability may change over time.
- External websites may modify their HTML structure.
- API responses may temporarily fail or be rate-limited.
- Data schemas should be validated after ingestion.
- `.env` is kept local and is not committed to GitHub.

The ingestion workflow follows:

```text
External Source
      ↓
Acquire Data
      ↓
Convert to DataFrame
      ↓
Parse Types
      ↓
Validate
      ↓
Save to data/raw/
```

Stage 04 files are stored under:

`homework/homework04/`

---

## Stage 05 — Data Storage

Stage 05 focused on implementing a reproducible and reusable data-storage workflow.

### Folder Structure

- `data/raw/` — raw datasets stored primarily as CSV
- `data/processed/` — processed datasets stored primarily as Parquet

### Storage Formats

#### CSV

CSV is used for raw data because it is:

- simple
- human-readable
- widely supported
- easy to inspect manually

#### Parquet

Parquet is used for processed data because it:

- preserves data types more reliably
- supports compression
- provides more efficient analytical storage
- is suitable for larger quantitative datasets

### Environment-Driven Paths

Storage paths are configured through `.env`:

```text
DATA_DIR_RAW=data/raw
DATA_DIR_PROCESSED=data/processed
```

Python loads these values using `python-dotenv`, which avoids hard-coding machine-specific file paths.

### Save and Reload Workflow

A DataFrame is saved in two formats:

```text
DataFrame
   ↓
CSV → data/raw/
   ↓
Parquet → data/processed/
```

Both files are then reloaded and validated.

### Validation

Validation checks include:

- confirming that reloaded DataFrames have the expected shape
- confirming that required columns exist
- checking important dtypes
- checking missing values
- verifying that dates and numeric columns are correctly interpreted

The recommended workflow is:

```text
Save
 ↓
Reload
 ↓
Validate
 ↓
Trust
```

### Reusable I/O Utilities

Stage 05 implements reusable functions including:

```python
detect_format()
write_df()
read_df()
```

These utilities:

- detect CSV or Parquet based on file suffix
- automatically create missing parent directories
- route to the correct pandas read/write method
- provide a clear error message if a Parquet engine is unavailable

### Assumptions

- Input DataFrames have a consistent schema before storage.
- Required Python packages are installed.
- A Parquet engine such as `pyarrow` or `fastparquet` is available when needed.
- `.env` contains valid relative paths for raw and processed data.
- Storage formats may preserve values correctly even when Python object types are not perfectly identical after a round trip.

Stage 05 files are stored under:

`homework/homework05/`

---

## Data and Version-Control Practices

This repository follows several reproducibility and security practices:

- `.env` files are kept local and are excluded from Git.
- `.env.example` files may be committed as configuration templates.
- Raw and processed datasets are stored separately.
- Relative paths are preferred over machine-specific absolute paths.
- Notebooks should be executable from top to bottom.
- Dependencies should be documented through `requirements.txt`.
- Each stage is maintained in its own homework folder.

---

## Homework Structure

```text
homework/
├── homework0/
├── homework01/
├── homework02/
├── homework03/
├── homework04/
└── homework05/
```

Each folder contains the files required for the corresponding bootcamp stage.

---

## Project Direction

The broader project direction is to build a quantitative framework for identifying short-term downside risk in Bitcoin using market and volatility indicators.

Future work may include:

- additional market data acquisition
- feature engineering
- volatility and momentum indicators
- downside-risk target construction
- predictive modeling
- out-of-sample evaluation
- visualization and reporting
- portfolio risk-management applications

---

## Repository Notes

This repository is maintained as part of the bootcamp coursework and will continue to be updated as later stages and project components are completed.