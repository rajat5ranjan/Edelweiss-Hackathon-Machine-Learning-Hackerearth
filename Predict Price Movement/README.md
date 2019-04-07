![title](edel.JPG)

# Edelweiss Hackathon-Machine Learning

## Predict Price Movement

### Broad Objective

To predict short term (intraday) price movement of various stocks on the basis of its price and combination of multiple features provided.

### Data Provided:
We have provided historical 5-min tick data for a universe of more than 150 stocks. The data has the following features:

* **Mid_Price:** The price over which the returns need to be calculated
* **Date and Time**
* **46 anonymized features**

### Methodology

The algorithm will decide whether to take a position in a stock (buy/sell)
Returns calculated will be calculated as

* If there is no current position in any stocks  at any point;  the algorithm can either buy an stocks or sell an stocks ; If the stock is bought it’s called a long position, and if the stock is sold its called a short position

* If there is a long position, the algo can only square-off the position: It means it will sell the current long position and become position neutral.

* If there is a short position, the algo can only square-off the position: It means it will buy  the current short position and become position neutral.

* At 3:15 PM every day the algo mandatorily should square-off any open position.

* Return should be calculated only when the positions are square-off: If the position was long the return calculated will be equal to ((exit price- entryprice)/entryprice)

* If the position was short the return calculated will be equal to ((entryprice -exit price)/entryprice)

* For any new entry with exit the “number of trades” will be equal to 1; for example if one enters underlying4 at 1:00 PM and exits at 3:15 , number of the trade for that day for that particular stock will be 1.

* Since all the price prediction needs to be done intraday , all the positions can get opened after (9:30 AM) and should exit at or before (3:15 PM)

### Output:

It should have the following information

* Stocks wise daily return (**daily return(a)**):  Return for any day for any stock : sum of all trades return for that day: For example : for underlying 7 : the algo enters long at 1:20 PM and square-off the position at 2:40 PM: and again goes short 2:45 and square-off at 3:15. The return for that day will be the return of two trades taken that day.

* Stocks wise number of daily trades (**trades(b)**) : Trades for any day for any stock : sum of all trades for that day. For example: the trades will be equal to 2, as in the above mentioned example.

### Detailed Objective:
* You have predict the Mid-price on the testing data and then build an algorithm that predicts the Buy/Sell decisions (Long/ Short positions) for the predicted Mid-prices.

* The final optimisation problem would be to maximise  of **((a)-(0.12%)*(b)) *(b)**, this will be the criterion for selecting the price predicting algos

However, there must be a minimum of 20 trades per stocks; averaged across stock.

**Leaderboard Score : 3799006.67320 (Profit in Returns)**
