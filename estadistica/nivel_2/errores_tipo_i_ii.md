# Errores tipo I y II, región crítica y poder del test

## Definición clara

En la inferencia estadística, los errores tipo I y II ocurren cuando se toman decisiones incorrectas al contrastar una hipótesis:

* **Error tipo I (α)**: rechazar una hipótesis nula que es verdadera (falso positivo).

* **Error tipo II (β)**: no rechazar una hipótesis nula que es falsa (falso negativo).

La **región crítica** es el conjunto de valores del estadístico para los cuales se rechaza la hipótesis nula. Se define a partir del nivel de significancia α.

El **poder del test** es la probabilidad de detectar correctamente una diferencia cuando existe:

Potencia=1−β

## Aplicación al trading cuantitativo

En trading cuantitativo, estos conceptos ayudan a **entender los riesgos de validar estrategias con datos históricos**:

* Un **error tipo I** puede hacer que aceptes una estrategia que en realidad no tiene ventaja.

* Un **error tipo II** puede hacerte descartar una estrategia ganadora por falta de evidencia.

Cuants enseña que el análisis de backtests debe incluir estos márgenes de error, especialmente cuando se prueban muchas estrategias al mismo tiempo.

## Ejemplo aplicado (con visualización)

Supongamos que estamos testeando si una estrategia tiene media > 0. Graficamos la distribución bajo H0 y H1, y la región crítica.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import norm

mu_0 = 0      # media bajo H0
mu_1 = 0.002  # media real de la estrategia
sigma = 0.01
n = 30
alpha = 0.05

# Estadísticos
se = sigma / np.sqrt(n)
x = np.linspace(-0.01, 0.01, 1000)
h0 = norm.pdf(x, mu_0, se)
h1 = norm.pdf(x, mu_1, se)
z_alpha = norm.ppf(1 - alpha, mu_0, se)

plt.plot(x, h0, label='H0 (sin ventaja)', color='blue')
plt.plot(x, h1, label='H1 (con ventaja)', color='green')
plt.axvline(z_alpha, color='red', linestyle='--', label='Región crítica')
plt.fill_between(x, 0, h0, where=(x > z_alpha), color='blue', alpha=0.3, label='Error tipo I')
plt.fill_between(x, 0, h1, where=(x < z_alpha), color='green', alpha=0.3, label='Error tipo II')
plt.title("Visualización de errores tipo I y II")
plt.legend()
plt.show()
```

