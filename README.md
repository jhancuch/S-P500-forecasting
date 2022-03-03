# Predicting the close price of S&P 500 Index
The goal is to predict the closing price of the S&P 500 Index for the last 20% of the dataset using three RNN tuned models. The independent variables include the volume of trades, opening price, lowest price, and highest price for each day.

## Research design and modeling methods
I utilize an 80/20 train/test split. The data is not randomly split to ensure each sequence is not shuffled but instead a clean split between the train and test set. I train three different types of models. The first model utilizes simple RNN layers and the second model uses GRU nodes. Both of these models use drop-out layers to help with the unstable gradient. I then use a simplified version of the WaveLength model for the third model. I use RMSE as the metric to measure the goodness of fit.
 
## Results and evaluation
| Metric | Model 1 | Model 2 | Model 3 |
|---     | ---     | ---     | ---     |
| Train RMSE | 0.042 | 0.014 | 0.005 | 
| Test RMSE | 0.031 | 0.019 | 0.008 |

The WaveLength model was the clear winner. Likely the structure of the model with the lower layers focused on learning short-term trends and the upper layers focused on learning long-term trends helped generate the accurate predictions with a RMSE of only .008.

## Conclusion
Attempting to predict the close of the S&P 500 would be near impossible if I did not have the opening price, max price, and close price. Otherwise I have a feeling my predictions wouldn't have been close since if predicting the movement of stock indexes was possible, everyone would be doing it.

I find that the wavelength model performed the best by far with GRU a distant second and SimpleRNN a far third. The unique ability of the WaveLength algorithmic structure to be able to focus on both short term and long term trends likely helped generate a very close prediction to the truth.
