#  Task 7: Time Series Analysis – Stock Price Dataset

> Synent Technologies Data Science Internship

---

##  Problem Statement

Stock prices change over time and contain hidden patterns like trends and seasonal cycles. This project analyzes historical stock price data to uncover time-based trends, detect seasonality, and optionally forecast future values — helping understand how a stock has behaved over time and where it might be headed.

---

##  Dataset Details

| Property | Details |
|----------|---------|
| **Name** | Stock Price Dataset |
| **Source** | [Kaggle – Stock Market Dataset](https://www.kaggle.com/datasets/jacksoncrow/stock-market-dataset) or [Yahoo Finance via yfinance](https://pypi.org/project/yfinance/) |
| **Frequency** | Daily |
| **Key Stock Used** | e.g. Apple (AAPL) / any stock of choice |

### Key Columns
| Column | Description |
|--------|-------------|
| `Date` | Trading date |
| `Open` | Opening price |
| `High` | Highest price of the day |
| `Low` | Lowest price of the day |
| `Close` | Closing price |
| `Volume` | Number of shares traded |

---

##  Approach

### Step 1 – Data Loading & Preprocessing
- Loaded stock price CSV (or fetched via `yfinance`)
- Parsed `Date` as datetime and set as index
- Checked for missing values and handled gaps
- Sorted data chronologically

### Step 2 – Exploratory Data Analysis
- Plotted raw closing price over time
- Visualized trading volume trends
- Computed rolling statistics (30-day and 90-day moving averages)

### Step 3 – Trend Analysis
- Applied moving averages (MA30, MA90) to smooth noise and reveal long-term direction
- Identified bullish and bearish periods
- Calculated daily returns and cumulative returns

### Step 4 – Seasonality Detection
- Resampled data to monthly and quarterly averages
- Plotted month-wise box plots to detect seasonal price patterns
- Used decomposition (`seasonal_decompose`) to separate trend, seasonality, and residuals

### Step 5 – Volatility Analysis
- Computed daily percentage change
- Plotted rolling standard deviation to measure volatility over time
- Identified periods of high and low market volatility

### Step 6 – Forecasting (Optional)
- Applied Simple Moving Average forecast
- Used ARIMA model for short-term price forecasting
- Plotted predicted vs actual values with confidence intervals

---

##  Results & Key Findings

- Clear **long-term upward trend** visible in the closing price over the analysis period
- **30-day and 90-day moving averages** confirmed trend direction and crossover signals
- **Monthly seasonality** detected — certain months consistently showed higher/lower prices
- **Seasonal decomposition** cleanly separated trend, seasonal, and residual components
- **Volatility spikes** aligned with major market events (e.g. earnings reports, economic news)
- Daily returns followed an approximately normal distribution with occasional extreme values
- ARIMA forecast captured short-term direction with reasonable accuracy

### Visualizations Generated
- Closing price over time (line chart)
- Moving averages (MA30 & MA90) overlaid on price
- Daily returns histogram
- Cumulative returns chart
- Monthly seasonality box plot
- Seasonal decomposition plot (Trend / Seasonal / Residual)
- Rolling volatility chart
- ARIMA forecast vs actual (if applicable)

---

##  Repository Structure

```
synent-task7-timeseriesanalysis-yourname/
│
├── task7_time_series_analysis.ipynb   # Main notebook
├── stock_data.csv                     # Raw dataset (or fetched via yfinance)
└── README.md                          # This file
```

---

##  How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/yourusername/synent-task7-timeseriesanalysis-yourname.git
   ```
2. Install dependencies
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels yfinance
   ```
3. Open the notebook
   ```bash
   jupyter notebook task7_time_series_analysis.ipynb
   ```
4. Run all cells top to bottom

> **Note:** If using `yfinance`, the notebook will automatically download the latest stock data — no CSV needed.

---

##  Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python 3.x | Programming language |
| Pandas | Data manipulation & resampling |
| NumPy | Numerical operations |
| Matplotlib | Visualizations |
| Seaborn | Statistical visualizations |
| Statsmodels | Seasonal decomposition & ARIMA |
| yfinance | Fetching live stock data (optional) |
| Jupyter Notebook | Development environment |

---

##  Author

Megh Chauhan

Data Science Intern – Synent Technologies  
[LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)
