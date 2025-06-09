# Distribución binomial

**Modelar éxitos y fracasos en estrategias de trading**

***

## ¿Qué es la distribución binomial?

La **distribución binomial** describe el número de veces que ocurre un determinado resultado (llamado “éxito”) en una cantidad fija de intentos, donde cada intento es independiente y tiene dos posibles resultados: **éxito o fracaso**.

Se define por dos parámetros:

* n: número de ensayos

* p: probabilidad de éxito en cada ensayo

La fórmula de probabilidad es:

$$P(X=k)= \binom{n}{k} * p^k * (1−p)^{n−k}$$
En el contexto del trading, un “éxito” puede ser una operación ganadora, una señal correcta o una predicción acertada.

***

## Aplicación en trading cuantitativo

* Medir la cantidad de **operaciones ganadoras en un conjunto de trades**

* Evaluar si una **estrategia tiene un edge estadístico** (más aciertos que el azar)

* Comparar el resultado observado con lo esperado por azar

* Construir tests simples como el **binomial test**: ¿mi sistema gana más del 50% de las veces?

***

## Ejemplo práctico

Supongamos que una estrategia opera 100 veces y acierta 58.
¿Es esto estadísticamente significativo si el azar esperaría 50?

Podemos usar la distribución binomial para calcular la probabilidad de observar 58 o más éxitos si p=0.5:

```python
from scipy.stats import binom

# Parámetros
n = 100
p = 0.5
x = 58

# p-value: probabilidad de obtener 58 o más aciertos por azar
p_valor = 1 - binom.cdf(x - 1, n, p)
print(f"P-valor: {p_valor:.4f}")
```

Si el p-valor es bajo (< 0.05), podrías considerar que el rendimiento **no es atribuible al azar**.

***

## Visualización de la distribución

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

* La binomial **no modela magnitud de la ganancia**, solo cuenta si hubo éxito o no

* Supone **independencia** entre ensayos — muchas estrategias tienen autocorrelación

* No es sensible al tamaño de los aciertos (gana lo mismo si ganás 1% o 10%)

***

La binomial no te dice cuánto ganás, pero sí cuántas veces tenés razón. Y eso también importa.

