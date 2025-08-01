Daily Sourdough Sales Forecast
Overview
This project uses time series analysis to forecast daily sourdough bread sales for a grocery-store bakery. As the order writer for the bread section, I built this model to reduce product waste and avoid stock-outs. The model was developed using real sales data collected from 764 consecutive days at the store where I work.

Objective
To build a SARIMA model that accurately predicts the next 28 days of sourdough loaf sales and quantifies forecast uncertainty to guide better ordering decisions.

Data
The dataset includes:

Date (MM/DD/YYYY)

Loaves sold

Day of the week

Data was collected manually by photographing weekly sales reports and extracting values using a custom-built OCR pipeline in R. Final cleaning was done by hand to ensure accuracy.

Methodology
Transformed the data using log(1 + sales)

Applied seasonal differencing (weekly) and one regular difference

Used ACF/PACF to select SARIMA model orders

Compared two candidate models

Chose SARIMA(1,1,1)(0,1,1)[7] based on lower AIC and RMSE

Evaluated model with Ljung–Box tests and residual analysis

Generated 28-day forecast with 95% confidence intervals

Results
The final model forecasts average sales of about 34 loaves per day, with a margin of plus or minus 8 loaves. This level of accuracy is sufficient for operational ordering in the store’s bread section.

Limitations & Future Work
This model does not account for holidays, stock-outs, or promotions. Future improvements could include:

Holiday or promotional flags

Day-of-week dummy variables

More flexible ML-based methods once implementation skills improve

Tools Used
R, forecast, tseries, ggplot2, lubridate, dplyr, tesseract, magick
