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

## Contents

| Jupiter notebook and README               | Description                                                        |
|--------------------|--------------------------------------------------------------------|
| `claims_model_static.R`    | Static SIS model with fixed β, γ and MH inference                  |
| `claims_model_time_varying.R` | Time-varying β(t), γ(t) inference via component-wise MH sampling |
| `README.md`         | Project overview (this file)                                      |

| Figures                                                           | Description                                             |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| `Histogram_of_Posterior_of_Beta_(Static_SIS_model).png`                                | Posterior distribution of fixed β                       |
| `Histogram_of_Posterior_of_Gamma_(Static_SIS_model).png`                               | Posterior distribution of fixed γ                       |
| `Trace_of_Beta_(Static_SIS_model).png`                                                 | MCMC trace plot for fixed β                             |
| `Trace_of_Gamma_(Static_SIS_model).png`                                                | MCMC trace plot for fixed γ                             |
| `Autocorrelation_plot_of_Beta_Samples_(Static_SIS_model).png`                          | Autocorrelation of β samples (static model)             |
| `Autocorrelation_plot_of_Gamma_Samples_(Static_SIS_model).png`                         | Autocorrelation of γ samples (static model)             |
| `Plot_of_Simulated_claims_path_(Static_SIS_model).png`                                 | Simulated claims path over time (Static SIS model)      |
| `Plot_of_Posterior_Predictive_Claim_Paths_for_five_sims_(Static_SIS_model).png`        | Posterior predictive claim paths (static model, 5 sims) |
| `Plot_number_of_Active_and_Susceptible_Policyholders_over_Time_(Static_SIS_model).png` | SIS model dynamics (S and I)                            |


## **Objectives**

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

- TSLA: Tesla’s share price showed steady growth until around 2019, after which it surged dramatically, peaking in 2021. This period aligns with increasing investor interest and rising revenues.

- GME: GameStop’s price remained relatively flat until early 2021, when it experienced an extreme short-term spike due to retail investor activity. The volatility was largely disconnected from fundamentals.
    
- Revenue vs Price: For Tesla, share price growth broadly follows revenue growth but with a noticeable lag. In contrast, GameStop’s share price spike does not correspond with revenue changes, indicating a speculative price movement.

## NLM Extension

- This project was extended by myself by applying linear regression to model the relationship between opening stock price and company revenue at Tesla after a logarithmic transformation to improve normality and model assumptions.

- Diagnostic tools were used to assess residual distributions before and after transformation. These included:
  - Residual vs. Fitted Plot: to check non-linearity or heteroscedasticity.
  - Q-Q Plot: to assess normality of residuals.
  - Influence Plot: to identify leverage and outlier points.
  - Kolmogorov-Smirnov (KS) Test: a nonparametric test used to statistically evaluate whether standardized residuals follow a normal distribution.

- Model was then applied to predict the effect of a hypothetical 10% increase in the company's revenue, with results back-transformed to the original scale and accompanied by 95% confidence and prediction intervals, illustrating both the expected change in the mean stock price and the variability in individual predictions.


