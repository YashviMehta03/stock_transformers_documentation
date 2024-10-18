## What is feature engineering?
Feature engineering is the process of selecting, manipulating and transforming raw data into features that can be used in supervised learning.

It requires using domain knowledge to select and transform the most relevant variables

The goal of feature engineering and selection is to improve the performance of machine learning (ML) algorithms.

## Why do we need feature engineering in stocks?

Raw stock prices can be noisy and may not always convey meaningful information for a machine learning model. Feature engineering transforms this noisy data into more informative features that allow the model to focus on key patterns, reducing the chances of being misled by noise or random fluctuations in the data.
Adding indicators provide statistical insights into market trends and behaviors, which are crucial for making informed predictions.

## Steps invlolved

### Data preparation

We have used yfinance which is a popular open source Python library that provides access to financial data on Yahoo Finance. This gave us a dataset with conventional features like open,high,low,close,volume.
  
### Exploratory Analysis

This is used to identify and summarize the main characteristics in a data set through data analysis. It helps in choosing the right features for a model.

For our prediction , we realized that momentum and volatility are two main charcteristics of a stock that significantly affect fluctuation in prices. Hence we proceeded to choose 3 indicators to be added into our dataset.


## Features added

### RSI - Relative Strength Index<br>
The relative strength index (RSI) is a momentum indicator used in technical analysis. RSI measures the speed and magnitude of a security's recent price changes to detect overvalued or undervalued conditions in the price of that security.

On a scale of 0 to 100, RSI reading of 70 or above indicates an overbought condition. A reading of 30 or below indicates an oversold condition.

### ROC - rate of change
The price rate of change (ROC) is a momentum-based technical indicator that measures the percentage change in price between the current price and the price a certain number of periods ago.

The ROC indicator is plotted against zero, with the indicator moving upwards into positive territory if price changes are to the upside, and moving into negative territory if price changes are to the downside.

It can be used to spot divergences, overbought and oversold conditions, and centerline crossovers.

### Bollinger bands 

Bollinger Bands help gauge the volatility of stocks to determine if they are over or undervalued.

Bands appear on stock charts as three lines that move with the price. The center line is the stock price's 20-day simple moving average (SMA). The upper and lower bands are set at a certain number of standard deviations, usually two, above and below the middle line.




