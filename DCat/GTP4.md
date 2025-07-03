# EJERCICIOS de REGRESIÓN de POISSON

Ejercicio 1. En un estudio sobre la población de un parásito se hizo un recuento de parásitos en 14
localizaciones distintas, midiendo la temperatura (ºC) y la humedad (%). Los datos obtenidos
fueron:
Realice una regresión de Poisson del conteo de parásitos en relación a la temperatura y
humedad. ¿A qué conclusión llegó, al nivel del 5%?

Número de observaciones: 14
Observaciones faltantes: 0
Iteraciones: 5 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est.	 E.E.  	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	4,45	   0,22	        4,03	        4,87	   424,43	<0,0001
°C        	0,01	4,6E-03	    -8,7E-04	        0,02	     3,13	 0,0770
%         	0,01	3,0E-03	     1,2E-03	        0,01	     5,62	 0,0178

               	 Valor  	gl
Log Likelihood 	10004,09	11
Deviance       	    1,44	11
Escala (fijada)	    1,00	  


Pruebas de hipótesis marginales

F.V.	gl	-2[L0-L1]	p-valor
°C  	 1	     3,12	 0,0773
%   	 1	     5,61	 0,0178


**β₀ = 4.45** (p < 0.0001)
Significativo al 5%
Cuando temperatura y humedad son cero (situación teórica), se espera:
e^4.45≈85.6 parasitos
No tiene sentido práctico (no existen esas condiciones), pero es la base del modelo.

**β₁ (Temperatura) = 0.01** (p = 0.077)
No significativo al 5%
El p-valor (0.077) es mayor que 0.05, **no hay evidencia suficiente para afirmar que la temperatura influye significativamente** en el conteo.

**β₂ (Humedad) = 0.01** (p = 0.0178)
Significativo al 5%
Por cada punto porcentual adicional de humedad, el número esperado de parásitos **aumenta aproximadamente un 1%**. e^0.01≈1.010


**Deviance = 1.44** con **11 grados de libertad**: indica **muy buen ajuste del modelo**.
* Pruebas marginales confirman:
**Temperatura no significativa** (p = 0.0773)
**Humedad significativa** (p = 0.0178)

---

Ejercicio 2. Considere el número (ni ) de casos nuevos reportados con melanomas en una región
determinada. Los totales Ni son los tamaños de las poblaciones que se estiman en riesgo, los
cuales pueden representar conteos de personas expuestas al riesgo. El interés es verificar si
las tasas ni/Ni, las cuales son densidades de incidencia, varían (al 5%) a través de dos grupos
de personas: quienes trabajan al aire libre o cielo abierto (aire libre) y las que trabajan bajo
techo (techo). Se recolectaron datos de 12 zonas geográficas.

Regresión Poisson

Distribución: Poisson
Función de enlace: Log
Offset: ln(Tamaño)

Variable dependiente: Casos
Número de observaciones: 12
Observaciones faltantes: 2
Iteraciones: 11 (max=20)
Tolerancia: 1E-9 (0,000000000)

      Parámetros      	Est. 	E.E.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante             	-5,45	0,07	       -5,58	       -5,31	  6203,63	<0,0001
Lugar de trabajo_techo	-0,21	0,08	       -0,37	       -0,06	     7,01	 0,0081

               	 Valor 	gl
Log Likelihood 	2543,84	10
Deviance       	  24,18	10
Escala (fijada)	   1,00	  


Pruebas de hipótesis marginales

         F.V.         	gl	-2[L0-L1]	p-valor
Lugar de trabajo_techo	 1	     6,77	 0,0093

β₁ = -0.21, p = 0.0081
Significativo al 1%
$e^{-0.21} ≈ 0.81$
Las personas que trabajan **bajo techo** tienen un **19% menos de tasa de melanoma** comparado con los que trabajan al aire libre


Supongamos que omitiesen -si los hubieren- los outliers (es decir, aquellos residuos fuera del
intervalo [-2; 2]) ¿Qué nos dicen los estimadores, con un nivel del 1%?

Al eliminar los dos posibles outliers (observaciones con residuos fuera del intervalo \[-2; 2]), el modelo se ajustó sobre 10 zonas y se obtuvo un estimador más fuerte:
**β = -0.27**, con un p-valor de **0.0009**, lo que indica que **es significativo al 1%**.

El coeficiente negativo indica que trabajar bajo techo se asocia con una **reducción significativa de la tasa de melanoma** respecto de trabajar al aire libre.\

Más específicamente, la tasa esperada **se reduce en aproximadamente un 24%** ($e^{-0.27} ≈ 0.76$).

El modelo muestra una mejora en el ajuste general: la **deviance bajó de 24,18 a 10,51**, indicando que el modelo ajusta mejor los datos sin los outliers.

---

Ejercicio 3. Los siguientes datos corresponden a las muertes por enfermedad coronaria en los últimos
años, según los registros de un determinado hospital.
¿La tasa de muerte, por dicha enfermedad, es mayor en las personas clasificadas como fumadores (1 = si, 0 = no)? Utilice un nivel de confianza del 95%.

Distribución: Poisson
Función de enlace: Log
Offset: ln(Personas)

Variable dependiente: Muertes
Número de observaciones: 10
Observaciones faltantes: 4
Iteraciones: 12 (max=20)
Tolerancia: 1E-9 (0,000000000)

 Parámetros  	 Est. 	 E.E.  	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante    	-10,58	   0,21	      -10,99	      -10,18	  2578,24	<0,0001
Edad promedio	  0,08	2,9E-03	        0,08	        0,09	   828,12	<0,0001
Fumadores    	  0,41	   0,11	        0,20	        0,62	    14,37	 0,0002

               	 Valor 	gl
Log Likelihood 	2693,87	 7
Deviance       	  69,18	 7
Escala (fijada)	   1,00	  


Pruebas de hipótesis marginales

    F.V.     	gl	-2[L0-L1]	p-valor
Edad promedio	 1	   836,79	<0,0001
Fumadores    	 1	    15,83	 0,0001

**β₀ = -10.58** (p < 0.0001)
Es **estadísticamente significativo**
Cuando la edad es 0 y la persona no fuma (caso base), la tasa esperada de muertes es:
 e^−10.58≈2.53×10^−5
 No tiene interpretación práctica, pero actúa como constante de base del modelo.

**β₁ (Edad promedio) = 0.08** (p < 0.0001)
**Significativo al 5%**
Por cada año adicional de edad, la tasa de muerte esperada **aumenta un 8.3% aproximadamente**:
e^0.08≈1.083

**β₂ (Fumador) = 0.41** (p = 0.0002)
**Significativo al 5%**
Las personas que fuman tienen una tasa de muerte por enfermedad coronaria **un 50.7% mayor** que las que no fuman:
e^0.41≈1.507

Con un nivel de confianza del 95%, se concluye que **las personas clasificadas como fumadoras presentan una tasa de muerte significativamente mayor** por enfermedad coronaria que las no fumadoras.

Específicamente, fumar está asociado con un **incremento del 50.7% en la tasa de muerte esperada**, controlando por edad y población expuesta.

---

Ejercicio 4. Supongamos que tenemos un conjunto de datos ficticios sobre el número de accidentes de
tráfico en diferentes intersecciones durante un mes. Las variables medidas fueron:

Y = número de accidentes: el nº de accidentes en cada intersección (variable discreta);
X1 = Tráfico: el nº de vehículos que pasan por la intersección durante el mes (variable discreta);
X2 =Iluminación: si la intersección tiene o no iluminación (variable dicotómica binaria: 1 si tiene
iluminación, 0 si no) y
X3 = Semáforo: si la intersección tiene o no semáforo (variable dicotómica binaria: 1 si tiene semáforo, 0 si no).

El modelo de regresión de Poisson propuesto, se puede definir como:
log(Y i ) = β 0 + β 1 X 1i + β 2 X 2i + β 3 X 3i

Imaginemos que al ajustar el modelo de regresión de Poisson, con un software estadístico,
obtenemos los siguientes resultados:

Parámetro	Estimador	E.E.	p
Intercepto (β0)	1.50	0.30	<0.01
Tráfico (β1)	0.02	0.01	0.04
Iluminación (β2)	-0.40	0.25	0.12
Semáforo (β3)	0.80	0.35	0.02

Interprete, con una significación del 5%, cada uno de los estimadores del modelo.

$\beta_0$ = 1.50:  cuando las variables regresoras son cero (X1=0, X2=0, X3=0) el numero de accidentes en la interseccion es: e^1.50 = 4.48

$\beta_1$ = 0.02: El incremento de un vehiculo por mes en el tráfico de la interseccion aumenta el numero de accidentes en un 2% (aprox). Para cada vehiulo adicional, la tasa de accidentes se multiplica por 1.02

$\beta_2$ = -0.40: No es estadisticamente significativo el 5%, lo que sugiere que la iluminacion no tiene un efecto claro sobre el numero de accidentes.
Si embargo, si fuera significativo, sugeriria que tener iluminación reduce la tasa de accidentes.

$\beta_3$ = 0.80: Este coeficiente es significativo. Y por ser: e^0,80 ≈ 2,23 indica que las intersecciones sin semáforo tienen una tasa de accidentes significativamente mayor que las intersecciones con semáforo. Un aumento, aproximado, del 120% en la tasa de accidentes se espera cuando no hay semáforo.

---

Ejercicio 5. Un investigador está interesado en predecir el número de delitos cometidos en diferentes barrios de una ciudad. Las variables medidas fueron:

Y = número de delitos: nº de delitos cometidos en cada barrio durante un mes;
X1 = Población: nº de habitantes de los barrios;
X2 = Ingreso: ingreso promedio (en %) mensual de las personas y
X3 = Desempleo: tasa de desempleados de los barrios.

Los datos obtenidos fueron:

Parámetro	Estimador	E.E.	p
Intercepto (β0)	-2.50	0.40	<0.01
Población (β1)	0.03	0.01	<0.01
Ingreso (β2)	-0.02	0.01	0.03
Desempleo (β3)	0.15	0.05	<0.01

Interprete, con una significación del 5%, cada uno de los estimadores del modelo.

**β₀ = -2.50**:
Este coeficiente es **estadísticamente significativo al 5%**
Cuando las variables regresoras son cero (Población = 0, Ingreso = 0, Desempleo = 0), el número esperado de delitos es: e^−2.5 ≈ 0. Este valor sirve como base del modelo. No se interpreta en términos prácticos (porque no existen barrios con 0 población, 0 ingreso y 0 desempleo), pero sirve como **base del modelo**.

**β₁ = 0.03**:
Este coeficiente es **estadísticamente significativo al 5%**.
Por cada habitante adicional en el barrio, el número esperado de delitos **aumenta un 3%** aproximadamente. Para cada unidad adicional en población, la tasa de delitos se multiplica por: e^0.03≈1.03

**β₂ = -0.02**:
Este coeficiente es **significativo al 5%**.
Por cada punto porcentual adicional en el ingreso promedio, el número esperado de delitos **disminuye un 2%** aproximadamente. La tasa de delitos se multiplica por:
e^−0.02≈0.98

**β₃ = 0.15**:
Este coeficiente es **significativo al 5%**.\
Por cada punto porcentual adicional en la tasa de desempleo, el número esperado de delitos **aumenta un 16.2%** aproximadamente.\
La tasa se multiplica por:
e^0.15≈1.162


---

Ejercicio 6. Considere la variable dependiente que cuenta el número de Casos con cáncer de piel, por
exposición al sol, obtenidos en dos áreas distintas. La población de cada área fue dividida en
ocho grupos etarios. En este ejemplo se involucran dos variables explicativas: la edad y la
localización. Ambas variables se han considerado como categóricas y mediante variables
ficticias o dummy (con 85 o +, como base) se pueden representar los ocho grupos etarios y
una para localización (con Área 1, como base).
¿Cómo interpretaría los resultados obtenidos, con una significación del 5%?

Área_2 = 0.80 (p < 0.0001)
Significativo al 5%
La tasa de cáncer en Área 2 es significativamente mayor que en Área 1
Se estima que es:
𝑒^0.80=2.23  veces mayor
Es decir, más del doble de casos esperados, a igual grupo etario y tamaño de población

Grupos etarios
Todos los coeficientes son negativos, porque se comparan contra el grupo de mayores de 85 años, que es la categoría base.

Grupo Etario	Estimador	p-valor	Interpretación
15-24	-6.18	<0.0001	La tasa esperada es muy inferior:
e^–6.18 ≈ 0.002 → prácticamente nula			
25-34	-3.55	<0.0001	e^–3.55 ≈ 0.028 → tasa 97% menor
35-44	-2.33	<0.0001	e^–2.33 ≈ 0.097 → tasa 90% menor
45-54	-1.58	<0.0001	e^–1.58 ≈ 0.206 → tasa 79% menor
55-64	-1.09	<0.0001	e^–1.09 ≈ 0.336 → tasa 66% menor
65-74	-0.53	<0.0001	e^–0.53 ≈ 0.59 → tasa 41% menor
75-84	-0.12	0.2809	No significativa → no se puede afirmar que tenga distinta tasa que el grupo base (85 o +)

---

Ejercicio 7. La dueña de un comercio está interesada en determinar si el número de ventas realizadas,
durante las cinco últimas semanas, fue satisfactorio. Para ello, además del nº de productos
vendidos (Ventas), se midieron las siguientes variables: Publicidad: nº de publicaciones en
redes sociales y Visitas: nº de personas que visitaron el comercio. Los datos obtenidos fueron:
¿Tuvo algún efecto en las ventas, al nivel del 5%, la publicidad en redes sociales?

Regresión Poisson

Distribución: Poisson
Función de enlace: Log

Variable dependiente: Ventas
Número de observaciones: 5
Observaciones faltantes: 11
Iteraciones: 5 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	 Est.  	 E.E.  	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	   2,96	   0,46	        2,06	        3,86	    41,41	<0,0001
Publicidad	   0,06	   0,03	     2,8E-03	        0,12	     4,21	 0,0401
Visitas   	3,1E-03	2,4E-03	    -1,7E-03	        0,01	     1,62	 0,2032

               	Valor 	gl
Log Likelihood 	878,81	 2
Deviance       	  1,80	 2
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

   F.V.   	gl	-2[L0-L1]	p-valor
Publicidad	 1	     4,48	 0,0344
Visitas   	 1	     1,62	 0,2025

Interpretación del coeficiente de **Publicidad**

* El coeficiente **β = 0.06** indica que **por cada publicación adicional en redes sociales**, el número esperado de ventas **aumenta en un 6.2% aproximadamente**: e^0.06≈1.062

* Como el **p-valor es 0.0401**, y se pidió un nivel de significación del 5%, **el efecto de la publicidad es significativo**.

* Las **visitas al comercio no resultan significativas** en este modelo (p = 0.2032).


---

Ejercicio 8. Supongamos que estamos modelando el número de llamadas de emergencia (Llamadas) que
se reciben cada trimestre en cierta ciudad. Las variables explicativas son: Temperatura: la
temperatura media en ºC durante el trimestre; Criminalidad: nº de crímenes reportados en la
ciudad durante el trimestre y Eventos: número de eventos (por ejemplo, conciertos, festivales,
etc.) que tuvieron lugar durante el trimestre. Después de ajustar los datos a un modelo de
Poisson, obtenemos los siguientes resultados:

Parámetro	Estimador	E.E.	p
Intercepto (β0)	3.20	0.35	<0.01
Temperatura (β1)	0.05	0.02	0.02
Criminalidad (β2)	0.10	0.03	0.01
Eventos (β3)	0.70	0.25	0.05

Interprete, con una significación del 2,5%, cada uno de los estimadores del modelo.

Y: nro. Llamadas
X1: Temperatura
X2: nro. Crimenes
X3: nro. Eventos

**β₀ = 3.20**:
Este coeficiente es **estadísticamente significativo al 2,5%**.\
Cuando las variables regresoras son cero (Temperatura = 0, Criminalidad = 0, Eventos = 0), el número esperado de llamadas de emergencia es: e^3.20≈24.53
Este valor representa la base del modelo, aunque no es realista en términos prácticos porque las regresoras no suelen ser cero al mismo tiempo.

**β₁ = 0.05**:
Este coeficiente tiene **p = 0.02**, por lo tanto es **significativo al 2,5%**.
Por cada grado Celsius adicional en la temperatura media del trimestre, el número esperado de llamadas de emergencia **aumenta un 5% aproximadamente**. La tasa se multiplica por:
e^0.05≈1.051

**β₂ = 0.10**:
Este coeficiente es **significativo al 2,5%** (p = 0.01).
Por cada crimen adicional reportado en el trimestre, el número esperado de llamadas de emergencia **aumenta un 10.5% aproximadamente**. La tasa se multiplica por: e^0.10≈1.105

**β₃ = 0.70**:
Este coeficiente **no es significativo al 2,5%**, ya que su p-valor es 0.05 (> 0.025).
Por lo tanto, **no hay evidencia suficiente para afirmar que el número de eventos tiene un efecto claro sobre las llamadas de emergencia**. Si fuera significativo, sugeriría que más eventos están asociados con un aumento importante en las llamadas:
e^0.70≈2.01 (lo que implicaría un incremento del 101%).

---

Ejercicio 9. El presente estudio retrospectivo, no da informaron sobre el número de muertes por SIDA en
un hospital público, en períodos trimestrales, desde enero de 1983 hasta junio de 1986. Para
ello se consideró, como variable dependiente, muerte y, como regresora, trimestre.
Supongamos que omitiesen -si los hubieren- los outliers (es decir, aquellos residuos fuera del
intervalo [-2; 2]) ¿Qué nos dicen los estimadores, con un nivel del 1%?

Variable dependiente: Muertes
Número de observaciones: 10
Observaciones faltantes: 2
Iteraciones: 8 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-0,21	0,36	       -0,91	        0,50	     0,33	 0,5661
Trimestre 	 0,29	0,03	        0,23	        0,35	    97,53	<0,0001

               	Valor 	gl
Log Likelihood 	327,36	 8
Deviance       	  3,86	 8
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

  F.V.   	gl	-2[L0-L1]	p-valor
Trimestre	 1	   163,87	<0,0001

**β₀ = –0.21** (p = 0.5661)
**No es significativo** al 1% ni al 5%.
Representa el número de muertes esperadas en el trimestre 0 (ficticio).
No tiene interpretación práctica, simplemente funciona como base del modelo.

**β₁ (Trimestre) = 0.29** (p < 0.0001)
**Muy significativo al 1%**
Indica que **por cada trimestre que pasa**, el número esperado de muertes **aumenta un 33.6% aproximadamente**:  e^0.29≈1.336

Es decir, el modelo indica un **crecimiento acelerado** en el número de muertes por SIDA con el paso del tiempo.

---

Ejercicio 10. Analice el siguiente conjunto de datos que contiene el número de personas que solicitaron
un préstamo personal (Préstamo), según el rango etario (Etario) en las dos sucursales -en
localidades distintas- de un mismo Banco (Sucursal), durante los meses de diciembre y
enero del año pasado.
¿Qué conclusión puede extraer de los estimadores obtenidos, al 0,10?

Regresión Poisson

Distribución: Poisson
Función de enlace: Log
Offset: ln(Población)

Variable dependiente: Préstamo
Número de observaciones: 12
Observaciones faltantes: 4
Iteraciones: 11 (max=20)
Tolerancia: 1E-9 (0,000000000)

 Parámetros 	Est. 	E.E.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante   	-4,39	0,19	       -4,76	       -4,02	   538,18	<0,0001
Sucursal_B  	-0,13	0,13	       -0,40	        0,13	     0,97	 0,3256
Etario_50-54	-1,49	0,25	       -1,98	       -1,00	    35,31	<0,0001
Etario_55-59	-0,32	0,25	       -0,82	        0,17	     1,64	 0,2007
Etario_60-64	 0,10	0,24	       -0,36	        0,56	     0,17	 0,6773
Etario_65-69	 0,34	0,23	       -0,11	        0,80	     2,16	 0,1420
Etario_70-74	 0,44	0,24	       -0,03	        0,91	     3,37	 0,0662

               	Valor 	gl
Log Likelihood 	435,19	 5
Deviance       	  9,90	 5
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

    F.V.    	gl	-2[L0-L1]	p-valor
Sucursal_B  	 1	     0,97	 0,3248
Etario_50-54	 1	    32,03	<0,0001
Etario_55-59	 1	     1,63	 0,2021
Etario_60-64	 1	     0,17	 0,6766
Etario_65-69	 1	     2,19	 0,1388
Etario_70-74	 1	     3,41	 0,0648


**Etario 50–54**
**Muy significativa**
e^(–1.49) ≈ 0.225 → la tasa de solicitud de préstamos es un **77.5% menor** que en el grupo 75 o más.

**Etario 70–74**
**Significativa al 10%**
e^(0.44) ≈ 1.55 → la tasa de solicitud es **un 55% mayor** que en el grupo de 75 o más.


---

Ejercicio 11. Se quiere determinar si el número de averías sufridas por barcos, en los últimos diez años,
están relacionadas con el año de construcción (1975, 1980, 1985 y 1990), el nº de viajes
realizados y clasificados por tipo de buque (A = carga general, B = portacontenedores, C =
graneleros, D = frigoríficos y D = petroleros). Los datos de las variables medidas, están en la
presente tabla:
¿A qué conclusión puede llegar, omitiendo -si los hubieren- aquellos residuos fuera del
intervalo [-2; 2], utilizando un nivel de confianza de 0,95?

Regresión Poisson

Distribución: Poisson
Función de enlace: Log
Offset: ln(Viajes)

Variable dependiente: Averías
Número de observaciones: 16
Observaciones faltantes: 0
Iteraciones: 12 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	96,13	55,20	      -12,07	      204,32	     3,03	 0,0816
Año       	-0,05	 0,03	       -0,11	     3,4E-03	     3,38	 0,0659
Tipo_B    	-0,70	 0,20	       -1,09	       -0,31	    12,14	 0,0005
Tipo_C    	-0,65	 0,34	       -1,32	        0,01	     3,69	 0,0548
Tipo_D    	-1,27	 0,53	       -2,30	       -0,23	     5,77	 0,0163
Tipo_E    	 0,01	 0,28	       -0,54	        0,57	  2,5E-03	 0,9601

               	Valor 	gl
Log Likelihood 	272,23	10
Deviance       	  7,83	10
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

 F.V. 	gl	-2[L0-L1]	p-valor
Año   	 1	     3,43	 0,0639
Tipo_B	 1	    11,38	 0,0007
Tipo_C	 1	     4,06	 0,0438
Tipo_D	 1	     8,05	 0,0045
Tipo_E	 1	  2,5E-03	 0,9601

Año: No es significativo al 5%, pero al 10% sí. Muestra una tendencia decreciente: por cada año más reciente, la tasa esperada de averías disminuye en ~5%.

Tipo	e^β	Cambio relativo en tasa de averías
B	0.50	50% menos que A (significativo)
C	0.52	48% menos que A (apenas significativo)
D	0.28	72% menos que A (muy significativo)
E	1.01	Sin diferencia con A (no significativo)

Conclusión (modo examen)
Con un nivel de confianza del 95%, se concluye que:
* El tipo de buque **influye significativamente en la tasa de averías por viaje**.
* En comparación con el tipo A (carga general):
* Los tipos B, C y D tienen **tasas significativamente menores** de averías.
* Tipo D es el más seguro, con un **72% menos de tasa**.
* Tipo E no presenta diferencias significativas.
* El **año de construcción no es significativo al 5%**, pero al 10% muestra una tendencia: **barcos más nuevos tienden a sufrir menos averías**.


---



Ejercicio 12. Una compañía proveedora de internet quiere determinar si las quejas de los usuarios en
relación al servicio ofrecido, en el último bimestre, dependen del rango etario (edad) y del nº
de abonados, clasificados por localidades (1, 2, 3 y 4). Los datos obtenidos fueron:
¿A qué conclusión puede llegar, omitiendo -si los hubieren- aquellos residuos fuera del
intervalo [-2; 2], utilizando un nivel de significación del 5%?

---

Ejercicio 13. Se quiere modelar el número de accidentes de tráfico que ocurren por hora en un cruce de
avenidas. Las variables disponibles son: Número de accidentes: el nº de accidentes por hora;
Tráfico: el nº de vehículos que pasan por el cruce por hora; Hora del día: una variable que
representa la hora del día, donde las horas de la mañana (de 6 a 12) toma un valor de 1, y las
horas de la tarde (de 12 a 18) toma un valor de 2 y Condiciones climáticas: variable binaria
que indica si las condiciones climáticas son adversas (1) o no (0).

Parámetro	Estimador	E.E.	p
Intercepto (β0)	-1.20	0.50	0.02
Tráfico (β1)	0.01	2	<0.01
Hora (β2)	0.30	0.10	0.01
Climáticas (β3)	0.80	0.25	0.02

¿Cómo interpretaría, con una confianza del 95%, los resultados obtenidos?

Y: nro accidentes por hora

X1: Trafico de vehiculos por hora
X2: Hora del día, donde 6-12: 1 y 12-18: 2
X3: Clima, adversas:1 o no:0

**β₀ = -1.20**:
Este coeficiente es **significativo al 5%** (p = 0.02).
Cuando el tráfico es 0, es de mañana (Hora = 1), y las condiciones climáticas no son adversas (Climáticas = 0), el número esperado de accidentes por hora es: e^−1.2 = 0.301
Es decir, **menos de 1 accidente por hora** en esas condiciones.

**β₁ = 0.01**:
Este coeficiente es **significativo al 5%** (p < 0.01).
Por cada vehículo adicional que pasa por el cruce por hora, el número esperado de accidentes **aumenta un 1% aproximadamente**.
La tasa de accidentes se multiplica por: e^0.01≈1.01

**β₂ = 0.30**:
Este coeficiente es **significativo al 5%** (p = 0.01).
Pasar de la mañana (Hora = 1) a la tarde (Hora = 2) **aumenta el número esperado de accidentes** en aproximadamente un **35%**.
La tasa de accidentes se multiplica por: e0.30≈1.35

**β₃ = 0.80**:\
Este coeficiente es **significativo al 5%** (p = 0.02).
Cuando las condiciones climáticas son adversas, el número esperado de accidentes por hora **se duplica aproximadamente**.
La tasa se multiplica por: e^0.80≈2.23

---

Ejercicio 14. El director de un call center analiza el número de llamadas recibidas, durante la semana
anterior, en función de la cantidad de operadores disponibles y clasificados según los días
que hubo promociones (1 = sí; 0 = no). Los resultados obtenidos fueron:
¿A qué conclusión llegó, al 5%, el director?

Distribución: Poisson
Función de enlace: Log

Variable dependiente: Llamadas
Número de observaciones: 7
Observaciones faltantes: 13
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros 	Est.	E.E.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante  	3,42	0,17	        3,08	        3,76	   388,03	<0,0001
Operadores 	0,16	0,03	        0,11	        0,21	    37,59	<0,0001
Promociones	0,36	0,08	        0,19	        0,52	    17,94	<0,0001

               	 Valor 	gl
Log Likelihood 	3040,31	 4
Deviance       	  11,95	 4
Escala (fijada)	   1,00	  


Pruebas de hipótesis marginales

   F.V.    	gl	-2[L0-L1]	p-valor
Operadores 	 1	    36,86	<0,0001
Promociones	 1	    18,73	<0,0001

---

Ejercicio 15. Una médica infectóloga de un hospital quiere determinar si el número de infecciones
intrahospitalarias de nuevos pacientes, internados durante el año pasado, está en función de
la cantidad de pacientes internados y el uso de antibióticos preventivos (1 = Si; 0 = No):
¿A qué conclusión llegó la infectóloga, con una significación de 0,01?

---

Ejercicio 16. El ingeniero de una fábrica analiza el número de fallas, en los últimos ocho días, de una
determinada máquina en función a las horas de uso diario y al mantenimiento preventivo (1
= Si; 0 =no).
¿A qué conclusión pudo llegar el ingeniero, con una confianza del 95%?

---

Ejercicio 17. El dueño de un restaurante quiere predecir el número de clientes que recibirá por día en
función de la temperatura (ºC) y del día de la semana (1 = feriado, 0 = laboral). Para ello
seleccionó, de manera aleatoria, cuatro días feriado, cuatro laborables (del mes pasado) y el
nº de clientes por día:
¿Qué conclusión obtuvo el dueño del restaurante, con un nivel de significación de 0,05?

Distribución: Poisson
Función de enlace: Log

Variable dependiente: Clientes
Número de observaciones: 8
Observaciones faltantes: 12
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros 	Est. 	E.E.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante  	 3,77	0,61	        2,56	        4,97	    37,55	<0,0001
Temperatura	 0,05	0,02	     7,5E-04	        0,09	     3,97	 0,0464
Día_laboral	-0,38	0,12	       -0,62	       -0,14	     9,85	 0,0017

               	 Valor 	gl
Log Likelihood 	3442,55	 5
Deviance       	  16,44	 5
Escala (fijada)	   1,00	  


Pruebas de hipótesis marginales

   F.V.    	gl	-2[L0-L1]	p-valor
Temperatura	 1	     3,92	 0,0477
Día_laboral	 1	    10,35	 0,0013

---

Ejercicio 18. El departamento de policía estudia el número de robos diarios, durante un mes, en función de
la cantidad de patrulleros movilizados y la iluminación urbana (1 = buena, 0 = deficiente o
nula), en cinco barrios de la ciudad. Luego de modelar los datos, se obtuvieron los siguientes
resultados:

Parámetro	Estimador	E.E.	p
Intercepto (β0)	0.8	0.25	0.05
Patrulleros (β1)	-0.1	1	0.03
Iluminación (β2)	-0.5	0.2	0.02

¿Cómo interpretaría, con una confianza del 95%, los resultados obtenidos?

Y: nro robos diarios
X1: cant. patrulleros
X2: iluminacion urbana (1: buena 0:deficiente)

**β₀ = 0.80**:
Este coeficiente es **apenas significativo al 5%** (p = 0.05).\
Cuando no hay patrulleros movilizados y la iluminación es deficiente (Iluminación = 0), el número esperado de robos diarios es:
e^0.8≈2.23. Es decir, **se esperan alrededor de 2 robos diarios** en esas condiciones base.

**β₁ = -0.10**:\
Este coeficiente es **significativo al 5%** (p = 0.03).\
Por cada patrullero adicional movilizado, el número esperado de robos **disminuye en aproximadamente un 9.5%**.\
La tasa se multiplica por: e^−0.10≈0.905
Esto indica que aumentar la presencia policial tiene un efecto preventivo sobre los robos.

**β₂ = -0.50**:\
Este coeficiente también es **significativo al 5%** (p = 0.02).\
Tener buena iluminación en el barrio reduce el número esperado de robos diarios en aproximadamente un **39%**.\
La tasa se multiplica por:  e^−0.50≈0.61

---

Ejercicio 19. El jefe de producción de una fábrica estudia, a partir de datos obtenidos el último año, la
cantidad de accidentes diarios, utilizando como variables regresoras: el número de horas
extras trabajadas y el uso de equipo de seguridad (1 = Sí; 0 = No). Luego de modelar los
datos, obtuvo los siguientes resultados:

Parámetro	Estimador	E.E.	p
Intercepto (β0)	1.0	0.25	0.04
Extras (β1)	0.3	0.01	0.01
Seguridad (β2)	-0.8	0.2	<0.01

¿Cuál fue la conclusión, al nivel del 5%, del jefe de producción?

Y: cant. accidentes diarios
X1: nro. horas extras
X2: uso equipo seguridad

**β₀ = 1.00** (p = 0.04):
Significativo al 5%.
Cuando no se trabajan horas extras y no se usa equipo de seguridad, el número esperado de accidentes diarios es: e^1.0≈2.72
Es decir, **se esperan cerca de 3 accidentes diarios**.

**β₁ = 0.30** (p = 0.01):
Significativo al 5%.
Por cada **hora extra trabajada**, el número esperado de accidentes **aumenta aproximadamente un 35%**.La tasa se multiplica por: e^0.30≈1.35

**β₂ = -0.80** (p < 0.01):
Significativo al 5%.
Cuando se usa equipo de seguridad, el número esperado de accidentes **disminuye aproximadamente un 55%**. La tasa se multiplica por: e^−0.80≈0.45


---

Ejercicio 20. En el siguiente ejemplo se quiere determinar si el número de visitas al médico está relacionado
con las variables explicativas: edad (en años) y si fuma (1 = Sí, 0 = No). Luego de modelar
los datos, se obtuvieron los siguientes resultados:

Parámetro	Estimador	E.E.	p
Intercepto (β0)	1.20	0.25	<0.01
Edad (β1)	0.03	0.01	<0.01
Fuma (β2)	0.40	0.20	<0.01

¿Cómo explicaría, con una confianza del 99%, los resultados obtenidos?

**β₀ = 1.20** (p < 0.01):
Este coeficiente es **estadísticamente significativo al 1%**.
Cuando la edad es 0 y la persona no fuma (caso base), el número esperado de visitas al médico es: e^1.20≈3.32
Esto representa el nivel base del modelo, aunque no tenga interpretación literal práctica (nadie tiene 0 años y fuma o no fuma), sirve como referencia.

**β₁ = 0.03** (p < 0.01):
Significativo al 1%.
Por cada año adicional de edad, el número esperado de visitas al médico **aumenta un 3% aproximadamente**. La tasa de visitas se multiplica por: e^0.03≈1.030

**β₂ = 0.40** (p < 0.01):
También significativo al 1%.
Fumar está asociado con un **aumento del 49% aproximadamente** en el número esperado de visitas al médico. La tasa se multiplica por: e^0.40≈1.49


---