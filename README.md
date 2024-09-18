# 📈 US Macroeconomic Time Series Analysis 

## Overview

This project explores US macroeconomic data by applying Vector Autoregressive (**VAR**), Vector Autoregressive Moving Average (**VARMA**), and Vector Autoregressive Moving Average with Exogenous Variables (**VARMAX**) models to forecast macroeconomic indicators. The analysis includes residual checks for normality and autocorrelation, ensuring that the models' assumptions are satisfied.

## Dataset

The dataset used in this analysis consists of US macroeconomic data from `statsmodels` library, available from [here](https://www.statsmodels.org/dev/datasets/generated/macrodata.html). The variables used in this analysis are:
- Real GDP (`realgdp`)
- Real Consumption (`realcons`)

## Notebook

The [Jupyter notebook](notebooks/macroeconomic_varmax_analysis.ipynb) is organized into the following sections:

0. **Imports**
1. **Augmented Dickey-Fuller Test**
2. **VAR Model**
3. **Granger Causality Test**
4. **VARMA Model**
5. **VARMAX Model**

## Models and Tests

### 1. Augmented Dickey-Fuller Test
Used to check the stationarity of time series data. The data needs to be stationary to produce accurate and reliable results. 

### 2. VAR Model
The Vector Autoregressive (VAR) model assumes that multiple time series influence each other. It helps in predicting macroeconomic variables like real GDP and real consumption.

#### Residual Diagnostics
- Histogram distribution is close to normal.
- Minimal deviation from normality in the Q-Q plot.
- No significant autocorrelation in the correlogram after lag zero.
- Residuals are close to a Gaussian distribution, supporting the reliability of the model for predictions.

### 3. Granger Causality Test
This test checks if one time series can predict another. In this case:
- The null hypothesis states that `realgdp` is not caused by `realcons` and vice versa.
- With a *p*-value < 0.05, we can reject the null hypothesis and conclude that `realgdp` Granger-causes `realcons`, and vice versa.

### 4. VARMA Model
VARMA is a combination of VAR and Moving Average models that handles both autoregressive and moving average components.

#### Residual Diagnostics
Similar to the VAR model, the residuals are close to Gaussian, with no significant autocorrelation after lag zero, indicating the model is appropriate for predictions.

### 5. VARMAX Model

**What is VARMAX?**

This model includes exogenous variables along with VARMA components, which ensures its ability to capture the relationships between time series and external influences.

The exogenous variables used are the other macroeconomic variables from the dataset:
- `realinv`, `realgovt`, `realdpi`, `cpi`, `m1`, `tbilrate`, `unemp`, `pop`, `infl`, `realint`   

#### Residual Diagnostics
- Close to normal distribution.
- Little deviation from normality, especially at the tails of the Q-Q plot.

## Conclusion

This project was created to apply VAR, VARMA, and VARMAX models to practice my time series analysis knowledge on prediction techniques. In general, the residual diagnostics indicate that these models can be trusted for forecasting.

***