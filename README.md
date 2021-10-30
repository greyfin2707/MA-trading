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
