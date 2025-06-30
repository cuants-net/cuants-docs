
# Distribución de Poisson

**Contar eventos que ocurren en un intervalo de tiempo o espacio**

---

## ¿Qué modela la distribución de Poisson?

La distribución de Poisson se usa para modelar la **cantidad de veces que ocurre un evento** en un **intervalo fijo** (de tiempo, espacio o unidades).

**Ejemplos**:
- Cantidad de autos que pasan por un peaje en una hora  
- Cantidad de errores en una página impresa  
- Cantidad de llamadas que recibe una central en un día  

---

## Condiciones para usar Poisson

Usamos Poisson cuando:
- Los eventos son **independientes** entre sí  
- La **tasa de ocurrencia** es constante  
- Es muy improbable que ocurran **dos eventos al mismo tiempo**  
- Se cuenta la cantidad de ocurrencias, no su magnitud  

---

## Variable aleatoria Poisson

Sea **X**: número de veces que ocurre el evento en un intervalo.

Se representa: $X \sim Po(\lambda)$

Donde:
* $\lambda$: tasa promedio de ocurrencia (media esperada por intervalo)

***

## Función de probabilidad

$P(X = x) = \frac{e^{-\lambda} \cdot \lambda^x}{x!}, \quad \text{para } x =0, 1, 2, \dots$

***

## Esperanza y varianza

Una propiedad importante de la Poisson es que:

E(X)=λ
Var(X)=λ

La media y la varianza son iguales.

***

## ¿Qué es un "intervalo" en Poisson?

El intervalo puede ser:

* **Tiempo**: 1 hora, 1 día

* **Espacio**: 1 m², 1 página

* **Cantidad**: 1 cliente, 1 transacción

La clave es que sea una **unidad fija** donde se puedan contar ocurrencias.

***

## Ejemplo práctico

Un sistema de trading lanza señales automáticas durante la jornada. En base al historial, se sabe que en promedio ocurre **0.25 señales falsas por hora**.

Durante una jornada se registran **40 horas de operación acumuladas** (por ejemplo, sumando varios días o múltiples instrumentos).

Entonces:

λ=40⋅0.25=10⇒X∼Po(10)

**X** representa el número de señales falsas detectadas en esas 40 horas.

### Preguntas:

* **a)** ¿Cuál es la probabilidad de observar exactamente **8 señales falsas**?\
  → `P(X = 8) = 0.1126`

* **b)** ¿Cuál es la probabilidad de que haya **10 o más señales falsas**?\
  → `P(X ≥ 10) = 1 − P(X ≤ 9) = 0.4579`

* **c)** ¿Cuántas señales falsas se esperan en promedio?\
  → `E(X) = λ = 10`

* **d)** ¿Con qué frecuencia se observarían **más de 15 señales falsas** en ese mismo intervalo?\
  → `P(X > 15) = 1 − P(X ≤ 15) = 0.0486`

Este último resultado (< 5%) sugiere que **ver más de 15 señales falsas es raro**. Si ocurre, puede indicar un problema con la configuración del sistema o un cambio inesperado en el mercado.


***

## Para recordar

* Poisson modela **conteos** en intervalos

* Ideal para eventos raros pero posibles

* Usa un solo parámetro: **λ** (media = varianza)

