# 📊 Bitcoin Sentiment & Trader Performance Analysis

## 🧠 Objective
This project explores the **relationship between Bitcoin market sentiment** (measured via the Fear & Greed Index) and **trader performance metrics** from historical trade data on the Hyperliquid platform. The goal is to derive **actionable insights** and develop **sentiment-aware trading strategies** that improve risk management and returns.

---

## 📁 Datasets Used

### 1. **Bitcoin Fear & Greed Index**
- `timestamp`, `value` (0–100), `classification` (Fear, Greed, etc.), `date`

### 2. **Hyperliquid Trader Data**
- `account`, `execution_price`, `size_usd`, `side`, `timestamp_ist`, `closed_pnl`, etc.

---

## 🧹 Data Preparation

### ✔️ Preprocessing
- Standardized column names
- Converted timestamps to datetime
- Extracted date from `timestamp_ist` for alignment

### 🔗 Merging
- **Inner join** on `date` to align trades with sentiment data

### ⚙️ Feature Engineering
- `is_profitable`: Boolean based on `closed_pnl > 0`
- `normalized_pnl`: `closed_pnl / size_usd`
- `pnl_category`: Categorical — High Loss, Loss, Breakeven, Profit, High Profit
- `sentiment_score`: Mapped sentiment labels (0 to 4)

---

## 📊 Exploratory Data Analysis (EDA)

### 📈 Profitability by Sentiment
- Higher profitability during **Greed** and **Extreme Greed**
- More losses during **Fear**, especially **Extreme Fear**

### 💹 Normalized PnL
- Greater returns per USD during optimistic sentiment

### 🧮 PnL Categories
- **Breakeven** most frequent across sentiments
- **High Loss** spikes during **Extreme Fear**
- **High Profit** more likely during Greed phases

### 🕒 Sentiment Trends
- Sentiment cycles align with Bitcoin bull/bear market trends

---

## 💡 Key Insights

- **Sentiment-Performance Correlation**: Higher sentiment = better average profitability
- **PnL Patterns**: Traders earn more per dollar during Greed
- **Volatility Behavior**: Execution price volatility increases with high sentiment
- **Predictive Potential**: Sentiment score shows predictive value for profitability
- **Trade Behavior**: Traders reduce size during Fear, potentially missing reversal gains

---

## 🎯 Strategy Recommendations

### 📌 Sentiment-Based Execution
- Prioritize high-value trades during **Greed**
- Use defensive positions during **Extreme Fear**

### 🔍 Sentiment-Aware Filters
- Combine technical setups with Greed-based filters for better confirmation

### 🧠 Trade Efficiency Tracking
- Use `pnl_per_token`, `normalized_pnl` to refine execution strategies

### 💼 Position Sizing & Risk Management
- Adjust leverage dynamically based on sentiment
- Tighter stops and smaller size during Fear

### 💸 Fee Optimization
- Bundle small trades and avoid breakeven trades with smart fee strategies

### 🧪 Strategy Backtesting
- Test:
  - Long during Greed → Exit at Neutral
  - Avoid trades in Extreme Fear

### 🤖 ML Forecasting Model
- Train models using:
  - `log_execution_price`
  - `sentiment_score`
  - `value_weighted_pnl`
  - Predict outcomes or optimal entry timing

---

## 🚀 Actionable Implementation Ideas

- 📊 **Dashboard**: Real-time sentiment + trade overlay, risk heatmaps
- 📢 **Trader Alerts**: Notify users during Extreme Fear/Greed
- 🧪 **Backtesting by Sentiment**: Simulate strategy performance per sentiment phase
- 💼 **Portfolio Shift**: Rebalance based on rolling sentiment scores

---

## 🛠️ Suggested Next Steps

- Integrate live sentiment API feed
- Develop sentiment-reactive ML model for scoring trades
- Build a performance dashboard with regular updates
- Run A/B tests for strategies across sentiment phases

---

## ✅ Conclusion

- The **Fear & Greed Index** provides strong predictive insight for trading performance.
- Merging engineered trade features with sentiment data allows for **smarter, more adaptable strategies**.
- Through automation and ongoing performance review, traders can consistently improve **profitability** and **risk exposure**.

---

## 📌 Author

**Ankur**  
*Data Analyst | Strategy Researcher | ML Enthusiast*
