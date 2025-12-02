# Test de medias emparejadas

## Introducción

Probaste una estrategia nueva durante un mes. Cada día, anotaste el resultado y lo comparaste con lo que habrías ganado usando tu estrategia anterior.

Tenés entonces **pares de datos**: el rendimiento diario con la estrategia vieja y el rendimiento con la nueva, para el mismo día.

La pregunta es:

**¿La nueva estrategia realmente mejora tus resultados?**

Ahí entra el **test de medias emparejadas**.


## Diferencias dentro de cada par

No te interesa si una estrategia da un 0.3% en promedio y la otra 0.4%.
Lo que te interesa es si **día a día la nueva gana más que la anterior**.

Entonces calculás:

* Día 1: nueva - vieja = diferencia 1

* Día 2: nueva - vieja = diferencia 2

* ...

Terminás con una lista de **diferencias diarias**.

Y si el promedio de esas diferencias es positivo y significativo, podés decir que **la nueva estrategia es mejor**.

***

## Ejemplo aplicado

Probaste ambas estrategias durante 30 días.\
Calculaste la diferencia diaria (nueva - vieja) y obtuviste:

* Media de las diferencias: $d = 0.09$

* Desviación estándar de las diferencias: $s_d = 0.25$

* Tamaño de muestra: $n = 30$

Querés ver si esa diferencia media es significativa.

### Paso 1: Calcular el error típico de la diferencia

$SE = \frac{s_d}{\sqrt{n}} = \frac{0.25}{\sqrt{30}} \approx 0.0456$

### Paso 2: Construir intervalo de confianza del 95%
Buscamos el valor crítico de la t de Student con grados de libertad:

t(0.025, 29) = 2.045

$IC = \bar{d} \pm t_{\alpha/2} \cdot SE = 0.09 \pm 2.045 \cdot 0.0456 = ( -0.003, 0.183 )$

### Interpretación

Como el intervalo **incluye el cero**, **no podés afirmar con confianza** que la estrategia nueva sea mejor.

Tal vez lo sea, pero **tus datos no alcanzan** para demostrarlo con significancia estadística.

## Visualización sugerida

Podés graficar las 30 diferencias como puntos en una línea horizontal.

* Trazá una línea en 0 (sin diferencia).

* Mostrá el promedio con una línea vertical.

* Agregá bandas de ±1 desviación estándar o el intervalo de confianza.

Esto te permite ver de un vistazo si la mayoría de las diferencias tienden a ser positivas o si están dispersas.


## ¿Cuándo conviene este enfoque?

Cuando trabajás con **pares naturales**:

* Mismos activos, antes y después de aplicar un cambio

* Mismo mercado, distinto horario

* Misma estrategia, pero con un ajuste en los parámetros

Este test te permite eliminar parte del ruido común a ambas condiciones, haciendo más sensible la comparación.


## Nota conceptual

Este enfoque clásico se basa en la diferencia de medias y asume que los datos tienen una distribución aproximadamente normal. Pero **no siempre eso se cumple**, especialmente en mercados volátiles o estrategias con resultados asimétricos.

En la sección de **modelos no paramétricos**, veremos cómo abordar esta comparación de forma más flexible, sin asumir normalidad y evaluando directamente el signo o el orden de las diferencias. Una de esas herramientas es el **test de Wilcoxon para muestras emparejadas**, que podés usar como alternativa cuando los supuestos clásicos no se cumplen.


