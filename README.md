# Portfolio Optimization Project

This project includes two main notebooks that address different aspects of portfolio optimization. Below are the detailed analyses, insights, recommendations, discoveries, observations, and conclusions for each.

### Analysis and Observations
- **Model Description**: The Black-Litterman model combines market expectations with investor opinions, while the Markowitz model utilizes historical data for the allocation of weights in the optimal portfolio.

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

| Indicator                | Modelo Markowitz | Modelo Black-Litterman |
|--------------------------|------------------|------------------------|
| Expected Annual Return   |     15.6%       | 9.1%                 |
| Annual Volatility        |     22.4%       | 19.1%               |
| Sharpe Ratio             |          0.21    | 0.37                  |


### Insights
- **Market Perspective**: The Colombia market presents several challenges for investment due to its developing nature:
  - Low liquidity
  - High volatility/high level of risk
  - Low returns
  - Limited diversification options
  - Few companies outperform a risk-free asset in Colombia
  - Limited presence of technology companies
  - High probability of currency devaluation


- **Investor Opinions**: [Discussion on how investor opinions were integrated].

### Recommendations
- **Model Usage**


## 2. Modelo Markowitz

### Análisis y Observaciones
- **Descripción del Portafolio**: El portafolio de tangencia busca maximizar el ratio de Sharpe.
- **Resultados Clave**: 
  - Expected annual return: 16.0%
  - Annual volatility: 23.4%
  - Sharpe Ratio: 0.22

- **Regularización L2**:
  - Expected annual return: 15.6%
  - Annual volatility: 22.4%
  - Sharpe Ratio: 0.21

### Insights
- **Rendimiento**: [Discusión sobre el rendimiento del portafolio].
- **Volatilidad**: [Discusión sobre la volatilidad y su impacto].

### Recomendaciones
- **Optimización del Portafolio**: Sugerimos [recomendaciones específicas basadas en los resultados].

### Descubrimientos
- **Impacto de la Regularización**: [Resultados y discusión sobre el impacto de la regularización L2].

### Conclusión
- **Eficacia del Portafolio de Tangencia**: El portafolio de tangencia es adecuado para [situaciones específicas] y ofrece [beneficios].

## 1. MODELO BLACK LITTERMAN

### Análisis y Observaciones
- **Descripción del Modelo**: El modelo Black-Litterman combina las expectativas del mercado con las opiniones del inversor.
- **Implementación**: Se implementó utilizando [detalles específicos del código].
- **Resultados Clave**: [Incluir resultados importantes del análisis].

### Insights
- **Perspectiva del Mercado**: [Discusión sobre las expectativas del mercado].
- **Opiniones del Inversor**: [Discusión sobre cómo se integraron las opiniones del inversor].

### Recomendaciones
- **Uso del Modelo**: Recomendamos utilizar el modelo Black-Litterman para [situaciones específicas].
- **Mejoras Futuras**: [Sugerencias para mejorar el modelo].

### Descubrimientos
- **Comparison with other Models**: The Markowitz model serves the function of reducing risk by diversifying across multiple companies; however, it is somewhat limited by relying solely on historical data. As the market is uncertain and tends to behave differently over the years, this limitation can affect its effectiveness. In contrast, the Black-Litterman model allows for adjustments based on investor opinions, making it more accurate and reliable for investment decisions.


### Conclusión
- **Eficacia del Modelo**: El modelo Black-Litterman es efectivo para [situaciones específicas] y proporciona [beneficios].


---

Para más detalles, consulta los notebooks individuales proporcionados en este proyecto.
