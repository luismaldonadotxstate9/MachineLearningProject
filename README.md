# MachineLearningProject

The readme file provides:

Project description:

We have a set of clients that will like to invest $100,000 in the stock market
Their preference is influenced by their stock appetite
We will analyze the stock data from the past 5 years (2015-2020) and suggest portfolio composition options



Use case description: 

Intuitively selected 30 Fortune 500 companies traded on the NYSE across different industry and with different risk profiles. 
Three types of investors:
Low risk appetite
Medium risk appetite
High risk appetite
Create three portfolios using clustering analysis based on the investors’ risk appetites and a sensitivity analysis and compare the beta and alpha of these portfolios to the benchmark (S&P 500).


Useful features from your data & the descriptions of the features:

-closing price/stock price- stock prices at the end of the period

-Daily returns- difference between a stock’s closing daily price and beginning daily price

-Annual Returns-  stock price at the end of the year minus stock price at the beginning of the year, adjusted for dividend

-Stock Prices/returns correlation- mutual connection between the stock prices/returns

-S&P 500 Prices- market benchmark

-Alpha - excess return (also known as the active return), an investment or a portfolio of investments ushers in, above and beyond a market index or benchmark that represent the market’s broader movements

-Beta - measurement of the volatility, or systematic risk of a security or portfolio, compared to the market as a whole

-Sharpe ratio - use the alpha, beta and standard technical risk calculations to calculate and compare an investment’s returns, along with standard deviation and  R-squared.

Efficient frontier - use monte carlo simulation to calculate the efficient frontier by comparing the minimum variance portfolio and the Value at Risk (VaR)





Data sources that include the names of your data files and links to retrieve data available on the Internet:

We sourced the data from an open-source python package ‘pandas_datareader’.
This fetches stock data directly from yahoo finance. 


