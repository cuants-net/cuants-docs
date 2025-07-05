# P-valor y significancia

## Definición

El **p-valor** (o _valor p_) es la probabilidad de obtener un resultado igual o más extremo que el observado, **suponiendo que la hipótesis nula es verdadera**.

> Es una forma de medir **cuán sorprendente es el resultado**, bajo el supuesto de que no hay efecto real.

***

## ¿Cómo se interpreta?

* Si el p-valor es **muy pequeño**, indica que sería raro observar esos datos si $H\_0$ fuera cierta. → → Se **rechaza $H\_0$**

* Si el p-valor es **grande**, los datos no son incompatibles con $H\_0$ → **No se rechaza $H\_0$**

> El p-valor **no mide la probabilidad de que la hipótesis sea cierta o falsa.**\
> Solo mide qué tan coherente son los datos con esa hipótesis.

***

## Nivel de significancia ($\alpha$)

Es un umbral que elegimos para decidir cuándo un p-valor es “suficientemente pequeño” como para rechazar $H\_0$.\
Lo más común es usar:

* $\alpha = 0.05$ (5%)

* $\alpha = 0.01$ (1%)

> Si $p < \alpha$ → se rechaza $H\_0$\
> Si $p \geq \alpha$ → no se rechaza $H\_0$

***

## Aplicación en trading cuantitativo

* Evaluar si una estrategia tiene **rentabilidad real o es puro azar**

* Comparar medias de dos activos o dos versiones de una estrategia

* Filtrar señales con significancia estadística

> Una estrategia con p-valor 0.92 frente a $H\_0: \mu = 0$\
> → probablemente está generando retornos sin evidencia estadística de que sean reales.

***

## Advertencias

* Un **p-valor bajo no garantiza que una estrategia sea buena**: puede tener alta varianza o haber sido sobreajustada.

* **El p-valor no mide el tamaño del efecto**, solo su significancia.

* Repetir tests múltiples **sin control** puede generar resultados falsamente significativos (sesgo de selección).

***

## Ejemplo aplicado

```python
from scipy import stats
import numpy as np

# Supongamos que evaluamos 50 días de retornos
retornos = np.random.normal(loc=0.001, scale=0.01, size=50)
t_stat, p_val = stats.ttest_1samp(retornos, popmean=0)

print(f"p-valor: {p_val:.4f}")
```

