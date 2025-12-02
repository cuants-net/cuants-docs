# Contraste de medias y proporciones

## Definición

Los **contrastes de medias** y **proporciones** son pruebas estadísticas que permiten comparar dos grupos o condiciones distintas para evaluar si **hay diferencias significativas** entre ellos.

¿Dos estrategias tienen diferente rendimiento promedio?
¿Una proporción de aciertos supera a otra?

***

## Tipos comunes de contrastes

### Contraste de medias (dos muestras)

* Se usa para comparar los promedios de dos grupos independientes.

* Hipótesis típica:

  * $H_0$: $\mu\_1 = \mu\_2$

  * $H_1$: $\mu\_1 \neq \mu\_2$

* Se usa el **test t de Student** (o variantes como Welch si hay varianzas distintas)

### 📌 Contraste de proporciones

* Compara la proporción de éxito entre dos grupos.

* Hipótesis típica:

  * $H_0$: $p\_1 = p\_2$

  * $H_1$: $p\_1 \neq p\_2$

* Se usa un test basado en la distribución normal (Z)

***

## Aplicación al trading cuantitativo

* Comparar el **retorno promedio** de dos estrategias

* Evaluar si una nueva versión mejora **la tasa de aciertos**

* Ver si un activo tiene rendimiento diferente en dos regímenes de mercado

* Analizar si la estrategia gana más veces que otra (proporciones)

Ejemplo:
$H_0$: “Ambas estrategias tienen el mismo retorno medio”
Resultado: p-valor = 0.02 → **rechazamos $H_0$**

***

## Ejemplo: test de diferencia de medias

```python
import numpy as np
from scipy import stats

# Simulamos retornos de dos estrategias
a = np.random.normal(0.001, 0.01, 50)
b = np.random.normal(0.002, 0.01, 50)

t_stat, p_val = stats.ttest_ind(a, b, equal_var=False)  # Welch
print(f"p-valor: {p_val:.4f}")
```

### Ejemplo: test de proporciones

```python
from statsmodels.stats.proportion import proportions_ztest

# Supongamos 20 ganadoras sobre 50 operaciones, vs. 25/50
count = np.array([20, 25])
nobs = np.array([50, 50])
stat, p_val = proportions_ztest(count, nobs)
print(f"p-valor (proporciones): {p_val:.4f}")

```
## Consideraciones importantes

* Se deben verificar supuestos: independencia, distribución, tamaño muestral

* El tamaño del efecto también importa: diferencia pequeña pero significativa ≠ útil

***
