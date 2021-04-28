# MachineLearningProject

The readme file provides:

Project description:
We have a set of clients that will like to invest $100,000 in the stock market. Their preference is influenced by their stock appetite. We will analyze the stock data from the past 5 years (2015-2020) and suggest portfolio composition options.

Use case description: 
We intuitively selected 30 Fortune 500 companies traded on the NYSE across different industries and with different risk profiles. 
The users are the investors with the different risk appetites. 
We categorize our investors into three categories based on their risk appetite:
Low risk appetite
Medium risk appetite
High risk appetite
We create three portfolios using clustering analysis based on the investors’ risk appetites. 
We make investment recommendations based on the returns, standard deviation, the Sharpe ratio and the efficient frontier using the Monte Carlo Simulation.
The users interact with the system by indicating their risk appetite and investment recommendation system that we create will choose a portfolio and allocate stocks based on their predetermined risk appetite. This can vary also depending on their available capital. 
The information system that will use the results is a customer dashboard that displays the recommended portfolio based on the users inputted risk profile.

Useful features from your data and the descriptions of the features:
Stock closing prices - stock prices at the end of the period
Daily returns - difference between a stock’s closing daily price and beginning daily price
Annual returns - stock price at the end of the year minus stock price at the beginning of the year, adjusted for dividend
Stock prices/returns correlation - mutual connection between the stock prices/returns
Standard deviation - to measure the volatility and risk.
Daily and Monthly Variance - derived from standard deviation.
S&P 500 Prices - market benchmark 
Sharpe ratio - use the alpha, beta and standard technical risk calculations to calculate and compare an investment’s returns, along with standard deviation and  R-squared.
Alpha - excess return an investment or a portfolio of investments ushers in, above and beyond a market index or benchmark that represent the market’s broader movements.
Beta - measurement of the volatility, or systematic risk of a security or portfolio, compared to the market as a whole
Efficient frontier - use monte carlo simulation to calculate the efficient frontier by comparing the minimum variance portfolio and the sharpe ratio

Data sources that include the names of your data files and links to retrieve data available on the Internet:
We sourced the data from an open-source python package ‘pandas_datareader’. This fetches stock data directly from yahoo finance. The data is open for public use.

Description of your models: 
Clustering Analysis:
K-means clustering was used in pyspark to create and evaluate clusters based on volatility of each stock. This method of clustering aims to place stocks into clusters that have the nearest mean to the features of each stock. The features used to define the volatility of a stock were the daily and monthly variance. These are measures of how much the prices of a stock differ from their mean over the timeframe specified. These are widely accepted as the best measures of volatility of a stock in the finance industry. A feature vector was created and then standardized to allow for appropriate clustering analysis. After running the clustering algorithm, we had 3 clusters that could identify the low, medium, and high risk stocks that were in our stock list. 

Monte Carlo Simulation:
The Monte Carlo approach is a ‘brute force approach’. With this approach, we try to discover the optimal weights by simply creating a large number of random portfolios (100,000), all with varying combinations of constituent stock weightings, calculating and recording the Sharpe ratio of each of these randomly weighted portfolio and then finally extracting the details corresponding to the result with the highest value. The random weightings will be bound by the constraint that they must be between zero and one for each of the individual stocks, and all the weights must sum to one to represent an investment of 100% of the capital. The more random portfolios that we create and calculate the Sharpe ratio for, the closer we get to the weightings of the “real” optimal portfolio. We will always experience some discrepancies however as we can never run enough simulated portfolios to replicate the exact weights we are searching for. We can get close, but never exact. The results will be plotted and both the “optimal” portfolio with the highest recorded Sharpe ratio and the “minimum variance portfolio” will be highlighted and marked for identification. The “minimum variance portfolio” is the portfolio with the lowest recorded variance (which also, by definition displays the lowest recorded standard deviation or “volatility”). The values recorded are as previously mentioned, the annualized return, annualized standard deviation and annualized Sharpe ratio. After running the codes in python, a scatter plot shows the efficient frontier. The data points are colored according to their respective Sharpe ratios, with blue signifying a higher value, and red a lower value. We repeated this process for the low risk clustered stocks, medium risk cluster and the high risk cluster.

Evaluation of your Models: 
We evaluated our clustering algorithm by comparing the silhouette score between having 2-10 clusters. This type of evaluation compares the squared euclidean distances within the clusters to each other. Squared euclidean distance is the distance from the features to the mean of the cluster that it is assigned to. The goal would be to have a smaller squared euclidean distance, which indicates more accurate clusters, but without overfitting by splitting the data into too many clusters. Upon visualizing the results of our evaluation, we determined that our optimal amount of clusters to use in our analysis would be 3 clusters. 
To ensure that results from the monte carlo simulation is effective, we ran 100,000 reiterations. The more the reiterations, the more the simulation is able to get the most efficient portfolio. We then compared the minimum value at risk and the returns. The higher the returns, the higher the value at risk. 

Conclusion: 
In conclusion, we used clustering analysis to categorize a total of 30 stocks into 5 clusters. K-Means cluster algorithm is a very efficient way to create clusters through the numerous iterations. Variance was the key indicator to determining the volatility of various stocks and classifying each company into their corresponding cluster. We then used the Monte Carlo Simulation to determine the optimal portfolio for our investors by comparing the Shape Ratio, value at risk and returns. This plotted the Efficient frontier from which the most efficient portfolio was chosen. The recommendation system that we have developed will help our clients make the best investment decision based on their tolerable risk appetite. 
