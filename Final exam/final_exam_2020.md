<center>
    <h1>FINANCIAL COMPUTATION WITH MATLAB</h1>
    <h3>FINAL EXAM</h3>
    <span>June 7, 2020</span>
</center>



**Instructions:**

(a) The time limit for this paper is 120 minutes.

(b) There are 6 questions in total, scored out of 100 marks.

(c) Please include MATLAB program scripts and charts along with your answers.

(d) MATLAB software must be used as the analysis tool.



**1. File `QTTN.xlsx` is the market price of SSE 50 stocks in 2016\~2019. File `IDX.xlsx` is the value of SSE 50 index at the same time period. Answer this question based on these materials. (9 marks)**

(a) Load the closing price of the 50 stocks and 1 index into MATLAB, in a total of 975 trading days. There is no missing value. (3 marks)

(b) Transform the value of the stock index to a column vector and the closing price of the 50 stocks to a matrix. (4 marks)

(c) Calculate the logarithmic rate of return of both the stock index and market prices of stocks. Output the shape of the two variables. (2 marks)



**2. Answer this question with statistics of the 50 stocks. (9 marks)**

(a) Find out the expectation of their rate of return. (2 marks)

(b)Find out the risks of these stocks, represented by standard deviation. (2 marks)

(c) Find out the number of trading days in each year of 2016 \~ 2019.

(d) If buying each stock on 2016-01-04 and selling on 2019-12-31, find out their cumulative rates of return in all 4 years and their annual rates of return in each year of 2016 \~ 2019. (5 marks)



**3. Construct a CAPM model and answer this question. (14 marks)**

(a) According to the closing price in 2018, use the classic CAPM model to estimate $\beta$ of the 50 stocks. The risk-free interest rate is 1.5%. (4 marks) 

(b) Use $\beta$ in Question 3(a) to predict the annual rate of return of the 50 stocks in 2019. Draw a histogram of the residuals of this prediction. (10 marks)



**4. Find the efficient frontier of the portfolio and answer this question. (22 marks)**

(a) Find out the covariance matrix of closing prices of the 50 stocks. (2 marks)

(b) With the cumulative rate of return and covariance based on data in 2016 \~ 2019, find out the efficient frontier of any 100 different portfolios which are combinations of the 50 stocks. Save the expectations, risks, and weight vectors of stocks in each portfolio.

(c) Draw $E-\sigma$ figure of the efficient frontier with saved data in Question 4(b). (10 marks)

(d) Add two constraints to portfolios: each stock is held at least 1 share; the portion of each stock in the portfolio is at most 10%. Draw the efficient frontier $E-\sigma$ figure. (10 marks)



**5. Analyze the compositions of SSE 50 index with machine learning methods and answer this question. (20 marks)**

(a) Using data in 2018 to fit a linear regression, predict the rate of return of SSE 50 index on each day with closing prices of the 50 stocks on the same day.

(b) Draw a bar plot of the weights of the 50 stocks in SSE 50 index by the coefficients of linear regression. (5 marks)

(c) Using data in 2016\~2018 to train a random forest model, predict the rate of return of SSE 50 index on each day with closing prices of the 50 stocks on the same day. Draw a histogram of residuals of this prediction. (10 marks)

(d) Draw a bar plot of the feature importances of the random forest in Question 5(c). (5 marks)

> **Hints**
>
> Denote the training set is consist of independent variables matrix `x_train` and dependent variable column vector `y_train`. The testing set is `x_test`, `y_test`.
>
> The minimum example of using linear regression in MATLAB:
>
> ```
> model = fitlm(x_train, y_train)
> y_pred = predict(model, x_test);
> histogram(y_pred – y_test, 'NumBins', 21)
> ```
>
> The minimum example of using random forest in MATLAB:
>
> ```
> model = fitrensemble(x_train, y_train)
> y_pred = predict(model, x_test);
> histogram(y_pred – y_test, 'NumBins', 21)
> ```
>
> For more information of the random forest model, refer to [MATLAB documentation](https://www.mathworks.com/help/stats/fitrensemble.html#d120e334185).



**6. Construct VaR models to assess financial risk and answer this question. (26 marks)**

(a) Find out the best length of lags of time series prediction for SSE 50 index in 2016 \~ 2018 with AIC and BIC methods. (6 marks)

(b) Train a GARCH model for time series prediction with SSE 50 index in 2016 \~ 2018. (5 marks)

(c) Assume the rate of return of SSE 50 index follows Gaussian distribution. Find out VaR segmented line based on the moving window of length 250. Draw a plot where one segmented line is the rate of return and the other is the lower bound of 1% VaR. (5 marks)

(d) Use the trained GARCH model to predict SSE 50 index's annual rate of return in 2019. Find out VaR segmented line by simulating 10,000 paths with the Monte-Carlo method. Assuming the rate of return of SSE 50 index follows Gaussian distribution, draw a plot where one segmented line is the rate of return and the other is the lower bound of 1% VaR. (10 marks)

