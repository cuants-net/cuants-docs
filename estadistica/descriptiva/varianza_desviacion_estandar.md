# Varianza y desviación estándar

La **varianza** y la **desviación estándar** son medidas que cuantifican **cuánto se alejan los datos de su valor medio**.

* La varianza calcula el promedio de los cuadrados de esas diferencias.

* La desviación estándar es su raíz cuadrada, y por eso **tiene las mismas unidades que los datos** (por ejemplo, % de retorno).

Si la media nos dice “cuánto ganamos en promedio”, la desviación nos dice “cuánto suele alejarse cada día de ese promedio”.

***

## ¿Cómo se calcula?

Dada una serie de datos $x_1, x_2, ..., x_n$ con media $\hat x$:

$Varianza = \sigma^2 = \frac{1}{n} \sum_1^n (x_i - \hat x)^2$

$Desviación\, estándar = \sigma = \sqrt {Varianza}$

En estadística inferencial muchas veces se divide por  **n - 1** en lugar de **n**, para corregir el sesgo de estimación en muestras pequeñas.

***

## ¿Por qué importa en trading cuantitativo?

La desviación estándar es una de las métricas clave en todo análisis cuantitativo:

* **Mide la volatilidad**: un activo con retornos muy variables tiene alta desviación.

* **Evalúa el riesgo**: si una estrategia tiene alta desviación, sus resultados son menos previsibles.

* **Sharpe ratio**: relaciona rentabilidad media con riesgo (media / desviación).

* **Detecta eventos anómalos**: precios que se alejan más de 2 o 3 desviaciones suelen considerarse “raros”.


### Ejemplo comparativo

* Estrategia A: media = 0.1%, desviación = 2%

* Estrategia B: media = 0.1%, desviación = 0.5%

Ambas ganan lo mismo en promedio, pero la B **es más estable y predecible**. En general, preferimos estrategias con **mayor media y menor desviación**.

***

## Ejemplo en Python

Supongamos que tenemos estos retornos diarios:

```python
import numpy as np
retornos = np.array([0.01, 0.02, -0.005, 0.015, -0.01])
media = np.mean(retornos)
desvio = np.std(retornos)
print(f"Media: {media:.4f}, Desviación estándar: {desvio:.4f}")
```

Esto nos permite medir la estabilidad de la estrategia y compararla con otras.

***

## Enlaces internos

* [Media y tendencia central](#)

* [Sharpe ratio](#)

* [Volatilidad de retornos](#)

* [Tests de hipótesis](#)

***

> Este módulo es una base fundamental del pensamiento cuantitativo: toda decisión informada requiere entender no solo _cuánto se gana_, sino _cuán variable es ese resultado_.
