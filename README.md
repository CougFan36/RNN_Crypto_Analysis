# RNN Crypto Analysis
## Overview
In thise exercise, we use the same Recurrent Neural Network model (LSTM) to predict the Bitcoin cryptocurreny price using data from two separate sources: the [Crypto Fear and Greed Index (FNG)](https://alternative.me/crypto/fear-and-greed-index/) and the Bitcoin closing prices pulled directly from the exchange.  The purpose behind this was to compare which model worked better, and to see if FNG (a social media sentiment score) was better at predicting BTC price then the actual closing price.

## Methodology
We used three separate rolling window periods (3 day, 5 day, and 10 day) to predict the stock price for the next day (Xt-n to predict Xt).  Our data pre-processing included scaling the data, then reshaping it so it would "fit" into our neural network.  

We used a multi-layer neural network that consisted of three different LSTM layers (the input layer and two additional hidden layers) as well as dropout layers between the LSTM layers to account for overfitting.  We then use a Dense layer as our final layer for our prediction.

## Conclusion
Across all three window frames (3 day, 5 day, and 10 day) the model using closing price had a much better loss rate.  It also seemed to predict the scores vs the actual scores better than the FNG.

Using the 3 day rolling window in the closing data seemed to provide the best predictions for the predicted closing price vs the actual closing price.
![3 Day Rolling Window - Closing Prices](Images/Closing%20Price%20Data_3%20Day%20Window.png)

So, in summary, we determined that using the closing prices was a more accurate predictor than using the social media sentiment score.  