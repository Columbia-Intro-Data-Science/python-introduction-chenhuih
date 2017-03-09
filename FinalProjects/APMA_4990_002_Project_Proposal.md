
# APMA 4990_002 Data Science in Industry Final Project



#### Team Members: Bing Han, Chenhui Huang
#### Role: Chenhui - Front End Design and Implementation, Bing - Back end ML algorithm
#### Tools: Python/R/MATLAB (TBD)

## Motivation and Background

<span style="color: #black; font-family: futura; font-size: 1em;">
The idea of using the chart with candlesticks (or candles) for predicting market prices is very old. Two centuries ago, Japanese rice trader found that the candlesticks pattern chart could be used as a tool to predict future prices in a free market with a natural demand-supply balance. The method was improved later by others and today it is successfully used by many traders and investors in the stock market.
</span>

### What is candlestick chart?

<span style="color: #black; font-family: futura; font-size: 1em;">
A candlestick is presented using high, low, opening, and closing prices during a certain trading period, for example, trading day. A regular candlestick figure consists of Real Body, Upper Shadow, and Lower Shadow. The number of candlesticks that is normally used for predicting can range within 1..12. Evidently, the number of different combinations of several candlesticks in a row can be big. 
</span>

![alt text](http://globaltrendtraders.com/wp-content/uploads/2010/04/candlestick.gif)
Figure 1. The aspects of a candle

### What are some common candlestick patterns?

![alt text](https://www.forexmt4indicators.com/wp-content/uploads/2016/09/candlestick-patterns.png)
Figure 2. Common candlestick patterns

### Some common powerful candlestick pattern
#### 1. Three Line Strike

<span style="color: #black; font-family: futura; font-size: 1em;">
The bullish three line strike reversal pattern carves out three black candles within a downtrend. Each bar posts a lower low and closes near the intrabar low. The fourth bar opens even lower but reverses in a wide-range outside bar that closes above the high of the first candle in the series. The opening print also marks the low of the fourth bar. According to Bulkowski, this reversal predicts higher prices with an 84% accuracy rate.
</span>

![alt text](http://i.investopedia.com/u53687/3linestrike.png)

#### 2. Evening Stars

<span style="color: #black; font-family: futura; font-size: 1em;">
The bearish evening star reversal pattern starts with a tall white bar that carries an uptrend to a new high. The market gaps higher on the next bar but fresh buyers fail to appear, yielding a narrow range candlestick. A gap down on the third bar completes the pattern, which predicts the decline will continue to even lower lows, perhaps triggering a broader scale downtrend. According to Bulkowski, this pattern predicts lower prices with a 72% accuracy rate.
</span>

![alt text](http://i.investopedia.com/u53687/eveningstar.png)

#### 3. Abandoned Baby

<span style="color: #black; font-family: futura; font-size: 1em;">
The bullish abandoned baby reversal pattern appears at the low of a downtrend, after a series of black candles print lower lows. The market gaps lower on the next bar but fresh sellers fail to appear, yielding a narrow range doji candlestick with opening and closing prints at the same price. A bullish gap on the third bar completes the pattern, which predicts the recovery will continue to even higher highs, perhaps triggering a broader scale uptrend. According to Bulkowski, this pattern predicts higher prices with a 70% accuracy rate.
</span>

![alt text](http://i.investopedia.com/u53687/abandonbaby.png)

Reference:

[Wikipedia: Candlestick pattern](https://en.wikipedia.org/wiki/Candlestick_pattern)

[The 5 Most Powerful Candlestick Patterns](http://www.investopedia.com/articles/active-trading/092315/5-most-powerful-candlestick-patterns.asp)


## Goal

<span style="color: #black; font-family: futura; font-size: 1em;">
Our project goal is to design and implement a equity market candlestick pattern recognition web app, which the app has graphical user interface and aid users to make desicions if they should buy or sell particular stock, by giving them the likelihood whether a stock price will rise/fall based on past similar patterns. 
</span>

<span style="color: #black; font-family: futura; font-size: 1em;">
There are two major goals in this project. First, a supervised classification method will be implemented to identify some typical Candlestick patterns like: "abandoned baby", "Evening star" from the price trends of different stocks. Identifying these trends is the prerequisite of making predictions. Secondly, which is a very ambitious goal, that we hope this app can achieve the following functionalities: 
- Allow users to self-define candlestick patterns within the app
- Generate list of stocks that have similar candlestick patterns in the past
- Quantify the amount of increase/decrease of the listed stocks in x amount of time
- Give user suggestions on whether user should: buy, sell, close out, hold.
</span>

### Data Source
<span style="color: #black; font-family: futura; font-size: 1em;">
We will use daily candlechart data from [finance.yahoo.com](http://finance.yahoo.com/quote/%5EIXIC/history?p=%5EIXIC), which is presented in the standard OHLC (open, high, low, close) format along with the trading volume.
</span>

![alt text](http://www.amibroker.com/kb/wp-content/uploads/2014/10/hybrid2.png)

### Algorithm

#### A. Neural Networks
<span style="color: #black; font-family: futura; font-size: 1em;">
ANN is a field of computational science with various types of methods which tries to solve real world problems by offering strong solutions [1]. Generally, ANN is a multi-layer network which includes input layer, hidden layer and output layer shown in Fig. 4. It mirrors the basic characteristic of a human brain, and has the ability of human to learn and generate its own knowledge from its surroundings [2].
According to Kamijo and Tanigawa’s [4] research on the ANN algorithm, they had found that the ANN algorithm is able to identify and recognise candlestick patterns in the learning and training stage. Other experiment works by Naeni, Taremia and Hashemi [3], Charkha [5], Kardos and Cwiok [6] which have shown significant results through implementing the ANN algorithm for prediction, whereby the ANN algorithm is more consistent in recognising the patterns.
</span>

![alt text](figures/part1.png)
![alt text](figures/part2.png)


#### B. Support Vector Machine
<span style="color: #black; font-family: futura; font-size: 1em;">
SVM is a supervised learning model which can act upon analysing data and recognising patterns. In SVM, a hyperplane is used for classification and regression in separating the data to the nearest training data point, which is based on the categories provided by the SVM training algorithm [7]. Basically, SVM utilises a set of input data to build a model in dividing the data into distinctly defined categories [8].
</span>

Reference

[1] E.G. Alvarez, “Artificial neural networks,” pp. 1–48, 2006.

[2] G. Zhang, B.E. Patuwo, and M.Y. Hu, “Forecasting with
Artificial Neural Networks : The State of The Art,” International
Journal of Forecasting, vol. 14, no. 1, pp. 35–62, Mar. 1998.

[3] M.P. Naeini, H. Taremia, and H.H.Baradaran, “Stock Market Value Prediction Using Neural Networks,” Proc. IEEE. Computer Information Systems and Industrial Management Applications (CISIM), pp. 132–136, Oct. 2010,
doi:10.1109/CISIM.2010.5643675.

[4] K. Kamijo and T. Tanigawa, “Stock Price Pattern Recognition-
ARecurrent Neural Network Approach,” International Joint Conference on Neural Networks (IJCNN), vol. 1, no. 1, pp. 215–221, 1990.

[5] P.R. Charkha, “Stock Price Prediction and Trend Prediction Using Neural Networks,” First International Conference on Emerging Trends in Engineering and Technology, pp. 592–594. 2008.

[6] M. Kordos and A. Cwiok, “A New Approach to Neural Network Based Stock Trading Strategy,”Intelligent Data Engineering and Automated Learning, H. Yin, W. Wang, R. Smith, and J. Victor, eds.,Lecture Notes in Computer Science, Berlin: Springer-Verlag, pp. 429–436, 2011.

[7] C.J.C. Burges, “A Tutorial on Support Vector Machines for Pattern Recognition,”Data Mining and Knowledge Discovery, vol. 2, no. 2, pp. 121–167, Jun. 1998.

[8] T. Fletcher, “Support Vector Machines Explained Acknowledgments,” 2009.


```python

```
