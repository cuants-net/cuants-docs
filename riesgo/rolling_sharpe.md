# Rolling Sharpe y métricas móviles: evaluar estabilidad en el tiempo

## Definición clara

El **Rolling Sharpe** (o Sharpe móvil) es una versión dinámica del Sharpe Ratio que se calcula **en ventanas de tiempo móviles**. Permite observar **cómo evoluciona la relación entre retorno y riesgo a lo largo del tiempo**.

También se pueden aplicar otros estadísticos en forma “rolling” (móvil), como:

* Rolling volatility (volatilidad móvil)

* Rolling mean (media móvil de retornos)

* Rolling max drawdown (drawdown móvil)

Estos indicadores ayudan a detectar **cambios estructurales** en el comportamiento de una estrategia.

## Aplicación al trading cuantitativo

Un sistema puede tener un excelente Sharpe Ratio global, pero **eso no garantiza que se haya comportado bien todo el tiempo**. El Rolling Sharpe muestra **la estabilidad o la fragilidad** de ese rendimiento.

En Cuants, se usa esta métrica para:

* Detectar **deterioro progresivo** de una estrategia

* Comparar períodos “buenos” y “malos”

* Evaluar adaptabilidad o sensibilidad al entorno

## Ejemplo aplicado (con código en Python)

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

# Simulamos retornos diarios
np.random.seed(42)
returns = np.random.normal(loc=0.001, scale=0.02, size=252)
returns_series = pd.Series(returns)

# Cálculo del Rolling Sharpe (ventana de 21 días)
rolling_mean = returns_series.rolling(window=21).mean()
rolling_std = returns_series.rolling(window=21).std()
rolling_sharpe = rolling_mean / rolling_std

# Visualización
plt.figure(figsize=(10, 4))
plt.plot(rolling_sharpe, label='Rolling Sharpe (21 días)', color='darkorange')
plt.axhline(0, linestyle='--', color='gray')
plt.title("Evolución del Sharpe Ratio en el tiempo")
plt.legend()
plt.show()

```

