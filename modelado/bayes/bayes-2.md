# Estimación bayesiana de rendimientos diarios

**"Estimar media y volatilidad de los retornos diarios con Bayes"**

---

## 1. ¿Por qué elegimos AAPL?

AAPL (Apple Inc.) es uno de los activos más líquidos y operados del mundo.  
Nos sirve como ejemplo ideal para estimar dos cosas fundamentales:

- **¿Cuánto rinde por día en promedio?** (la media, μ)  
- **¿Qué tan variable es su rendimiento?** (la volatilidad, σ)

Estos dos valores son **la base para evaluar si una estrategia aporta valor extra o simplemente sigue el movimiento natural del activo.**

---

## 2. ¿Qué vamos a hacer?

- Tomamos los precios de cierre diarios de AAPL en el último año.
- Calculamos los **rendimientos logarítmicos diarios**.
- Usamos un enfoque bayesiano para estimar:
  - La **media diaria (μ)** del rendimiento
  - La **volatilidad diaria (σ)**

Pero esta vez, no vamos a terminar con “la media es 0.12%”.  
Vamos a terminar con una **distribución** que diga:

La media más probable está alrededor de 0.12%,
pero también podría estar entre -0.05% y 0.3%,
con cierto grado de confianza.

---

## 3. Paso a paso con código

```python
import numpy as np
import pandas as pd
import yfinance as yf
import matplotlib.pyplot as plt
import pymc as pm

# Descargar datos de AAPL
data = yf.download('AAPL', start='2023-01-01', end='2024-01-01')
data['log_ret'] = np.log(data['Close'] / data['Close'].shift(1))
rets = data['log_ret'].dropna().values

# Modelo Bayesiano
with pm.Model() as model:
    mu = pm.Normal("mu", mu=0, sigma=1)
    sigma = pm.HalfNormal("sigma", sigma=1)
    returns = pm.Normal("returns", mu=mu, sigma=sigma, observed=rets)
    trace = pm.sample(2000, tune=1000, return_inferencedata=True, random_seed=42)

```

## 4. Resultados: no es un número, es una curva

Graficamos las distribuciones posteriores de μ y σ:

```python
import arviz as az
az.plot_posterior(trace, var_names=["mu", "sigma"])
plt.show()
```

Estas curvas **son tu nuevo conocimiento**.
Y no son simétricas ni fijas:

* Se pueden mover si entran nuevos datos.

* Te muestran incertidumbre.

* Y son mucho más ricas que cualquier número puntual.

---

## 5. ¿Qué hacemos con esto?

Con estas distribuciones, ahora podés:

* Calcular intervalos creíbles:

  > “Con 95% de probabilidad, la media diaria está entre X e Y.”

* Simular futuros posibles (Monte Carlo bayesiano).

* Comparar este comportamiento **contra estrategias que prometen rendimientos mayores.**

Y lo más importante:

> **Pensar en términos de confianza y evidencia, no en certezas.**

---

## 6. Lo que viene

En la próxima ficha vamos a:

* Aprender a **leer e interpretar intervalos creíbles**

* Usarlos para decidir si una estrategia supera al activo base

* Diferenciar entre **ruido, azar y edge real**

