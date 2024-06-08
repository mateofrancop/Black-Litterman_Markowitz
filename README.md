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


## 1. Modelo Markowitz

### Análisis y Observaciones
- **Rendimientos historicos**:

A continuacion se puede obervar el rendimiento promedio anual de las acciones colombianas a lo largo de 20 años 
![](https://i.imgur.com/qnAVn4p.png[/img])

Se puede observar como la mayoria de las empresas seleccionadas tienen un rendimiento superior a la tasa libre de riesgo actual en colombia que esta en un porcentaje rondeado de 10%, sin embargo cabe destacar que una gran mayoria de estas tuvo sus mejores rendimientos en sus primeros 10 años apartir de ahi tuvieron un crecimiento mas lento incluso algunas de ellas se desvalorizaron pero al haber tenido grander rendimientos en el pasado al calcular el rendimiento salieron faborecidas. lo que puede significar un alto nivel de riesgo en el corto plazo. ademas sin tener la incertidumbre politica y economica que esta viviendo el pais actualmente.

- **Descripción del Portafolio**: El portafolio de tangencia busca maximizar el ratio de Sharpe.
- **Resultados Clave**: 
  - Expected annual return: 16.0%
  - Annual volatility: 23.4%
  - Sharpe Ratio: 0.22
 
 Al maximizar la razon de Sharpe se optine los siguientes pesos porcentuales en el portafolio optimo. 
 
![](https://i.imgur.com/xFRlopu.png[/img])

Sin embargo como se puede obervar en la tabla los pesos porcentuales se consentran en pocos activos lo que puede significar un alto nivel de riesgo al no diversificar el portafolio de una manera mas proporcionada por se hace un proceso de regulacion con un proceso de machine learning como se puede apreciar a conticuancion  

- **Regularización L2**:
  - Expected annual return: 15.6%
  - Annual volatility: 22.4%
  - Sharpe Ratio: 0.21
  
  Se puede observar como con este metodo se disminuye el riesgo
  
![](https://i.imgur.com/7JMfNqK.png[/img])

apesar de que se sigue consentrando en solo 3 activos los pesos estan mas equilibrados entre si lo que confirma la teoria de markowitz que dice que entre mayor diversificacion en el portafolio menor es el riesgo asumido.

### Frontera efficiente

![](https://i.imgur.com/g0tNqQR.png[/img])

como se observa en la frontera eficiente la estrella es el punto de tangencia el cual determina el portafolio optimo. Los puntos negros con letras en rojo son los activos que hacen parte de ese portafolio. se ve como el modelo elije activos que tengan mejor relacino riesgo/rendimiento ademas de que escoge los activos que esten por encima del punto de inicio de la linea de mercado de capitales lo que significa que se escogen activos que tengan rendimiento superior a un activo libre de riesgo.

### Insights
- **Rendimiento**: teniendo en cuanta la situacion economica del pais se puede considerar una buen rendimiento para un portafolio conformado por empresas de un pais en desarrollo.

- **Volatilidad**:  Por otro lado al tener en cuenta la volatilidad el rendimiento es bajo comparado al riesgo asumido, como se puede ver en la razon de Sharpe de 0.21 lo cual indica poca retribucion por el riesgo tomado 

### Recomendaciones
- **Optimización del Portafolio**: Al tomar deciciones de inversion no seria sensato regirse estricatamente por el portafolio aqui presentado ya este modelo no tiene en cuenta la situacion actual de cada una de estas empresas ni el contexto macroeconimico. por lo que antes de invertir se recomendaria hacer un estudio exautivo y un analisis fundamental de cada una de estas empresas. 


### Conclusión

El modelo markowitz es util para tener una idea de como ha sido el rendimineto de los activos a traves de los años y como se puede diversificar el riesgo al invertir en una variedad de activos, sin embargo, al intentar predecir el comportamiento de las acciones tiende a quedarse corto al asumir que el mercado se comportara de igual forma en el futuro. 

## 1. MODELO BLACK LITTERMAN

### Análisis y Observaciones
- **Descripción del Modelo**: El modelo Black-Litterman combina las expectativas del mercado con las opiniones del inversor.

- **Rendimiento esperado**:

PRIOR
![](https://i.imgur.com/c3Cur4j.png[/img])

Como se puede observar en la grafica los rendimientos esperados calculados por el modelos estan por debajo de la tasa libre de riesgo en colombia, por lo tanto sera necesario omitir el uso de esta para maximizar la razon de Sharpe, ya que el modelo solo distribuye peso a las acciones que estan por encima a la tasa libre de riesgo.

- **Opiniones del inversor**

views 
![](https://i.imgur.com/N46hW5w.png[/img])

en este Diccionario se puede ver las opiniones del inversionista de como sera el rendimiento anual esperado para cada una de las acciones.

- **Descripción del Portafolio**: El portafolio de tangencia busca maximizar el ratio de Sharpe.
- **Resultados Clave**: 
  - Expected annual return: 10.6%
  - Annual volatility: 21.5%
  - Sharpe Ratio: 0.40
 
 Al maximizar la razon de Sharpe se optine los siguientes pesos porcentuales en el portafolio optimo. 
 
![](https://i.imgur.com/BZF1B7H.png[/img])

Se puede obervar en la tabla los pesos porcentuales se consentran en pocos activos lo que puede significar un alto nivel de riesgo al no diversificar el portafolio de una manera mas proporcionada por se hace un proceso de regulacion con un proceso de machine learning como se puede apreciar a conticuancion  

- **Regularización L2**:
  - Expected annual return: 9.1%
  - Annual volatility: 19.1%
  - Sharpe Ratio: 0.36
  
 Se puede observar como con este metodo se disminuye el riesgo
  
![](https://i.imgur.com/IanvK31.png[/img])

![](https://i.imgur.com/ItSltVn.png[/img])

Se puede observar una mejor distribuacion de los pesos del portafolio optimo 

- **Comparacion**:

![](https://i.imgur.com/K2jrJY2.png[/img])

![](https://i.imgur.com/uIiYK2h.png[/img])

Se puede observar como en la mayoria de los casos posterior es el promedio de views y prior teniendo en cuenta la teroria de bayesiana 

### Frontera efficiente

![](https://i.imgur.com/cUTIIL7.png[/img])

como se observa en la frontera eficiente la estrella es el punto de tangencia el cual determina el portafolio optimo. Los puntos negros con letras en rojo son los activos que hacen parte de ese portafolio. 


### Insights
- **Perspectiva del Mercado**: Con este modelo la esperanza de rendimientos en el meracado colombiano es menor que con el modelo Markowitz sin embargo este modelo esta mas ajustado a la realidad actual por la que pasa el pais en donde una gran cantida de empresas estan esperimentando perdidas considerables en el valor de sus acciones.

### Recomendaciones
- **Uso del Modelo**:  Es importante aclarar que para el calculo de los wies que se incorporaran en el modelo como espectativa del inversor, es recomendable hacer un analisis fundamental y tecnico. ademas de tener un conocimiento micro y macro economico del mercado. sin embargo para este modelo se determinaron los views con base en rendimientos historicos y analisis de proyeccion con poca informacion.   

- **Mejoras Futuras**: Hacer un analisis exautivo de cada una de las empresas seleccionadas para tener proyecciones mas precisas y confiables. 

### Conclusión
- **Eficacia del los Modelos**:  The Markowitz model serves the function of reducing risk by diversifying across multiple companies; however, it is somewhat limited by relying solely on historical data. As the market is uncertain and tends to behave differently over the years, this limitation can affect its effectiveness. In contrast, the Black-Litterman model allows for adjustments based on investor opinions, making it more accurate and reliable for investment decisions.

---

Para más detalles, consulta los notebooks individuales proporcionados en este proyecto.
