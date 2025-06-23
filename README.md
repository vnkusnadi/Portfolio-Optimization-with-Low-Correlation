# 📊 Project: Portfolio-Optimization-with-Low-Correlation 
An algorithmic portfolio management simulation over a 12-year horizon using correlation-based stock selection strategies and performance evaluation with Sharpe Ratio and Max Drawdown. This project simulates a systematic approach to managing a $1M investment in the U.S. stock market from 2012 to 2024. The strategy involves quarterly rebalancing and selecting low-correlation assets from the S&P 500 to form a diversified portfolio of 10 stocks.

<br>

## 📈 Performance Evaluation

| Strategy Version       | Sharpe Ratio | Max Drawdown | Return (2012–2024) |
|------------------------|--------------|--------------|--------------------|
| **Original Strategy**  | 1.13         | -35.17%      | 900%+              |
| **Improved Strategy**  | 1.45         | -29.22%      | 1800%+             |
| **SPY ETF**            | 0.88         | -32.05%      | ~700–800%          |
| **QQQ ETF**            | 0.95         | -36.69%      | ~1000–1100%        |

<br>

##  🧩 Strategy Breakdown
- Every 3 months, the following is done:
  - Use the past 6 months of daily return data for all S&P 500 stocks.
  - Select 10 stocks based on correlation analysis:
    - Stock 1: Lowest average absolute correlation to all others.
    - Stock 2: Lowest absolute correlation with Stock 1.
    - Stock 3: Lowest average absolute correlation to Stock 1 & 2.
    - Repeat until 10 unique stocks are chosen.
- Invest equally in the selected 10 stocks.
- Hold for the next 3 months.
- Repeat this process for the entire 12-year period.

<br>

During the simulation, the portfolio's daily wealth is tracked to compute:
- 📉 Maximum Drawdown (MDD): Largest observed loss from a peak to a trough.
- 📊 Sharpe Ratio (Annualized):
  - Convert daily Sharpe ratio to annual using:
  - $$ \text{Sharpe}_{\text{annual}} = \text{Sharpe}_{\text{daily}} \times \sqrt{252} $$
These metrics are used to evaluate performance against benchmark ETFs:
- SPY – S&P 500 Index
- QQQ – Nasdaq 100 Index


<br>

## 🧮 What I Learned
- Correlation Matrix: How to compute and interpret correlations between assets.
- Portfolio Diversification: Reducing risk via low-correlation asset selection.
- Performance Metrics: Sharpe Ratio and Max Drawdown as risk-return indicators.
- Time-Series Handling: Using pandas and yfinance to handle financial time series data.
- Investment Simulation: Creating realistic backtests with rebalance logic and historical data.

<br>

## 🔧 Technologies Used
- Python 3.13.3
- pandas, numpy, matplotlib
- yfinance: Historical stock data
- seaborn: Visualization
- scipy: Statistical functions

<br>

## 💻 How to Run

    # In Jupyter Notebook
    !pip install yfinance pandas numpy matplotlib seaborn
Open the notebook Project_1_Portfolio_Management.ipynb, and run cells sequentially to:
- Fetch data
- Build portfolio quarterly
- Plot performance
- Compare with SPY and QQQ

<br>

## 🧠 Stochastic Concepts Used
This project applies stochastic modeling by simulating a dynamic investment strategy under uncertainty:
- Daily price movement introduces randomness
- Correlation analysis uses random time series behavior
- Sharpe ratio models risk-adjusted expected returns
