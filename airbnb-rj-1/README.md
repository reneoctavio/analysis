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

In this project, I was interested in using Airbnb data of Rio de Janeiro from April 2018 to December 2020 to understand:

1. What was the price and supply behavior before and during the pandemic?
2. Does a title in English or Portuguese impact the price?
3. What features correlate with the price? Can we predict a price? Which features matters?

## File Description

1. Data Treatment - Read data and treat it for futher use. Used langid to detect language from `name` column.
2. Data Analysis - Correlation and Time Series analysis. Verify if difference in price between Portuguese titled listing is different from those in English.
3. Preditions - Fit the treated data to a model (Random Forest), and check important features.
4. lang_pred.csv - Language preditions along with their ground truth (manually labeled by the author)

## Results

The results can be found in the [article](https://reneoctavio.medium.com/that-pandemic-shock-in-the-online-vacation-rental-market-failed-to-happen-until-it-did-bae31923686b). Check there!

## Licensing, Authors, Acknowledgements

You can download the data at [Inside Airbnb](http://insideairbnb.com/get-the-data.html).
It is licensed under a [Creative Commons CC0 1.0 Universal (CC0 1.0) "Public Domain Dedication"](http://creativecommons.org/publicdomain/zero/1.0/) license.

The BRL-USD exchange rate is from [Banco Central do Brasil](https://www.bcb.gov.br/) through [IPEA](http://ipeadata.gov.br/exibeserie.aspx?serid=38389). Public data by law.

The code is licensed under MIT license.
