---
layout: post
title:  "Forecasting cryptocurrency markets"
date:   2020-04-20 09:00:00 -4000
categories: learning data 
---

Regression models can be leveraged to forecast economic markets. I used the [scikit-learn](https://scikit-learn.org/stable/index.html) library and a wealth of daily, hourly, and minute-by-minute data from [CryptoCompare](https://min-api.cryptocompare.com/) to model and predict cryptocurrency market metadata. With training, **Cryforecast** can predict highs, lows, openings, closings, and ingress and egress trading volumes for any cryptocurrency market.

<p align="center">
  <img src="/assets/high_plot.png" style="zoom:50%;">
</p>

```python
# update CryptoCompare data cache
request_hourly_data('BTC')

# gather data from cache
source = CryptoCompareHourlyHistory('./json/BTC.hourly.json')

# initialize a regressor with cached data
regressor = Regressor(source) # initialize regressor

# optimize a model to predict BTC market highs one hour in advance
regressor.optimal_model(i=0, look_ahead=1, to_path='./regressors/temp')

# plot test data for the fitted model
regressor.plot_test('./regressors/temp')
```
