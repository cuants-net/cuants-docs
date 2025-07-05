# Distribución Binomial

**Contar aciertos en experimentos repetidos**

***

## Antes de empezar: Bernoulli como base

Para entender la binomial, primero necesitamos conocer la distribución **Bernoulli**.

Un **ensayo de Bernoulli** es un experimento con solo dos resultados posibles:

* Éxito (1)

* Fracaso (0)

Por ejemplo:

* Lanzar una moneda: ¿salio cara (1) o no (0)?

* ¿El trade fue ganador (1) o no (0)?

Una **variable aleatoria Bernoulli** representa el resultado de un solo ensayo:

Donde:

* p: probabilidad de éxito

* 1-p : probabilidad de fracaso


***

## ¿Qué es la distribución binomial?

La distribución binomial **modela el número de éxitos en n ensayos de Bernoulli independientes**.

Se usa cuando:

* El experimento se repite n veces

* Cada repetición es independiente

* La probabilidad de éxito p se mantiene constante

* Nos interesa **contar cuántas veces ocurre el éxito**

Se representa: $X \sim Bi(n, p)$

Donde:

* X: cantidad de éxitos

* n: cantidad de ensayos

* p: probabilidad de éxito

***

## Función de probabilidad

La probabilidad de observar exactamente k éxitos es:
$$P(X=k)= \binom{n}{k} * p^k * (1−p)^{n−k}$$
Donde $\binom{n}{k}$ es el coeficiente binomial:
$$\binom{n}{k} = \frac{n!}{k!*(n-k)!}$$
***

## Esperanza y varianza

* $E(X) = n * p$

* $Var(X) = n \cdot p \cdot (1 - p) = n \cdot p \cdot q$

Estas fórmulas permiten anticipar cuántos aciertos esperamos **en promedio** y cuánta variabilidad pueden tener.

***

## Aplicación en trading cuantitativo

La binomial es útil cuando:

* Queremos medir la cantidad de **trades ganadores** entre un conjunto de operaciones

* Evaluamos si una estrategia tiene **un edge estadístico** (más aciertos que el azar)

* Hacemos un **binomial test**: ¿ganamos significativamente más del 50%?

***

## Ejemplo práctico

Una estrategia opera 100 veces y gana 58.

Si el azar esperara 50 aciertos (ósea ), ¿es 58 un resultado significativo?

```python
from scipy.stats import binom

n = 100
p = 0.5
x = 58

# P(X >= 58)
p_valor = 1 - binom.cdf(x - 1, n, p)
print(f"P-valor: {p_valor:.4f}")
```

Si el p-valor es bajo (< 0.05), puede considerarse que el resultado **no es atribuible al azar**.

***

## Visualización

```python
import matplotlib.pyplot as plt
import numpy as np

n = 100
p = 0.5
x = np.arange(0, n+1)
pmf = binom.pmf(x, n, p)

plt.bar(x, pmf, alpha=0.6)
plt.title("Distribución binomial: n=100, p=0.5")
plt.xlabel("Cantidad de aciertos")
plt.ylabel("Probabilidad")
plt.show()
```

***

## Precauciones

* La binomial **no mide el tamaño de las ganancias**, solo cuenta aciertos

* Requiere **independencia** entre operaciones (no siempre se cumple)

* Trata igual un trade que gana 1% y otro que gana 10%

***

