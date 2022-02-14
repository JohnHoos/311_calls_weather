# 311 Requests Prediction and Weather
Predict NYC 311 requests with adjacent weather data and quantify their impact; explore trend and insights of 311 requests.

## Notebooks
- 311_calls: data clean and exploration of 311 requests
- weather: data clean and exploration of weather
- preprocess_modeling: preprocess and join the two datasets before embarking on modeling

## Data Sources
- Up to date 311 requests and information. [Available](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9) from NYC open data. You can either download the entire dataset from the website or uses the built-in API to query the data. You can specify parameters in the API requests and therefore filter the returned result. Code to download through API available in `311_calls.ipynb`. Additionally, you can create a filtered table on NYC Open Data website and then query that filtered view directly.
- Weather dataset from 2010 to Nov 2018 [here](https://app.box.com/s/k9tnc9tmo9dgjrbm6saw10eigsh39imw)

## Summary of findings
- A slide deck of the project can be found [here](https://docs.google.com/presentation/d/1YpVCXMxEA4nlKWsVC60pL23X2LHXiN5JuhDBT-VvzU8/edit?usp=sharing)
- 311 request volume exhibit a strong intraday and day of the week pattern. This makes it a good candidate for time-series forecasting and a poor one for linear regression models.
- 311 requests are also heavily influenced by the COVID-19 pandemic. This is clear in both how the volume changes with the onset and subsequent re-opening of the city, especially noise complaints, and how new complaint types related to the pandemic arise (e.g. non-compliance with phased reopening, non-compliance with mask mandate etc.)
- Weather data provides a small lift to prediction accuracy. In the case of a random forest model, mean temperature has the greatest impact in all the weather data variables. Autoregressive variables such as lags and trailing moving average, however, still have the strongest impact on prediciton accuracy.
- Due to multicolinearity, special attention must be paid to feature selection and model selection. I tried to alleviate this through data cleaning, feature engineering, feature selection through permutation, and finally using random forest and SARIMAX model.
- In the end, both a random forest and SARIMAX model right out of the box achieve comparable result using a walk-forward time series train-test split. More information on time series split with a fixed and expanding window can be found on Scikit-learn documentation [here](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.TimeSeriesSplit.html).
