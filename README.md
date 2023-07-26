# Algorithmic-Trading
The objective of this project is to develop and evaluate an exchange rate trading strategy using a macroeconomic fundamental as an indicator. The evaluation of the strategy will be based on 10+ metrics and compared with the HFRI Macro Currency index.
For the purpose of our paper, we are utilizing the 3-month Interbank Rates and employing a directional forecast for the DEXUSAL–the U.S. Dollars to Australian Dollar Spot Exchange Rate.

## STRATEGY DESCRIPTION
### Kalman Filter
The strategy involves utilizing the interest rate differential between two countries to predict the future movement of the exchange rate. By setting specific parameters, the strategy determines when a trading action should be taken based on the degree of movement observed. This allows for an understanding of the direction in which the exchange rate is likely to move and aids in forecasting future market trends..
### Rules for Trading
A. We go long (buy) when the signal equals 1 and we go short (sell) when the signal equals -1. The signals are generated based on the condition that the absolute difference between the filtered interest rates and their moving average is greater than ‘z’ times the rolling standard deviation of the filtered error.
B. The exit strategy is based on the holding period defined by the parameter 'h'. The positions are held for 'h' periods after a signal is generated. For example, if a long signal is generated at time 't', then we go long and hold the position for 'h' periods, i.e., until time 't+h'. At time 't+h', we exit the position. Similarly, if a short signal is generated at time 't', then we go short and hold the position for 'h' periods, i.e., until time 't+h', and exit the position at time 't+h'.
