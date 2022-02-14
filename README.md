# 311 Requests Prediction and Weather
Predict NYC 311 requests with adjacent weather data and quantify their impact; explore trend and insights of 311 requests.

## Notebooks
- 311_calls: data clean and exploration of 311 requests
- weather: data clean and exploration of weather
- preprocess_modeling: preprocess and join the two datasets before embarking on modeling

## Data Sources
- Up to date 311 requests and information. [Available](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9) from NYC open data. You can either download the entire dataset from the website or uses the built-in API to query the data. You can specify parameters in the API requests and therefore filter the returned result. Code to download through API available in `311_calls.ipynb`. Additionally, you can create a filtered table on NYC Open Data website and then query that filtered view directly.
- Weather dataset from 2010 to Nov 2018
