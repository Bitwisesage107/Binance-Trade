# Binance Trader Performance Analysis

This project analyzes historical trade data to evaluate and rank trader performance based on key financial metrics.  It processes trade data from CSV files, calculates performance indicators, determines feature importance using a machine learning model, and ranks accounts based on a weighted scoring system.

## Dataset

The dataset 'TRADES_90D.csv' used in this analysis consists of trade information stored in a CSV file. CSV file contains, The data of trading of 90 days from many users it has two columns Port_ids and `Trade_History`. `Trade_History` column within the dataset contains trade details as string representations of Python lists of dictionaries here each dictionary contains trade details, including timestamps, symbols, buy/sell indicators, quantities, fees, and realized profits. This project focuses on cleaning and converting this data into a usable format for analysis.

The dataset used in this analysis is proprietary and not publicly available.

## Code

The Python code for this analysis is contained in the notebook `trader_performance_analysis.ipynb` or in the Python script `trader_performance_analysis.py`.  The code is organized into the following sections:

1. **Data Loading and Exploration:** Reads trade data from the 'TRADES_90D.csv' file and converts this into a Pandas DataFrame.
2.  **Data Cleaning and Preprocessing:** Cleans and converts the `Trade_History` column from strings to lists of dictionaries using `ast.literal_eval()`. Handles potential errors during the conversion process.
3.  **Feature Engineering and Metric Calculation:** Calculates key performance indicators (KPIs) such as ROI, PnL, Sharpe Ratio, MDD, and Win Rate for each `baseAsset`.
4.  **Feature Importance and Scoring:**  Determines feature importance using a linear regression model trained to predict `realizedProfit`. Implements a weighted scoring system based on feature importance and KPIs.
5.  **Ranking and Output:** Ranks accounts (grouped by `baseAsset`) based on their average weighted score.  Saves the results to CSV files.

**How to Run the Code:**

1.  Clone this repository.
2.  Install the required libraries (see "Tools" section below).  It's recommended to use a virtual environment: `python3 -m venv .venv` followed by `source .venv/bin/activate` (or the equivalent for your OS). Then install the requirements: `pip install -r requirements.txt`.
3.  Place your CSV data files in the `data` directory (or specify the correct path in the script).
4.  Run the Python script: `trader_performance_analysis.ipynb` or `python trader_performance_analysis.py`.
5.  The results, including the calculated metrics and top 20 accounts, will be saved to CSV files in the project directory.

## Results

The analysis identified key performance differences across various `baseAsset`s. "The analysis revealed that certain assets exhibited higher risk-adjusted returns, while others prioritized lower volatility.  The feature importance analysis highlighted the influence of `profit_per_trade` on overall profitability.  The top-ranked accounts demonstrated a combination of high ROI and controlled drawdowns.

"The top 20 accounts achieved significantly higher average returns (ROI) compared to the overall population, while maintaining a reasonable level of risk.  Their Sharpe Ratios were notably stronger, indicating better risk-adjusted performance.  These accounts also showed a tendency towards higher win rates and optimized trade sizing, contributing to their success."






## Tools

*   Python 3
*   Pandas
*   NumPy
*   Scikit-learn
*   SciPy
*   `ast` (Abstract Syntax Trees)
*   Jupyter Notebook
*   `requirements.txt` (List of requirements for the project)