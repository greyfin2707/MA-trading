# EMA-crossover trading
This code simulates an exchange trading strategy by crossing two exponential moving averages (EMA 20 and EMA 100). The strategy is based on the assumption that the crossing of the long and the short moving averages is a signal for a change of trend.

To test the performance of the strategy, the stock of the pharmaceutical company Regeneron Pharmaceuticals was selected in periods:
• From 01.01.2010 to 31.12.2019
• From 01.01.2020 to 31.12.2020
• From 01.01.2021 to 13.08.2021

A long position is opened when the short moving average crosses the long moving average (EMA 20 > EMA 100) from bottom to top. A short position is opened when the long moving average crosses above the short moving average (EMA 20 < EMA 100). When trading short, the long position is automatically closed and vice versa.

In the beginning, we upload data about the closing price of a stock using the yfinance library. Data for different time periods are assigned to the variables train, test, final. Immediately thereafter, a graph of the closing price of the stock for the specified time periods is plotted.
![image](https://user-images.githubusercontent.com/87248163/139530039-1530d4a8-d289-45b2-a6d7-409dd740f2ab.png)
