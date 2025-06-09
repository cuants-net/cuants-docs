# Estimadores y sesgo

**Cómo usamos datos para aproximar lo que no vemos — y por qué a veces nos equivocamos**

***

## ¿Qué es un estimador?

Un **estimador** es una fórmula o regla que usamos para **inferir una característica de una población**, a partir de una **muestra**.

**Por ejemplo:**

* La media muestral ($\hat x$) es un **estimador de la media poblacional** (μ)

* La proporción de trades ganadores en 100 operaciones es un **estimador de la tasa real de aciertos**

En trading, nunca tenemos todos los datos posibles. Siempre operamos con muestras. Por eso **necesitamos estimadores** para tomar decisiones racionales.

***

## ¿Qué es el sesgo de un estimador?

El **sesgo** (bias) es la diferencia sistemática entre el valor esperado del estimador y el valor real del parámetro poblacional.

$Sesgo=E[\hat θ]−θ$

Si el sesgo es cero, el estimador es **insesgado**.

***

### Ejemplo:

* Media muestral insesgada

  $E[\hat x]=μ$

* Varianza muestral sin corrección, **sesgada**.Por eso usamos n−1​ y no n​

***

## ¿Por qué importa esto en trading cuantitativo?

* Porque todo lo que medimos (media, volatilidad, tasas de acierto) es una **estimación basada en muestras**

* Si no entendemos el sesgo, podemos **sobreestimar** el rendimiento o subestimar el riesgo

* También afecta cómo construimos **intervalos de confianza**, **tests de hipótesis**, y validaciones de estrategia

No se trata solo de calcular. Se trata de entender **qué tan confiables son nuestras medidas.**

***

## Código en Python: estimación de media y varianza

```python
import numpy as np

retornos = np.random.normal(0.001, 0.02, size=100)

media_muestral = np.mean(retornos)
var_sesgada = np.var(retornos)  # divide por n
var_insesgada = np.var(retornos, ddof=1)  # divide por n-1

print(f"Media estimada: {media_muestral:.4%}")
print(f"Varianza sesgada: {var_sesgada:.6f}")
print(f"Varianza insesgada: {var_insesgada:.6f}")
```

***

## Buenas prácticas

* Saber si tu estimador tiene sesgo → consultá la teoría, no adivines

* Si el sesgo es pequeño y la varianza es baja, puede ser aceptable

* **No confundas precisión con veracidad**: un estimador puede ser preciso (poca variación) pero estar sesgado


