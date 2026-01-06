Stochastic Forecasting of Economic Indicators

Language: R
License: MIT
Status: Completed

PROJECT OVERVIEW
This project applies the Box-Jenkins methodology to model and forecast two distinct types of economic time series data over a 10-year period (2015–2025):

1. EUR/USD Exchange Rate: A non-seasonal, stochastic financial time series.
2. US Housing Starts: A highly seasonal macroeconomic indicator.

By comparing these two datasets, the analysis demonstrates the difference between modeling Random Walks (Efficient Market Hypothesis) and Seasonal Cycles (Construction Industry trends).

KEY FINDINGS

Dataset 1: EUR/USD Exchange Rate

* Characteristics: Non-Stationary, Stochastic
* Model Selected: ARIMA(1,1,0)
* 12-Month Forecast Trend: Flat/Neutral (Random Walk behavior with wide confidence intervals).

Dataset 2: US Housing Starts

* Characteristics: Strong Seasonality, Variance Instability
* Model Selected: SARIMA(1,0,0)(0,1,1)[12]
* 12-Month Forecast Trend: Cyclical (Predictable seasonal peaks in summer and troughs in winter).

METHODOLOGY
The project follows a rigorous statistical pipeline using R:

1. Data Preprocessing:
* Cleaning and handling missing values.
* Transformation: Applied Log transformation to stabilize variance (Housing Starts).
* Stationarity: Used Augmented Dickey-Fuller (ADF) tests to detect unit roots.


2. Model Identification:
* Analyzed ACF/PACF plots to determine AR/MA orders.
* Applied First Differencing (d=1) and Seasonal Differencing (D=1) to achieve stationarity.


3. Model Fitting:
* Evaluated candidate models based on minimized AIC/BIC scores.


4. Diagnostic Checking:
* Ljung-Box Test: Verified residuals are white noise (independent).
* Shapiro-Wilk Test: Checked for normality of residuals.


5. Forecasting:
* Generated 12-month and 24-month forecasts with 80% and 95% confidence intervals.



VISUALIZATIONS

1. EUR/USD Forecast (The "Random Walk")
The widening confidence intervals indicate the inherent unpredictability of exchange rates.
[<img width="1297" height="716" alt="image" src="https://github.com/user-attachments/assets/231d1ae8-4675-4e4a-be28-49431b9e31b7" />
2. Housing Starts Forecast (The "Seasonal Cycle")
The model accurately captures the annual construction cycle.
[<img width="1153" height="750" alt="image" src="https://github.com/user-attachments/assets/046845af-b30b-40d1-a135-070544afb55a" />]

TECHNOLOGIES & LIBRARIES

* Language: R
* IDE: RStudio
* Key Libraries:
* forecast (ARIMA modeling)
* tseries (ADF tests)
* TSA (Time Series Analysis tools)
* ggplot2 (Visualization)



PROJECT STRUCTURE
data/
DEXUSEU.csv       (Raw Exchange Rate Data - FRED)
HOUSTNSA.csv      (Raw Housing Starts Data - FRED)
src/
analysis.Rmd      (Source code - R Markdown)
analysis.pdf      (Final Report - Readable format)
README.md            (Project Documentation)
LICENSE              (MIT License)

HOW TO RUN

1. Clone the repository:
git clone [https://github.com/YourUsername/RepoName.git](https://www.google.com/search?q=https://github.com/YourUsername/RepoName.git)
2. Open RStudio and install dependencies:
install.packages(c("forecast", "tseries", "TSA"))
3. Run the analysis:
Open src/analysis.Rmd
Click "Knit" to generate the full PDF report with all graphs.

DATA SOURCES
Federal Reserve Bank of St. Louis (FRED):

* DEXUSEU (U.S. / Euro Foreign Exchange Rate)
* HOUSTNSA (New Privately Owned Housing Units Started)

AUTHOR
Hemalatha Katta
