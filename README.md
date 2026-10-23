# Currency Exchange Rate Tracker & Time Series Analysis

A data pipeline that pulls daily exchange rates from a public API, stores them in SQLite, and analyzes trends with SQL window functions.

## Data Source
Frankfurter API (European Central Bank reference rates), base currency USD.

## Tools
- Python: requests, pandas, matplotlib
- SQL: SQLite (LAG, moving averages, CTEs, joins, aggregation)
- Google Colab

## Pipeline
1. Pulled two years of daily rates for 6 currencies (EUR, GBP, JPY, CHF, CAD, AUD)
2. Reshaped the JSON response into a long-format table
3. Cleaned the data and added year, month, and weekday columns
4. Stored the data in SQLite
5. Ran SQL analysis: min/max, monthly averages, daily change, 7 and 30 day moving averages, volatility ranking
6. Visualized results with matplotlib

## Key Findings
- The dataset covers 3066 daily observations from 2024-10-23 to 2026-10-23 across 6 currencies.
- The most volatile currency against USD is AUD (average absolute daily change 0.419%), while the most stable is CAD (0.232%).
- Over the full period, the USD gained the most against JPY (2.53%) and gained the least or lost the most against AUD (-5.55%).
- Moving averages (7-day and 30-day) were computed with SQL window functions to separate short-term noise from trend.

## Files
- exchange_rates_final.csv: cleaned dataset
- currency.db: SQLite database
- *.png: charts

## How to Run
Open the notebook in Google Colab and run all cells in order.
