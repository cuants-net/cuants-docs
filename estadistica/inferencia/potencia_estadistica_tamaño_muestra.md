# Potencia estadística y tamaño de muestra

## Definición clara

La **potencia estadística** de un test es la probabilidad de detectar un efecto real cuando realmente existe, es decir, de **rechazar correctamente la hipótesis nula falsa**. Se expresa como:

$Potencia=1−β$

donde β es la probabilidad de cometer un **error tipo II** (no detectar un efecto que sí existe).

El **tamaño de muestra** influye directamente en la potencia: muestras pequeñas hacen más difícil detectar efectos reales. Cuanto más grande la muestra (y menor la variabilidad), mayor será la potencia.

## Aplicación al trading cuantitativo

Cuando un trader evalúa si una estrategia es "mejor que el azar", necesita saber si sus resultados son estadísticamente significativos. Si la muestra es muy pequeña, incluso una estrategia rentable puede no superar un test de hipótesis.

Cuants utiliza este concepto para enseñar que **no basta con obtener buenos resultados: hay que demostrar que no son ruido**, y para eso se necesita potencia adecuada. Esto evita sobreinterpretar resultados en backtests con pocas operaciones.

## Ejemplo aplicado (con código en Python)

Simulamos cómo cambia la potencia según el tamaño de muestra al testear si una media es mayor que 0.

```python
import numpy as np
from scipy.stats import norm

# Supuestos del test
mu_0 = 0        # media bajo H0
mu_1 = 0.002    # media alternativa (estrategia supuestamente rentable)
sigma = 0.01
alpha = 0.05

# Función para calcular potencia de un test unilateral
def calcular_potencia(n, mu_0, mu_1, sigma, alpha):
    z_alpha = norm.ppf(1 - alpha)
    z = (mu_1 - mu_0) / (sigma / np.sqrt(n))
    beta = norm.cdf(z_alpha - z)
    return 1 - beta

# Calculamos potencia para distintos tamaños de muestra
for n in [10, 30, 50, 100, 300]:
    potencia = calcular_potencia(n, mu_0, mu_1, sigma, alpha)
    print(f"Tamaño de muestra: {n}, Potencia: {potencia:.2f}")
```

