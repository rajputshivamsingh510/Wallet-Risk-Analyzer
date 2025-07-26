#  Wallet Risk Scoring from Scratch

This project evaluates the on-chain risk of Ethereum wallets based on their activity with the Compound V2 protocol. It analyzes wallet behavior using DeFi data and assigns a risk score from **0 (low risk)** to **1000 (high risk)**. The goal is to help identify potentially risky wallet behaviors for DeFi platforms, auditors, or analysts.

---

##  What This Project Does

- Connects to **Moralis API** to retrieve real-time wallet data from the Ethereum mainnet.
- Extracts key features that impact DeFi risk (e.g. borrow/supply ratio, liquidation history, token diversity).
- Applies **KMeans clustering** and **Random Forest modeling** to generate a refined risk score.
- Outputs risk scores in CSV format and includes insightful visualizations.

---

##  Features Extracted

| Feature               | Description                                 |
|-----------------------|---------------------------------------------|
| Leverage Risk         | Borrowed vs Supplied assets                 |
| Liquidation Risk      | Count of past liquidations                  |
| Portfolio Size Risk   | Total exposure in USD                       |
| Diversification Risk  | Number of unique tokens held                |
| Health Risk           | Estimated safety ratio (supply/borrow)      |

---

##  How Scoring Works

1. **Rule-Based Weighting**: Each feature is weighted (e.g., leverage = 30%, liquidation = 25%, etc.)
2. **Clustering**: KMeans clustering groups wallets into 5 behavior-based segments.
3. **ML Refinement**: A Random Forest model refines and predicts a normalized risk score.
4. **Scaling**: Final scores are scaled to a 0–1000 range.

---

##  Outputs

- `wallet_risk_scores.csv` – Final output with `wallet_id` and `score`
- `wallet_risk_scores_detailed.csv` – Full feature breakdown per wallet
- `Wallet_Risk_Assignment.pdf/.docx` – Full documentation and methodology
- Visualizations:
  - Risk Score Histogram
  - Risk Category Pie Chart

---

##  Technologies Used

- Python
- Pandas, NumPy, Requests, TQDM
- Scikit-learn (KMeans, RandomForestRegressor)
- Matplotlib, Seaborn
- Moralis Web3 API
- DOCX & PDF generation libraries

---

##  Visual Preview

![Risk Visualization](https://github.com/rajputshivamsingh510/Wallet-Risk-Analyzer/blob/3063389a75acc0b323cfef7338f2cf888b121b8f/Screenshot%202025-07-26%20162706.png)

---

##  Ideal For

- DeFi risk analysis
- Wallet profiling
- On-chain behavior audits
- Smart contract protocol security

