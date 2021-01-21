# Airbnb Rio de Janeiro Analysis 1

The article:
[That pandemic shock in the online vacation rental market failed to happen; until it did!](https://reneoctavio.medium.com/that-pandemic-shock-in-the-online-vacation-rental-market-failed-to-happen-until-it-did-bae31923686b)

## Installation

### Requirements

1. Python 3
2. numpy, scipy, seaborn, matplotlib, scikit-learn, pandas, statsmodels
3. langid
4. tqdm, pendulum

### tldr;

`pip install -r requirements.txt`

## Motivation

For this project, I was interested in understanding how the vacation rental market in Brazil reacted to the pandemic.
I also wanted to verify if English titled rooms are higher priced than those in Portuguse.

## Methodology Framework

We used CRISP-DM.

### Business Understanding

We want to answer the following question regarding the vacation rental market in Rio de Janeiro.

1. What was the price and supply behavior before and during the pandemic?
2. Does a title in English or Portuguese impact the price?
3. What features correlate with the price? Can we predict a price? Which features matters?

### Data Understanding

1. We used all available data from Inside Airbnb for Rio de Janeiro from Apr-2018 to Dec-2020.
2. In Data Treatment notebook, we explored the data.
3. Got their descriptions and feature distributions.
4. We observed that we could get the listing language by detected language through the `name` column.

### Data Preparation

1. In tandem with data understanding, we treated our absent values (e.g NaNs).
2. We removed extreme `price` outliers, which occured mostly to mistyping.
3. We created new derived features, the title language and appearances.
4. We applied log transformation to some features.

### Modeling

1. The results for price and supply during the pandemic was mostly observational, by descriptive statistics and data visualization.
2. We tested the difference in price between English and Portuguese by using Welch's t-test.
3. We used Pearson's correlation to describe the linear correlation between price and other numerical features.
4. We did a regression using Random Forests to understand which features matters for determining a price.

- First three are detailed in the Data Analysis notebook, and the fourth in the Predictions notebook

### Results

1. We observed that hosts kept their listing at same price during the pandemic till a certain point.
2. We rejected the null hypothesis of equal means between the price in English and Portuguese, using Welch's t-test,
   for each scraping date.
3. The most important features are geographical, room types and reviews. (RMSE of 0.26 and R2 of 0.93)

- More detailed results are in Data Analysis and Predictions notebooks.

### Deploy

1. The main findings is written in this [report](https://reneoctavio.medium.com/that-pandemic-shock-in-the-online-vacation-rental-market-failed-to-happen-until-it-did-bae31923686b).
2. During our analysis we created several other hypotheses that can be analyzed in future works.

## File Description

1. Data Treatment - Read data and treat it for futher use. Used langid to detect language from `name` column.
2. Data Analysis - Correlation and Time Series analysis. Verify if difference in price between Portuguese titled listing is different from those in English.
3. Preditions - Fit the treated data to a model (Random Forest), and check important features.
4. lang_pred.csv - Language preditions along with their ground truth (manually labeled by the author)

## Licensing, Authors, Acknowledgements

You can download the data at [Inside Airbnb](http://insideairbnb.com/get-the-data.html).
It is licensed under a [Creative Commons CC0 1.0 Universal (CC0 1.0) "Public Domain Dedication"](http://creativecommons.org/publicdomain/zero/1.0/) license.

The BRL-USD exchange rate is from [Banco Central do Brasil](https://www.bcb.gov.br/) through [IPEA](http://ipeadata.gov.br/exibeserie.aspx?serid=38389). Public data by law.

The code is licensed under MIT license.
