# Summary
This Jupyter notebook consists of Pairs Trading in Crypto and Event Driven Backtesting

## Pairs Trading in Crypto

- Cointegration test is chosen for finding the correlated pairs for this pairs trading strategy, and I choose 0.5% as minimum P-value for the cointegration test, heatmap & OLS result are also used for analysis.
- I concluded the below criteria for pairs trading in this project by plotting and analysing spread between real data and regression result.
- As Rolling normalized spread of Crypto will be similar in range (1.5+1.5=3) in my graph in the notebook, but are skewed to downside because in general market drops faster than rally, so the criteria for pairs trading in this project will be:


1. [ ] if 10 minutes' rolling normalized spread > +1, short other/chsb pair, i.e. short sell other and buy chsb, both using 50% of the total capital
2. [ ] if 10 minutes' rolling normalized spread < -2, long other/chsb pair, i.e. buy other and short sell chsb, both using 50% of the total capital
3. [ ] if 10 minutes' rolling normalized spread is between -2 and +1, hold the current portfolio

## Event Driven Backtesting

An Event Driven Backtesting library backtrader is used for backtesting, the back-tester with documentation in the coding, using the criteria for pairs trading mentioned above is included the notebook

## Edge & Bottle Neck of the strategy and future improvements

- The pnl graphs show the strategy can effectively capture the temporary correlation breakdown when both coins are within a stable price range
- However, the pnl graphs show a sharp drawdown at around 6pm on 10 Jun because Spell breaks out its current price range faster than Chsb does, so the model cannot capture this kind of price range breakout movement
- Possible future improvements are adding stop loss to avoid having significant drawdown during price range breakout movement, or adding predictor function to classify that it is a price range breakout so the position can be closed immediately after the classification

## Related Project
[Stock Pairs Trading and Event Driven Backtesting](https://github.com/Hansen-chen/Pairs-Trading-and-Event-Driven-Backtesting)
