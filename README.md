# 📈 Hyperliquid Trader Behavior & Sentiment Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/Goutham-IITJ/crypto-behavioral-clustering-ml/blob/main/analysis.ipynb)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([https://github.com/Goutham-IITJ/crypto-behavioral-clustering-ml/blob/main/analysis.ipynb](https://colab.research.google.com/drive/1GCpUAHcnIBJZ06GdCO2RDtJFgBl0cBcl?usp=sharing))

## 📌 Overview
This repository contains a comprehensive data science pipeline analyzing the relationship between **Hyperliquid Historical Trader Data** and the **Bitcoin Fear & Greed Index**. The goal was to move beyond surface-level correlations to uncover "hidden patterns" in trader archetypes and sentiment-driven performance.

---

## 🚀 Key Insights & "Hidden Patterns"

### 1. Extreme Profit Concentration (The Whale Effect)
* **Finding:** Profit is not distributed normally; it follows a power law.
* **Data Point:** The top 1% of accounts (represented by 1 elite trader in this dataset) generated **$2,143,382.60**, accounting for **20.9%** of the total ecosystem profit.
* **Strategic Insight:** Success on the platform is driven by institutional-scale conviction, which often moves independently of retail sentiment indicators.

### 2. High-Alpha "Fear" Windows
* **Finding:** Market entries during "Extreme Fear" carry significantly higher risk-adjusted returns.
* **Data Point:** **BUY** signals during Fear yielded a **Mean PnL of $252.94**, whereas **SELL** signals during Greed yielded only **$55.98**.
* **Strategic Insight:** While "Greed" provides more frequent trading opportunities, "Fear" provides the highest individual trade quality and capital efficiency.

### 3. Sentiment as a Lagging Indicator
* **Finding:** The Fear/Greed index functions as a confirmation tool rather than a predictive signal.
* **Data Point:** Cross-correlation analysis shows the strongest relationship at a **-7 day lag**.
* **Strategic Insight:** Price action leads sentiment; by the time the index reflects "Extreme Fear," the optimal accumulation window for professional "Whales" has often already passed.

---

## 🛠️ Technical Workflow

### 1. Data Engineering & Feature Extraction
* **Time-Series Alignment:** Synchronized high-frequency trading timestamps with daily macro sentiment logs.
* **Sentiment Velocity:** Engineered a "Velocity" feature to track the rate of change in market mood—identified as a Top-3 predictor of PnL.
* **Contrarian Flag:** Developed logic to isolate traders acting against the herd (e.g., selling into "Extreme Greed").

### 2. Behavioral Clustering (K-Means)
I identified 4 distinct **Trader Archetypes** using unsupervised learning:
* **Archetype 0 (Institutional Whale):** Characterized by high trade size and high PnL.
* **Archetype 1 (The Retail Herd):** Characterized by low PnL and low contrarianism.
* **Archetype 3 (The Velocity Specialist):** Traders who maximize profit specifically during rapid sentiment shifts.

### 3. Predictive Modeling (Random Forest)
A Random Forest Regressor was used to rank features driving trade success:
* **Top Predictors:** **Size USD (0.47)** and **Sentiment Velocity (0.14)**.
* This confirms that while capital scale is the primary driver of total profit, sentiment-aware execution offers a verifiable edge.

---

## 📂 Repository Structure
* **`analysis.ipynb`**: The primary research notebook containing EDA, ML, and Backtesting.
* **`requirements.txt`**: Necessary libraries (`pandas`, `scikit-learn`, `seaborn`, `matplotlib`).
* **`plots/`**: Visualizations of equity curves, cluster distributions, and feature importance.

---

## 🏁 Conclusion
The data suggests that a simple "Fear/Greed" strategy is insufficient to beat the market baseline due to the 7-day lag in sentiment reporting. However, by tracking **Whale Archetypes** and **Sentiment Velocity**, we can identify high-probability reversal zones and avoid retail exhaustion.
