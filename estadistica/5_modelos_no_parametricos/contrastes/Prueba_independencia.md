# Prueba de independencia de 2 vías

Analizaremos como se puede utilizar una prueba de independencia en un problema concreto.

## El problema

Un trader está evaluando una regla sencilla basada en patrones intradía. Si la primera vela de 5 minutos del día fue alcista o bajista, y si al final del día el precio cerró en positivo o negativo.Registró estos datos durante 100 sesiones.
La pregunta es: ¿Es el resultado de cierre independiente de la forma de la prima vela del día?

### Frecuencias observadas
Esta tabla resume cómo lo que el trader registró, la llamaremos tabla de frecuencias (conteos) observadas:

|                      | Cierre positivo | Cierre negativo | Total |
| -------------------- | --------------- | --------------- | ----- |
| Primera vela alcista | **28**          | **22**          | 50    |
| Primera vela bajista | **12**          | **38**          | 50    |
| **Total**            | 40              | 60              | 100   |

### Frecuencias esperadas

¿Qué frecuencias deberiamos encontrar en la tabla anterior si los eventos fueran independientes?. Para hallar estos valores nos basamos en la regla del producto para eventos independientes:

Si los dos eventos son independientes:
$P(A∩B)=P(A)*P(B)$

Si tuvieramos que completar la tabla **como si las variables fueran independientes**:

$fe = \frac{\text{total fila} \times \text{total columna}}{\text{total general}}$

De esta forma construimos una nueva tabla , que la llamamos tabla de frecuencias esperadas:

|                      | Cierre positivo | Cierre negativo | Total |
| -------------------- | --------------- | --------------- | ----- |
| Primera vela alcista | **20**          | **30**          | 50    |
| Primera vela bajista | **20**          | **30**          | 50    |
| **Total**            | 40              | 60              | 100   |

Observando las dos tablas vemos que hay diferencias que nos generan sospechas, deseamos encontrar alguna manera de poder evaluar estadisticamente esas diferencias. Para ello construimos un estadístico.

### Calculo del estadístico

Veo diferencias entre lo **observado** y lo que **esperado**. ¿Cómo puedo **medir** ese desajuste?

Necesito un estimador que: 
	- Capture la diferencia entre lo observado y lo esperado: $(fo - fe)^2$.
    - Tenga en cuenta la magnitud esperada: divido por $fe$.
    - Me dé una única medida global: sumatoria.

$\chi^2_{obs} = \sum \frac{(fo - fe)^2}{fe}$

Calculamos en cada celda:

* $(28 - 20)^2 / 20 = 3.2$
* $(22 - 30)^2 / 30 = 2.13$
* $(12 - 20)^2 / 20 = 3.2$
* $(38 - 30)^2 / 30 = 2.13$

$\chi^2_{\text{obs}} = 3.2 + 2.13 + 3.2 + 2.13 = 10.66$

Un valor alto indica que lo observado difiere bastante de lo esperado bajo independencia. Pero ¿cómo sabemos si el resultado que nos dio es alto o bajo?

### Distribución del estimador

Hasta aquí construimos un estimador que mide cuánto difieren los valores observados (fo) de los esperados (fe). Pero ese número, por sí solo, no nos dice si el desajuste es grande o pequeño. Necesitamos compararlo contra algo.

Imaginemos que repitiéramos este experimento muchas veces, obteniendo una nueva tabla en cada ocasión. En cada repetición, los valores observados (fo) cambiarían un poco, simplemente por el azar. A veces estarían más cerca de fe, otras veces más lejos. Pero si las variables fueran realmente independientes, lo esperable sería que **el valor medio de fo esté cerca de fe**.

Ahora bien, ¿cómo medimos y comparamos esas fluctuaciones?

El término $(fo-fe)^2/fe$ cumple con dos funciones:
	- Elevar al cuadrado permite captar tanto diferencias positivas como negativas, amplificando su magnitud
	- Dividir por fe permite ajustar esa diferencia a la escala esperada (una forma de normalizarla).

Si repetimos este procedimiento muchas veces bajo la hipótesis de independencia, y registramos los valores del estadístico en cada caso, veremos que siguen una forma característica: esa forma es lo que conocemos como la **distribución chi-cuadrado**.

### Grados de libertad

Para saber qué versión específica de la distribución chi-cuadrado usar, necesitamos calcular los grados de libertad:

$\text{gl} = (\text{filas}-1)(\text{columnas}-1) = 1$

Buscamos el área bajo la curva (el p-valor) a la derecha del estimador.

### Interpretación

El valor del estadístico observado fue χ2=10.66.
Para interpretar este resultado, necesitamos compararlo con un **valor crítico** obtenido de la distribución chi-cuadrado. Supongamos que trabajamos con un **nivel de significancia α=0.05**, es decir, estamos dispuestos a aceptar un 5% de error si rechazamos la hipótesis de independencia, siendo verdadera.

Consultamos la distribución chi-cuadrado con 1 grado de libertad:

$$X^2_{critico} = 3.84$$
Comparamos:
$$X²_{obs} = 10.66 > X²_{crit} = 3.84$$
**Decisión:** Como el valor observado supera ampliamente al valor crítico, **rechazamos la hipótesis de independencia.**

| Grados de libertad ($gl$) | $\alpha = 0.10$ | $\alpha = 0.05$ | $\alpha = 0.01$ |
| ------------------------- | --------------- | --------------- | --------------- |
| 1                         | 2.71            | 3.84            | 6.63            |
| 2                         | 4.61            | 5.99            | 9.21            |
| 3                         | 6.25            | 7.81            | 11.34           |

Tabla de valores críticos de χ2

### ¿qué es el p-valor?

El **p-valor** es la probabilidad de obtener un resultado **tan extremo o más extremo** que el observado, suponiendo que la hipótesis nula es verdadera.

$p-valor = P(X² > X²_{obs})$

En este caso, nos dice **qué tan raro sería observar una diferencia como la que vimos en la tabla**, si en realidad las variables fueran independientes.

En lugar de comparar el estadístico con un valor crítico, también podríamos calcular el p-valor correspondiente a χ2=10.66 y ver si es menor que α=0.05. Si lo es, también se rechaza la hipótesis de independencia.

Ambos enfoques (valor crítico y p-valor) **llevan a la misma decisión**, pero el uso del valor crítico enfatiza el razonamiento formal de las pruebas de hipótesis.


## Conclusiónes

En este ejemplo ficticio descubrimos que **la forma de la primera vela del día y el resultado final del cierre no son independientes**. Lo observamos al comparar las frecuencias reales con las esperadas bajo el supuesto de independencia, y al obtener un valor del estadístico chi-cuadrado que fue **extremadamente improbable** bajo esa hipótesis.

Por lo tanto, **existe evidencia estadística de que hay una relación entre ambas variables.**

Sin embargo, debemos tener claro que **la prueba de chi-cuadrado no mide cuán fuerte es esa relación**, solo nos indica que **hay una diferencia significativa entre lo que esperaríamos por azar y lo que efectivamente ocurrió**.

En otras palabras:

* **Sabemos que hay dependencia.**

* **Pero no sabemos cuánta.**

Es importante señalar que la prueba de independencia **no reconoce la dimensión temporal de los datos**.\
Es decir, **no distingue si una observación proviene de la semana pasada o de hace dos años**: todas tienen el mismo peso. Esto implica que la prueba **ignora que está trabajando con una serie temporal**, y por lo tanto, **omite posibles variaciones estructurales a lo largo del tiempo**.

Esta es una limitación relevante, especialmente en contextos como el trading, donde los comportamientos pueden **aparecer, desvanecerse o invertirse** en distintas etapas del mercado.

Existen metodologías más avanzadas que permiten superar estas restricciones:

* **Pruebas móviles (rolling windows):**
Aplicar la chi-cuadrado en tramos móviles (por ejemplo, de 20 días) permite detectar si la relación aparece y desaparece a lo largo del tiempo.

* **Ponderación temporal:**
Asignar mayor peso a observaciones recientes, como se hace en modelos exponenciales, reconoce que no todos los datos tienen la misma relevancia.

* **Modelos secuenciales o bayesianos dinámicos:**
Permiten actualizar la creencia sobre la existencia de una relación a medida que ingresan nuevos datos, adaptándose a posibles cambios en el patrón.




