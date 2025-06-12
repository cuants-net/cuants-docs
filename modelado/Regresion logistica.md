# Regresión logística binaria

La regresión logística es una técnica estadística esencial para modelar fenómenos donde el resultado es binario: éxito o fracaso, presencia o ausencia, sí o no. Si bien su nombre incluye "regresión", su objetivo principal es **clasificar** y **estimar probabilidades**, por eso también es ampliamente utilizada en machine learning como modelo de clasificación.
***

Explicaremos que es una regresión binaria a traves de un ejemplo, que no es una estrategia real, pero sirve para entender como se aplica en un contexto real.

Supongamos que estamos estudiando aperturas del mercado, y registramos para cada día:

* **Rango del primer minuto** (máximo - mínimo)

* **Dirección** (cierre - apertura)

* Y codificamos de forma binaria: **¿El precio subió al menos 5 puntos en los siguientes 10 minutos?**

    - Sí (éxito = 1)

    - No (fracaso = 0)

 Tendremos una tabla como la siguiente:
 
 | Rango | Dirección | Subió |
|-----------|--------------|---------|
| 1.5 | -1.2 | No|
| 2.6| 1.8 | Si |
|..... |..... |..... |


Graficamos y obtenemos:

![cfddfa38302b354fb441bfe017d8bb84.png](./cfddfa38302b354fb441bfe017d8bb84.png)
 
 

### ¿Podemos encontrar una forma de separar los exitos de los fracasos?

A simple vista, parece que hay cierta zona donde se acumulan los verdes, y otra con más rojos.

Lo que queremos es **encontrar una línea**, una frontera, que nos diga:
    - Si las condiciones del setup están de este lado, probablemente sea un exito.
    - Si están del otro, probablemente sea un fracaso.

### ¿Cómo lo hacemos?

Podríamos intentar usar una recta. Algo como:

$z = b ​+w_1​* x_1 + w_2​ * x_2$
 
Esa recta nos devuelve un número. Pero ese número **no es todavía una probabilidad**. Podría ser 10, –5 o 2.3. No tiene un significado claro como éxito o fracaso.Necesitamos transformarlo en algo útil.

![a407b74235feb6e88cd98a333b73ebb8.png](./a407b74235feb6e88cd98a333b73ebb8.png)

## La función logística

Aplicamos una función que transforma cualquier número en un valor **entre 0 y 1**.
Ese valor ahora **sí podemos interpretarlo como una probabilidad**.

$π(x)=\frac{1}{1+e^{−(β0​+β1​x1​+⋯+βk​xk​)}}$


Esa curva es la base de la regresión logística. Y nos permite responder una pregunta muy concreta, basada en datos:

> “¿Con qué probabilidad este setup tiene éxito, dadas sus condiciones técnicas?”

***

## Y eso… se puede usar para clasificar

Si π(x)>0.6, lo consideramos trade válido.\
Si π(x)<0.4, mejor lo evitamos.

Y todo esto… sin reglas fijas, sin “magia”, solo **aprendiendo de lo que ya pasó**.



***

## ¿Cómo lo hacemos?

Podríamos intentar usar una recta. Algo como:

z=β0​+β1​⋅impulso+β2​⋅volumen

Esa recta nos devuelve un número. Pero ese número **no es todavía una probabilidad**. Podría ser 10, –5 o 2.3. No tiene un significado claro como éxito o fracaso.

Necesitamos transformarlo en algo útil.


## 1. ¿Qué problemas resuelve la regresión logística?

Se utiliza cuando la **variable dependiente (Y)** es **dicotómica** (binaria), por ejemplo:

* ¿Una persona tiene una enfermedad? (sí = 1, no = 0)

* ¿Un correo es spam? (sí = 1, no = 0)

* ¿Una vaca queda preñada tras un tratamiento? (sí = 1, no = 0)

* ¿Un cliente comprará un producto? (sí = 1, no = 0)

El modelo permite:

* **Estimar la probabilidad** de que Y = 1, dado un conjunto de **variables predictoras** X.

* **Clasificar** a una observación en una categoría usando un umbral (por ejemplo, si la probabilidad > 0.5, clasificar como “positivo”).

* **Identificar factores de riesgo o protección**.

***

## 2. Diferencia con la regresión lineal

**Regresión lineal** predice un valor numérico continuo.\
**Regresión logística** predice la **probabilidad** de un evento categórico.

En regresión lineal, el modelo ajusta una **recta** (o un hiperplano si hay más de dos variables).
En regresión logística, el modelo ajusta una **curva sigmoide**, cuya forma es ideal para representar probabilidades entre 0 y 1.

Ejemplo visual:

* En regresión lineal, predecimos directamente la altura dada una edad.

* En regresión logística, predecimos la **probabilidad de ser obeso** dada una edad o un peso.

***

## 3. Fundamento matemático

### ¿Qué queremos modelar?
Queremos saber **cuál es la probabilidad** de que ocurra un evento, por ejemplo:
¿Cuál es la probabilidad de que una persona esté enferma, dado su edad y peso?

Esa probabilidad la llamamos:

$\pi(x) = P(Y=1∣X=x)$

**π(x)** es simplemente una forma de escribir la **probabilidad de que Y sea 1**, dado un conjunto de variables x. Si hay una sola variable predictora, se puede escribir π(x). Si hay más de una, π(x1​,x2​,…,xk​).

El modelo logístico parte del **logit** de la probabilidad, que se define como:

$logit(\pi(x)) = log(\frac {π(x)}{1−π(x)​}) = β0​+β1​*x1​+⋯+βk​*xk​$

A partir de ahí, se estima la probabilidad:

$π(x)=\frac{1}{1+e^{−(β0​+β1​x1​+⋯+βk​xk​)}}$

Esta forma genera una **curva sigmoide** que se aplana hacia 0 o 1, ideal para fenómenos que no cambian de forma abrupta, sino gradualmente.

***

## 4. Interpretación de coeficientes

Cada coeficiente βi​ indica cuánto cambia el **logit** por cada unidad de cambio en xi​. Pero se interpreta mejor mediante su exponencial:

$OR=e^{βi}​$

Esto nos da el **Odds Ratio**: cuántas veces más (o menos) probable es el evento al aumentar en una unidad xi​, manteniendo las demás constantes.

* OR = 1: no hay efecto.

* OR > 1: la variable aumenta el riesgo.

* OR < 1: la variable es un factor protector.

***

## 5. Clasificación y umbral

El modelo predice una **probabilidad**. Para clasificar, se fija un **umbral** (cut-off), típicamente 0.5:

* Si π(x)>0.5 → clase 1 (evento ocurre).

* Si π(x)≤0.5 → clase 0 (evento no ocurre).

Este valor se puede ajustar según se quiera priorizar **sensibilidad** (detectar todos los positivos) o **especificidad** (evitar falsos positivos).

***

## 6. Estimación: máxima verosimilitud

A diferencia de la regresión lineal (que usa mínimos cuadrados), la regresión logística utiliza el método de **máxima verosimilitud**, que busca los valores de los parámetros que hacen más probable observar los datos reales.

La **función de verosimilitud** se construye como el producto de las probabilidades estimadas para los casos positivos y las complementarias para los negativos, y luego se **maximiza**.

***

## 7. Evaluación del modelo

### Bondad de ajuste

* **Log-verosimilitud**: qué tan probable es el conjunto de datos dado el modelo.

* **Pseudo R² de McFadden**: similar al R² clásico, mide cuánta información aporta el modelo.

  * Valores > 0.2 son considerados buenos.

* **Likelihood Ratio Test**: compara modelos para ver si añadir variables mejora el ajuste significativamente.

### Capacidad predictiva (clasificatoria)

* **Curva ROC**: grafica sensibilidad vs. 1 - especificidad.

* **AUC (área bajo la curva)**:

  * AUC ≈ 0.5: modelo aleatorio.

  * AUC > 0.8: buen modelo.

***

## 8. Supuestos y buenas prácticas

* Y es binaria.

* Observaciones independientes.

* Relación lineal entre logit y predictores.

* Evitar multicolinealidad.

* Tamaño de muestra adecuado: se recomienda 20 a 30 casos por predictor.

***

## 9. Aplicaciones prácticas

La regresión logística es aplicable a múltiples disciplinas:

* **Salud**: predecir enfermedades, riesgos de complicaciones
