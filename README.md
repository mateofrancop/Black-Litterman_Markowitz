# Portfolio Optimization Project

This project includes two main notebooks that address different aspects of portfolio optimization. Below are the detailed analyses, insights, recommendations, discoveries, observations, and conclusions for each.

## 1. Black-Litterman Model

### Analysis and Observations
- **Model Description**: The Black-Litterman model combines market expectations with investor opinions.
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
- **Key Results**: [Include important analysis results].

### Insights
- **Market Perspective**: [Discussion on market expectations].
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
- **Comparación con otros Modelos**: [Resultados de la comparación con otros modelos de optimización].

### Conclusión
- **Eficacia del Modelo**: El modelo Black-Litterman es efectivo para [situaciones específicas] y proporciona [beneficios].


---

Para más detalles, consulta los notebooks individuales proporcionados en este proyecto.
