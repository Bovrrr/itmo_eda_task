# Copilot Instructions for AI Coding Agents

## Project Overview
This repository contains anonymized financial transaction data for fraud detection and exploratory data analysis (EDA). The main files are:
- `transaction_fraud_data.parquet`: Transaction records with rich features for ML and analytics.
- `historical_currency_exchange.parquet`: Daily currency exchange rates for normalization.
- `README.md`: Detailed schema and field descriptions for both datasets.

## Data Architecture
- **No code files** are present; the workspace is data-centric. All logic and workflows should be built around reading, transforming, and analyzing the provided Parquet datasets.
- **Transaction data** includes nested structures (see `last_hour_activity`), categorical, numerical, and boolean features. Fraud labels are present for supervised ML.
- **Currency exchange data** enables normalization of transaction amounts across currencies and dates.

## Developer Workflows
- **Typical workflow:**
  1. Load Parquet files using Python (recommended: `pandas`, `pyarrow`).
  2. Join/merge transaction data with currency rates for normalization.
  3. Perform EDA, feature engineering, and ML modeling.
- **No build or test scripts** are present. You may create notebooks or scripts as needed.
- **No external dependencies** are required by default; install Python packages as needed for data analysis (e.g., `pandas`, `scikit-learn`, `matplotlib`).

## Project-Specific Patterns
- **Field types and meanings** are fully described in `README.md`. Always consult this file for schema details before coding.
- **Nested fields**: The `last_hour_activity` field is a struct with multiple subfields. Handle with appropriate dataframe/nested structure logic.
- **Fraud detection**: The `is_fraud` boolean is the target for ML tasks.
- **Currency normalization**: Use `historical_currency_exchange.parquet` to convert `amount` to a common currency (usually USD) based on `timestamp`.

## Conventions
- **Russian language** is used for documentation and field descriptions. Code and comments should be in English for clarity.
- **No custom scripts or automation** are present. All workflows are ad hoc and should be documented in notebooks or scripts you create.
- **No hidden conventions**: All relevant patterns are discoverable in `README.md`.

## Example Workflow
```python
import pandas as pd
# Load transaction data
transactions = pd.read_parquet('transaction_fraud_data.parquet')
# Load currency rates
rates = pd.read_parquet('historical_currency_exchange.parquet')
# Normalize transaction amounts to USD (example logic)
# ...
```

## Key Files
- `README.md`: Always reference for schema and field explanations.
- `transaction_fraud_data.parquet`: Main dataset for analysis.
- `historical_currency_exchange.parquet`: Use for currency conversion.

---
For new scripts, notebooks, or ML models, follow the above patterns and document any new conventions in this file.

<remark>
– think step by step
– do step by step
</remark>