# EMA-crossover trading
This code simulates an exchange trading strategy by crossing two exponential moving averages (EMA 20 and EMA 100). The strategy is based on the assumption that the crossing of the long and the short moving averages is a signal for a change of trend.

To test the performance of the strategy, the stock of the pharmaceutical company Regeneron Pharmaceuticals was selected in periods:

• From 01.01.2010 to 31.12.2019

• From 01.01.2020 to 31.12.2020

• From 01.01.2021 to 13.08.2021

A long position is opened when the short moving average crosses the long moving average (EMA 20 > EMA 100) from bottom to top. A short position is opened when the long moving average crosses above the short moving average (EMA 20 < EMA 100). When trading short, the long position is automatically closed and vice versa.

In the beginning, we upload data about the closing price of a stock using the yfinance library. Data for different time periods are assigned to the variables train, test, final. Immediately thereafter, a graph of the closing price of the stock for the specified time periods is plotted.

![image](https://user-images.githubusercontent.com/87248163/139530039-1530d4a8-d289-45b2-a6d7-409dd740f2ab.png)

Then a function is created that adds a new column with the calculated values of exponential moving averages to the datasets, as well as adding moving average lines to the graph. The values of exponential moving averages were calculated using the technical analysis library 'ta'.

![image](https://user-images.githubusercontent.com/87248163/139530392-ceeec8f9-164e-491f-9f39-60861dbc03e4.png)

Then we create a function that determines the current position (1 - long position, -1 - short position). Columns with position values are added to the dataset, and a graph with the moments of buying and selling the stock is plotted.

![image](https://user-images.githubusercontent.com/87248163/139530542-e209a8c6-9b10-4d60-8c51-5474e81f4143.png)
![image](https://user-images.githubusercontent.com/87248163/139530557-0dd0c8d1-77f0-465d-b3e6-6f8cab365a0a.png)

After that we create a function that calculates the profitability of the strategy (value of the position multiplied by the change in price).

![image](https://user-images.githubusercontent.com/87248163/139530685-e01468dc-157c-43f1-8a83-e000e6a5ed9d.png)

Next, we create a function that calculates the indicators for backtesting the strategy: Sharpe ratio, Drawdown ratio and Maximum drawdown. The yield of 10-year US Treasuries was taken as the risk-free rate.

![image](https://user-images.githubusercontent.com/87248163/139530838-3fea0463-e76e-4398-af99-2b55e70e688e.png)

Then for comparison, data on the S&P-500 stock index was uploaded, and its returns were calculated. 

![image](https://user-images.githubusercontent.com/87248163/139530948-1c275710-640a-4a13-85bd-0ea79f1e33cd.png)

As you can see, the exponential moving average crossover trading strategy has outperformed the S&P-500 index only once (in 2021). And that happened only due to the fact that there was only one transaction of buying Regeneron shares during that year. Based on this, we can conclude that this trading strategy is not successful for this stock.
