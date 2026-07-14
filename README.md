# ✈️ Airline Passenger Time Series Analysis Using Python

## Overview

This project analyzes airline passenger data using Python to understand time-series behavior, identify trends and seasonality, and test whether the data is stationary using the **Augmented Dickey-Fuller (ADF) test**.

Time-series stationarity is a key concept in forecasting. Many statistical forecasting models, including ARIMA-based models, require the data to have a stable statistical structure over time. This project demonstrates how to inspect a time series, decompose its components, perform stationarity testing, and transform the data when necessary.

---

## Objectives

The main goals of this project are:

* Explore airline passenger growth over time
* Visualize trends and seasonal patterns
* Decompose the time series into:

  * Trend
  * Seasonality
  * Residual components
* Perform an Augmented Dickey-Fuller (ADF) test
* Determine whether the series is stationary
* Apply differencing to remove trends
* Re-test the transformed series for stationarity
* Analyze autocorrelation patterns using ACF and PACF plots

---

## Dataset

The dataset contains monthly totals of international airline passengers from **1949 to 1960**.

### Features

| Column     | Description                   |
| ---------- | ----------------------------- |
| Month      | Month and year of observation |
| Passengers | Number of airline passengers  |

The dataset contains:

* 144 monthly observations
* A clear upward trend
* Strong yearly seasonality

---

## Technologies Used

### Programming Language

* Python

### Libraries

* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical operations
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Statsmodels** — Time-series analysis and statistical testing

---

## Project Workflow

### 1. Data Loading and Preparation

The airline passenger dataset is imported and converted into a proper datetime-indexed time series.

Steps performed:

* Load CSV data
* Convert date column to datetime format
* Set date as index
* Inspect dataset structure

---

### 2. Exploratory Data Analysis

The passenger data is visualized to identify:

* Long-term growth trends
* Seasonal fluctuations
* Changes in passenger demand over time

The visualization shows that airline travel increased significantly throughout the observed period.

---

### 3. Time Series Decomposition

The series is decomposed into three components:

### Trend

Shows the long-term increase in airline passengers.

### Seasonality

Captures repeating yearly patterns caused by seasonal travel demand.

### Residual

Represents random variation not explained by trend or seasonality.

---

## Augmented Dickey-Fuller (ADF) Test

The ADF test is used to determine whether the time series is stationary.

### Hypotheses

**Null Hypothesis (H₀):**

The series contains a unit root and is non-stationary.

**Alternative Hypothesis (H₁):**

The series is stationary.

### Decision Rule

* If p-value ≤ 0.05:

  * Reject H₀
  * The data is stationary

* If p-value > 0.05:

  * Fail to reject H₀
  * The data is non-stationary

---

## Results

### Original Airline Data

The initial ADF test indicates that the airline passenger series is:

* Non-stationary
* Contains a strong trend
* Contains seasonal variation

Because of this, the dataset requires transformation before applying many forecasting models.

---

## Data Transformation

### Differencing

Differencing is applied to remove trend behavior:

[
Y_t' = Y_t - Y_{t-1}
]

This calculates the change between consecutive observations and helps stabilize the mean of the time series.

After differencing:

* Trend effects are reduced
* The series becomes more stable
* Stationarity improves

---

## Second ADF Test

After applying differencing, the ADF test is performed again.

Expected outcome:

* Lower p-value
* Stronger evidence of stationarity
* Data becomes more suitable for forecasting models

---

## Autocorrelation Analysis

ACF and PACF plots are generated to analyze relationships between current and previous observations.

These plots are commonly used when selecting parameters for:

* AR models
* MA models
* ARIMA models
* SARIMA models

---

## How to Run the Project

### 1. Clone the repository

```bash
git clone <repository-url>
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn statsmodels
```

### 3. Run the notebook

Open the notebook:

```bash
jupyter notebook
```

Run all cells to reproduce the analysis.

---

## Project Structure

```
Airline-Time-Series-Analysis/
│
├── Airline_Analysis.ipynb
├── README.md
├── requirements.txt
│
└── data/
    └── airline-passengers.csv
```

---

## Key Learnings

Through this project, the following concepts were explored:

* Time-series visualization
* Trend and seasonality analysis
* Stationarity concepts
* Augmented Dickey-Fuller testing
* Differencing techniques
* ACF/PACF interpretation
* Preparing data for forecasting models

---

## Future Improvements

Possible extensions include:

* Building ARIMA forecasting models
* Implementing SARIMA for seasonal forecasting
* Comparing forecasting accuracy using RMSE and MAE
* Applying machine learning models for passenger prediction
* Creating an interactive dashboard using Streamlit

---

## Author

**Your Name**

Data Analytics | Machine Learning | Time Series Forecasting

---

## License

This project is created for educational and analytical purposes.