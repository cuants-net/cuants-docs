# Odds Ratio en tablas de 2x2
**Medir la fuerza y dirección de una asociación categórica**

Aunque la prueba de chi-cuadrado nos indica que hay una **dependencia estadística significativa**, no nos dice **cuán fuerte** es esa relación ni **en qué dirección**. Para eso, usamos una herramienta complementaria:

## Odds Ratio (OR)

El OR se utiliza en tablas 2x2 para **medir la fuerza y la dirección de la asociación** entre dos variables categóricas.

Dado el siguiente formato:
|         | Éxito (Sí) | Fracaso (No) |
| ------- | ---------- | ------------ |
| Grupo A | a          | b            |
| Grupo B | c          | d            |

El **Odds Ratio** se calcula como:$$OR = \frac{a * d}{b * c}$$

#### ¿Cómo se interpreta?
OR = 1	No hay diferencia (las probabilidades son iguales)
OR > 1	Mayor probabilidad en el Grupo A
OR < 1	Mayor probabilidad en el Grupo B

El OR no mide probabilidad directa, sino **razón de chances**. Por ejemplo:
Hay 1.5 veces más chances de éxito que de fracaso



### Intervalo de confianza del OR

Cuando calculamos un Odds Ratio (OR), lo hacemos a partir de una **muestra**. Pero si tomáramos otra muestra, los valores de la tabla cambiarían un poco, y el OR también. Por eso, además del OR puntual, suele calcularse un **intervalo de confianza (IC)** que indica un rango plausible de valores para el OR verdadero en la población.

El intervalo de confianza del OR **no es simétrico**, porque el OR está definido en escala multiplicativa. Se construye sobre el **logaritmo del OR**, que sí es aproximadamente normal:

$IC_{log(OR)} = log( OR) ± Z * SE_{log(OR)​}$

**Donde**:

* Z depende del nivel de confianza deseado (por ejemplo, Z=1.96 para 95%)

* $SE_{log(OR)}$​ es el error estándar del logaritmo del OR y se calcula así:

$SE_{log(OR)} ​= \sqrt {1/a​+1/b​+1/c​+1/d​​}$

Finalmente, se vuelve a la escala original:

$IC_{OR} ​= [e^{log(OR)−Z * SE}, e^{log(OR)+Z * SE}]$

#### ¿Cómo se interpreta?

* Si el intervalo **incluye el 1**, **no se puede afirmar** que hay asociación significativa.

* Si el intervalo **está completamente por encima o debajo de 1**, **la asociación es estadísticamente significativa** al nivel elegido.


### Ejemplo aplicado
Tomamos una tabla del análisis de patrones de apertura en trading:

|                      | Cierre positivo | Cierre negativo | Total |
| -------------------- | --------------- | --------------- | ----- |
| Primera vela alcista | 28              | 22              | 50    |
| Primera vela bajista | 12              | 38              | 50    |


Aplicamos la fórmula:

OR = 4.03

Esto significa que cuando la primera vela es alcista, la probabilidad de que el día cierre en positivo es aproximadamente 4 veces mayor que si la primera vela fue bajista.

## ¿Qué relación hay entre OR y χ2?


| Herramienta | Qué responde                           |
| ----------- | -------------------------------------- |
| $\chi^2$    | ¿Existe una asociación?                |
| OR          | ¿Qué tan fuerte es? ¿En qué dirección? |

## Conclusión

El **Odds Ratio** es una herramienta esencial cuando trabajamos con variables categóricas binarias. Mientras que la prueba de χ2 nos avisa si hay una señal estadística, el OR nos dice **cuánto vale la pena prestarle atención**.
En contextos como el trading, donde hay que decidir en base a evidencia, conocer ambas herramientas **nos permite distinguir entre ruido, señal y relevancia**.

