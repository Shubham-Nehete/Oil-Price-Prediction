# Oil-Price-Prediction
Oil prices predictions traded on NYMEX (New York Mercantile Exchange) using time-varying approach.

As the title itself is very subjective, there are much more than just a price to predict the market
movements of the oil such as GDP growth, Inflation rate, Industrial growth, etc. along with some arbitrary
factors which cannot be collected in the form of data such as political factor (e.g. The former US President
Donald Trump’s tweet caused oil prices tumbled more than 3% at OPEC).

**Methodology:** 
Talking about the methodology, initially, I have calculated 90 days ahead returns and then aggregated
them on monthly basis and consider this as the dependent feature for prediction. Forecasting returns as
opposed to prices results in lower expectation. The primary benefit of using monthly returns data instead
of daily return data is that with monthly data, returns are at least approximately normally distributed (or,
at the very least, the simplifying assumption of normality is much less crazy for monthly returns than it is
for daily returns). Returns is a complete and scale-free summary of the investment opportunity.
Secondly, a return series are easier to handle than price series because the former have more attractive
statistical properties like a bit of normally distributed and less volatile. Additionally, the data regarding US
economy rate (percentage change), Inflation and WTI (West Texas Intermediate) percentage change
prices are considered every quarter and that is extracted from the Federal Reserve Economic Data (FRED)
website. It is an online database consisting of hundreds of thousands of economic data from scores of
national, international, public & private sources which is created and maintained by the research
department at the Federal Reserve Bank of St. Louis (USA) since 1991. This data is used because, in general
the US economy and the world’s economy runs in tandem and it acts as a good proxy for the world
economic rate, also US is the biggest consumer of an oil. In this project the crude oil prices are taken from
the NYMEX (New York Mercantile Exchange) and the benchmark for these prices is WTI which is the US
classification of oil and hence, US economy and Inflation are one of the factors affecting oil prices. This
additional data is used while dealing with linear regression as an independent features along with month
of a year. Previous quarter value is taken for the current quarter so that it would be a lagging one, not the
leading.

**Problem statement & Motivation:** 
Prediction of oil price to study/predict the market movements using time-varying approach. What can be more rewarding for
a data scientist than being able to predict market movements of any kind with their models?

**Models used:** 
In this project, I had tried the time-series models, i.e. AR (Autoregressive), ARIMA (Autoregressive Integrated
Moving Average), and FbProphet and Simple Linear Regression.

**Libraries/Tools:** 
Pandas, Numpy, Datetime, Seaborn, Matplotlib, Plotly, Sklearn, ARIMA, AR, FbProphet, Timeseries-cv.

**Conclusion:**
It is observed that almost all the time series models (AR, ARIMA, FbProphet) have performed somewhat
similar, out of that FbProphet model cross-validation result is more consistent than the other two and
linear regression. Comparing the RMSE scores of cross-validation, even though it is trivial in this case since
the oil prices are highly volatile and there are some arbitrary factors which affect the oil prices such as
political factor, natural catastrophe, etc. and these factors can’t be represented in the form of data for
analysis. Generally, in the case of time series analysis, as we keep increasing the data for modelling, the
results keep on varying and the models usually produce more accurate results when applied to a shorter
period. Still, we can compare the cross-validation results and it is found that –
1. 75% of the rmse scores (cross-validation) of the AR model is ≤ 26.98.
2. 75% of the rmse scores (cross-validation) of the ARIMA model is ≤ 27.33.
3. 75% of the rmse scores (cross-validation) of the FbProphet model is ≤ 23.92.
4. 75% of the rmse scores (cross-validation) of the Linear regression model is ≤ 30.62.
Hence, Overall, FbProphet model has performed better.

**Future scope:** 
1. Could make use of other factors for predicting oil prices.
2. Could make regularization for linear regression using ridge & lasso and can try other algorithms.
