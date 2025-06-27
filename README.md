# 📊 Trader Behavior vs Market Sentiment Analysis

## 📁 Project Overview
This project analyzes the relationship between Bitcoin market sentiment (Fear vs. Greed) and trader behavior/performance. Using historical trade data and sentiment index values, we uncover patterns in profit/loss (PnL), trade size, and win rates to guide better trading strategies.

---

## 📄 Datasets Used
1. **Bitcoin Market Sentiment Dataset**  
   ➤ Columns: `date`, `value`, `classification` (e.g., Extreme Greed, Fear)

2. **Hyperliquid Trader Data**  
   ➤ Columns: `Account`, `Coin`, `Execution Price`, `Size Tokens`, `Size USD`, `Side`, `Timestamp`, `Closed PnL`, `Fee`, etc.

---

## ⚙️ Key Steps Performed

### 1. 📥 Data Cleaning & Merging
- Removed irrelevant columns like transaction hash/order IDs
- Merged both datasets using the `date` field
- Verified no missing values

### 2. 🧠 Feature Engineering
- Added binary flag `is_profitable`
- Created `classification_simple` column with just "Fear" or "Greed"
- Scaled the sentiment score using `StandardScaler`

### 3. 📊 Exploratory Data Analysis (EDA)
- **Box and Violin Plots**: Showed that PnL varies widely regardless of sentiment
- **Bar Charts**: Showed average PnL and win rates per sentiment

### 4. 🧪 Hypothesis Testing
- Ran a t-test on PnL for Fear vs. Greed days
- Result: No statistically significant difference in PnL

### 5. 🔮 Regression Analysis
- Built a simple Linear Regression model:
    - Input: Scaled sentiment
    - Output: Closed PnL
- Result: Weak positive correlation, not enough to make predictions

---

## 🔍 Key Findings
1. Traders' PnL is highly variable — most make small or no profit.
2. On Fear days, traders use **larger position sizes**, likely reacting to volatility.
3. **Average PnL** is slightly higher in Fear days, but not statistically significant.
4. **Win rate** is marginally better on Greed days (0.5% higher).
5. Linear regression shows a weak positive link between sentiment score and profit — not reliable alone.
6. Combining sentiment with other features (like leverage or timing) could improve prediction power.

---

## 📁 Folder Structure
```
📦 Sentiment_Trader_Analysis
├── trader_sentiment_analysis.ipynb   # Main analysis notebook
├── README.md                         # This file
├── historical_data.csv               # Trader data
├── fear_greed_index.csv              # Sentiment index
```

---

## 📌 How to Run
1. Install required packages:
```bash
pip install pandas matplotlib seaborn scikit-learn
```
2. Open `trader_sentiment_analysis.ipynb`
3. Run all cells in order

---

## 💬 Final Thoughts
While trader performance shows some sensitivity to market sentiment, the relationship is weak. This analysis sets a strong foundation for deeper modeling using multi-variable approaches.

---

