# Test de hipótesis

## Definición

Un **test de hipótesis** es una herramienta estadística que nos permite decidir si los datos que observamos **son coherentes con una afirmación (hipótesis nula)** o si hay evidencia para rechazarla y aceptar una alternativa.

> Es una forma sistemática de responder a preguntas del tipo:\
> “¿Esta estrategia genera realmente retornos positivos, o es puro azar?”

***

## ¿Cómo funciona?

### 1. **Se plantea una hipótesis nula** ($H\_0$)

Ejemplo: _El retorno medio es igual a cero_.

### 2. **Se plantea una hipótesis alternativa** ($H\_1$)

Ejemplo: _El retorno medio es mayor que cero_.

### 3. **Se calcula una estadística de prueba**

Usualmente basada en la media, desviación y tamaño de la muestra.

### 4. **Se obtiene un valor p**

Indica la probabilidad de obtener un resultado igual o más extremo **si la hipótesis nula fuera cierta**.

### 5. **Se toma una decisión**

Si el p-valor es menor que el nivel de significancia (por ejemplo, $\alpha = 0.05$), se **rechaza $H\_0$**.

***

## Aplicación al trading cuantitativo

Permite responder preguntas clave como:

* ¿Mi estrategia genera retornos positivos significativos?

* ¿Dos estrategias tienen medias significativamente distintas?

* ¿La diferencia de performance es real o ruido?

### Ejemplo típico:

> $H\_0$: la estrategia tiene un retorno promedio igual a cero\
> $H\_1$: el retorno promedio es mayor que cero\
> Resultado: p-valor = 0.02 → se rechaza $H\_0$ → **hay evidencia de que la estrategia es rentable**

***

## Ejemplo aplicado

```python
from scipy import stats
import numpy as np

# Supuestos: retornos simulados
retornos = np.random.normal(loc=0.001, scale=0.01, size=50)
t_stat, p_value = stats.ttest_1samp(retornos, popmean=0)

print(f"t = {t_stat:.3f}, p-value = {p_value:.4f}")
```

## Consideraciones importantes

* Un p-valor bajo no garantiza que la estrategia sea buena, solo que **no es coherente con $H\_0$**.

* Rechazar $H\_0$ no es lo mismo que demostrar $H\_1$ con certeza.

* El contexto, la muestra y la variabilidad importan tanto como el p-valor.
