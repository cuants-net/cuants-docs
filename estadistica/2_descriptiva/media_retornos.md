# Media de los retornos

La **media** (también llamada promedio o valor esperado) es una medida de tendencia central. Nos indica el valor “típico” o promedio de una serie de datos.

En trading cuantitativo, la media se aplica sobre los retornos (y no sobre los precios). Nos dice **cuánto ganamos (o perdemos) en promedio, por período (día, semana, mes).

Ejemplo: Si tu estrategia tiene una media de retorno diario de 0.2%, eso no significa que siempre ganás eso. Significa que **ese es el promedio de todos tus días buenos y malos**.

***

## ¿Cómo se calcula o se usa?

Dada una serie de retornos:
$$R = [r_1, r_2, ..., r_n]$$
La media se calcula como:
$$\mu = \frac{1}{n} \sum_1^n r_i$$
En Python, se puede calcular así:

```python
import numpy as np
retornos = np.array([0.01, 0.02, -0.005, 0.015, -0.01])
media = np.mean(retornos)
print(f"Media: {media:.4f}")
```

Nota: cuando trabajamos con precios, usualmente calculamos primero los **retornos** y luego la media de esos retornos.

***

## ¿Cómo se aplica al trading cuantitativo?

La media de los retornos es una de las métricas más importantes para cualquier sistema o activo:

* **Evalúa la rentabilidad promedio** esperada

* Sirve para **comparar estrategias**

* Es parte clave del **Sharpe ratio**, que ajusta la rentabilidad por riesgo

* Puede actuar como **benchmark estadístico**: si no superás a la media histórica del mercado, ¿por qué operar?


## Ejemplo aplicado

Simulamos 100 retornos diarios de una estrategia con media teórica de 0.1% (0.001) y volatilidad del 2%:

```python
# Simulación de 100 retornos aleatorios con media 0.001
np.random.seed(42)
retornos = np.random.normal(0.001, 0.02, size=100)
media = np.mean(retornos)
print(f"Media de los retornos simulados: {media:.4f}")
```

***
## Enlaces internos

* [Varianza y desviación estándar](varianza_desviacion_estandar.md)

* [Retornos simples y logarítmicos](#)

* [Sharpe ratio](#)

* [Backtesting y análisis de rendimiento](#)

***

La media es el primer número que nos preguntamos en trading: “¿Cuánto gano?”. Pero sin saber cuánto varía ese número, esa media puede ser una ilusión. Por eso siempre viene acompañada de su hermana: la desviación.
