# Markowitz and Black-Litterman Project

This project includes two main notebooks that address different aspects of portfolio optimization. Below are the detailed analyses, insights, recommendations, discoveries, observations, and conclusions for each.

### Analysis and Observations
- **Model Description**: The Markowitz model utilizes historical data for the allocation of weights in the optimal portfolio, while the Black-Litterman model combines market expectations with investor opinions. 

- **Implementation**: Implemented using the following code:

  ```python
  import yfinance as yf
  from pypfopt import EfficientFrontier, risk_models, expected_returns, plotting, objective_functions
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np
  from pypfopt import black_litterman 
  from pypfopt import BlackLittermanModel 
  from sklearn import covariance
  ```
- **Key Results**:


| Indicator                | Markowitz Model | Black-Litterman Model |
|--------------------------|------------------|------------------------|
| Expected Annual Return   |     15.6%       | 9.1%                 |
| Annual Volatility        |     22.4%       | 19.1%               |
| Sharpe Ratio             |          0.21    | 0.37                  |

## Insights
- **Market Perspective**:
The Colombian market presents several challenges for investment due to its developing nature:
	- Low liquidity
	- High volatility/high level of risk
	- Low returns
	- Limited diversification options
	- Few companies outperform a risk-free asset in Colombia
	- Limited presence of technology companies
	- High probability of currency devaluation

## 1. Markowitz Model

### Analysis and Observations
- **Historical Returns**:

Below is the average annual return of Colombian stocks over 20 years:

![](https://i.imgur.com/qnAVn4p.png)

It can be observed that the majority of the selected companies have a return higher than the current risk-free rate in Colombia, which is approximately 10%. However, it is noteworthy that many of these companies had their best returns in the first 10 years. After that, they experienced slower growth, and some even depreciated. However, due to their higher past returns, they still showed favorable results when calculating returns, indicating a high level of short-term risk. Furthermore, this analysis does not account for the current political and economic uncertainty in the country.

- **Portfolio Description**: The tangency portfolio aims to maximize the Sharpe ratio.
- **Key Results**: 
  - Expected annual return: 16.0%
  - Annual volatility: 23.4%
  - Sharpe Ratio: 0.22
 
By maximizing the Sharpe ratio, the following percentage weights are obtained in the optimal portfolio:
 
![](https://i.imgur.com/xFRlopu.png)

However, as observed in the table, the percentage weights are concentrated in a few assets, indicating a high level of risk due to insufficient diversification. To address this, a regularization process using machine learning is applied, as shown below.

- **L2 Regularization**:
  - Expected annual return: 15.6%
  - Annual volatility: 22.4%
  - Sharpe Ratio: 0.21
  
  Applying this method reduces risk as shown below:
  
![](https://i.imgur.com/7JMfNqK.png)

Although the portfolio still focuses on only three assets, the weights are more balanced, confirming Markowitz's theory that greater diversification in the portfolio leads to lower assumed risk.

### Efficient Frontier

![](https://i.imgur.com/g0tNqQR.png)

In the efficient frontier, the star denotes the tangency point, which determines the optimal portfolio. The black dots with red letters represent the assets included in that portfolio.

### Insights
- **Return**: Considering the country's economic situation, the return can be considered good for a portfolio composed of companies in a developing country.
- **Volatility**: However, when considering volatility, the return is low compared to the assumed risk, as indicated by the Sharpe ratio of 0.21, suggesting minimal return for the risk taken.

### Recommendations
- **Portfolio Optimization**: When making investment decisions, strictly adhering to the portfolio presented here may not be prudent, as this model does not consider the current situation of each of these companies or the macroeconomic context. Therefore, before investing, conducting exhaustive studies and fundamental analysis of each of these companies is recommended.

### Conclusion

The Markowitz model is useful for understanding the historical performance of assets over the years and how risk can be diversified by investing in a variety of assets. However, when attempting to predict the behavior of stocks, it falls short by assuming that the market will behave similarly in the future.


## 2. Modelo Black-Litterman

### Analysis and Observations

- **Description of the Model**: The Black-Litterman model combines market expectations with investor opinions.

- **Expected Returns**:

Prior:
![Prior Returns](https://i.imgur.com/c3Cur4j.png)

As can be seen in the graph, the expected returns calculated by the model are below the risk-free rate in Colombia. Therefore, it will be necessary to omit the use of this to maximize the Sharpe ratio, as the model only distributes weight to actions that are above the risk-free rate.

- **Investor Opinions**:

Views:
![Investor Views](https://i.imgur.com/N46hW5w.png)

In this dictionary, we can see the investor's opinions on the expected annual return for each of the actions.

- **Portfolio Description**: The tangency portfolio seeks to maximize the Sharpe ratio.

- **Key Results**:
	- Expected annual return: 10.6%
	- Annual volatility: 21.5%
	- Sharpe Ratio: 0.40

By maximizing the Sharpe ratio, the following percentage weights are obtained in the optimal portfolio.

![Portfolio Weights](https://i.imgur.com/BZF1B7H.png)

It can be observed in the table that the percentage weights are concentrated in a few assets, which may indicate a high level of risk due to the lack of diversification. However, a regularization process with machine learning is performed to achieve a more balanced distribution of weights in the portfolio.

- **Regularization L2**:
	- Expected annual return: 9.1%
	- Annual volatility: 19.1%
	- Sharpe Ratio: 0.36

![Regularization L2](https://i.imgur.com/IanvK31.png)

![Regularization L2](https://i.imgur.com/ItSltVn.png)

A better distribution of weights in the optimal portfolio can be observed.

- **Comparison**:

![](https://i.imgur.com/K2jrJY2.png)
![](https://i.imgur.com/uIiYK2h.png)

It can be observed that in most cases, the posterior is the average of views and prior, taking into account Bayesian theory.


### Efficient Frontier
![Efficient Frontier](https://i.imgur.com/cUTIIL7.png)

As observed in the efficient frontier, the star is the tangency point which determines the optimal portfolio. The black dots with red letters are the assets that are part of that portfolio.

## Insights
- **Market Perspective**: With this model, the expected return on investments in the Colombian market is lower than with the Markowitz model; however, this model is more adjusted to the current reality of the country, where many companies are experiencing significant losses in the value of their stocks.

### Recommendations
- **Use of the Model**: It is important to clarify that for the calculation of the weights to be incorporated into the model as the investor's expectation, it is recommended to perform a fundamental and technical analysis. Additionally, having a micro and macroeconomic knowledge of the market is important. However, for this model, the views were determined based on historical returns and projection analysis with limited information.

- **Future Improvements**: Conduct a thorough analysis of each of the selected companies to have more precise and reliable projections.

### Conclusion
- **Model Efficacy**: The Markowitz model serves the function of reducing risk by diversifying across multiple companies; however, it is somewhat limited by relying solely on historical data. As the market is uncertain and tends to behave differently over the years, this limitation can affect its effectiveness. In contrast, the Black-Litterman model allows for adjustments based on investor opinions, making it more accurate and reliable for investment decisions.

---

For more details, refer to the individual notebooks provided in this project.
