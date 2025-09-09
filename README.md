# Trader Performance & Market Sentiment Analysis 

This project analyzes the relationship between **trader performance** and **market sentiment** using historical trading data and the Fear & Greed Index. The goal is to understand how different market conditions impact **daily profit/loss (PnL)**, **win rate**, and **average trade size**.

---

## Project Overview

Traders’ performance can be influenced by market sentiment. By combining historical trading data with the Fear & Greed Index, this project aims to:  

- Examine how **daily PnL**, **win rate**, and **average trade size** vary with sentiment.  
- Explore correlations between performance metrics and market sentiment.  
- Visualize trends and distributions to gain actionable insights.  

---

## Dataset

### 1. Historical Trader Data (`historical_data.csv`)  
| Column           | Description                                      |
|-----------------|--------------------------------------------------|
| `date`          | Date of trading activity                          |
| `Account`       | Trader account ID                                 |
| `dailyPnL`      | Daily profit/loss in USD                          |
| `avgTradeSizeUSD` | Average trade size in USD                        |
| `winRate`       | Daily win rate (0–1)                              |

### 2. Fear & Greed Index (`fear_greed_index.csv`)  
| Column           | Description                                      |
|-----------------|--------------------------------------------------|
| `date`          | Date                                             |
| `classification`| Market sentiment (`Extreme Fear`, `Fear`, `Neutral`, `Greed`, `Extreme Greed`) |

---

## Data Processing

- Loaded CSVs using `pandas`.  
- Converted `date` column to datetime format.  
- Mapped sentiment classifications to numerical scores:

```python
sentiment_map = {
    "Extreme Fear": -2,
    "Fear": -1,
    "Neutral": 0,
    "Greed": 1,
    "Extreme Greed": 2
}
## Analysis & Visualizations

### Statistical Analysis by Sentiment
- Calculated mean **daily PnL**, **win rate**, and **average trade size** grouped by sentiment.

### Correlation Analysis
- Generated correlation matrix of `dailyPnL`, `winRate`, `avgTradeSizeUSD`, and `sentiment_score`.

### Visualizations
- **Boxplots**: Show distribution of PnL, win rate, and trade size by sentiment.  
- **Lineplot**: Tracks daily PnL trends over time with sentiment context.  
- **Heatmap**: Displays correlations between metrics.

---

## Key Insights
- Market sentiment impacts trading performance:  
  - Extreme greed or fear days show higher variability in profits/losses.  
  - Average trade size and win rate can fluctuate significantly with sentiment.  
- Sentiment score correlates with key trader metrics, providing actionable insights for strategy adjustment.

---

###Future Work
-Include more granular sentiment data (e.g., hourly instead of daily).
-Analyze sentiment impact on individual trading strategies.
-Incorporate additional metrics such as volatility, leverage, or asset type.
