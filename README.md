# **Extracting and Visualizing Stock Data**

Analyze real stock price data and company revenue, then communicate insights with clear visuals.
Built as part of IBM’s Python Project for Data Science.

## **Overview**
  
This project pulls daily stock prices via yfinance, scrapes quarterly revenue data from a public source, and produces side-by-side visuals for Tesla (TSLA) and GameStop (GME).
It demonstrates data acquisition, cleaning, exploratory analysis, and presentation in Python.

Key questions:

1. How have TSLA and GME prices evolved over time?
2. What does their revenue trend look like?
3. How do price movements relate to revenue changes?

## **Objectives**

- Implement a reusable plotting function for time-series data.
    
- Extract stock prices with yfinance.
    
- Scrape revenue tables with requests + BeautifulSoup.
    
- Clean/merge the data for analysis.
    
- Produce publication-ready charts for TSLA and GME.

- Implement a reusable plotting function for time-series data.
    
- Extract stock prices with yfinance.
    
- Scrape revenue tables with requests + BeautifulSoup.
    
- Clean/merge the data for analysis.
    
- Produce publication-ready charts for TSLA and GME.

## **Stack**

- Python: pandas, numpy, matplotlib, yfinance, requests, beautifulsoup4
    
- Environment: Jupyter Notebook
    
- Optional: plotly (interactive charts)

## **Methods**

- Price Data (yfinance)
    
- Tickers: TSLA, GME
    
- Columns used: Date, Open, High, Low, Close, Volume
    
- Revenue Data (Web Scraping)
    
- Parse quarterly revenue table (date, revenue) from a public webpage.
    
- Clean currency strings, cast to numeric, handle missing rows.
    
- Visualization
    
- Reusable make_graph() to plot price/revenue time series.
    
- Export charts to figures/.

## **Results**

- TSLA: [PLACEHOLDER: 1–2 sentences on trend or notable periods]

- GME: [PLACEHOLDER: short note on spikes/volatility]
    
- Revenue vs Price: [PLACEHOLDER: any visible relationship/lag]

## **Extension**

This project was extended by applying linear regression to model the relationship between opening stock price and company revenue at Tesla after a logarithmic transformation to improve normality and model assumptions. Diagnostic tools, including Q-Q plots, were used to assess residual distributions before and after transformation. The model was then applied to predict the effect of a hypothetical 10% increase in the company's revenue, with results back-transformed to the original scale and accompanied by 95% confidence and prediction intervals, illustrating both the expected change in the mean stock price and the variability in individual predictions.


