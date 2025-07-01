## Paso a paso: ¿cómo interpretar la salida?

1. ¿Cuál es el evento de interés?
Identificá qué significa el 1 en la variable dependiente (éxito). Siempre tiene que estar claro:

“Se considera como éxito (1) que el paciente tenga afectación de ganglios”

2. ¿Qué variables predictoras se usan?
Enumerá las regresoras, su tipo (numérica o dicotómica) y cómo están codificadas. Esto te ayuda a interpretar después los coeficientes.

3. ¿Qué dice la tabla de coeficientes?
Para cada variable, mirá:

Elemento	¿Cómo lo interpreto?
Coeficiente (β)	Si es positivo, aumenta las chances de éxito. Si es negativo, las reduce.
OR (odds ratio)	Cuánto se multiplican las odds si esa variable aumenta una unidad
p-valor (Wald)	Si < 0.05 → variable significativa (aportaría al modelo)

4. ¿Qué dice la tabla de pruebas marginales?
Es una prueba alternativa más robusta. Usala especialmente cuando:

La muestra es chica

Los p-valores de Wald están cerca de 0.10

Si el p marginal < 0.05, podés considerar que la variable sí aporta al modelo

5. ¿Qué variables aportan al modelo?
Elegí un criterio coherente (usualmente 5% o 10%) y escribí:

“Según el p-valor de Wald/marginal, la variable X resulta significativa al 5%, por lo que se considera que influye sobre la variable respuesta”

6. ¿Cómo interpreto el odds ratio?
Solo si la variable es significativa, agregá:

“El OR indica que las odds de éxito se multiplican por X cuando la variable X aumenta una unidad”

7. ¿Qué dice el modelo como conjunto?
Usá la Deviance y la convergencia para confirmar que el modelo es razonable.

“La deviance baja y la convergencia rápida indican un ajuste aceptable del modelo, pese al tamaño reducido de la muestra”

✅ Conclusión final sugerida
“El modelo sugiere que [variable significativa] es un predictor relevante para [evento]. Esto se observa en el signo del coeficiente, el OR y el p-valor. El modelo presenta buen ajuste general, aunque debido al tamaño de la muestra los resultados deben interpretarse con cautela.”

### Ejercicio 1
Los siguientes datos se refieren a pacientes sometidos a cirugía de cáncer de próstata. Para determinar qué tratamiento postoperatorio adoptar, es necesario establecer si el tumor ha afectado o no a los ganglios linfáticos circundantes (1=sí; 0=no). Esto se puede estudiar mediante variables registradas previas a la intervención: radiografías (1=grave; 0=leve), estado del tumor confirmado por biopsia (1=grave; 0=leve) y nivel de fosfatasa sérica. afectó ganglios radiografías biopsia fosfatasa sérica afectó ganglios radiografías biopsia fosfatasa sérica 

¿A qué conclusión llegó (utilizando el modelo completo), con una significación del 5%?

 Parámetros   	Est. 	E.E.	O.R. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante       	-4,90	1,94	 0,01	     1,7E-04	        0,34	     6,35	 0,0117
radiografias    	 0,78	1,78	 2,18	        0,07	       71,64	     0,19	 0,6610
biopsia         	 3,28	1,42	26,61	        1,64	      430,46	     5,34	 0,0209
fosfatasa_serica	 0,03	0,02	 1,03	        1,00	        1,07	     3,05	 0,0807

               	Valor	gl
Log Likelihood 	-8,17	21
Deviance       	16,35	21
Escala (fijada)	 1,00	  


Pruebas de hipótesis marginales

      F.V.      	gl	-2[L0-L1]	p-valor
radiografias    	 1	     0,19	 0,6637
biopsia         	 1	     6,69	 0,0097
fosfatasa_serica	 1	     3,36	 0,0667

El modelo indica que el principal predictor de afectación de ganglios es el resultado de la biopsia: cuando el tumor es grave, las odds de afectación aumentan más de 26 veces, de forma estadísticamente significativa (p < 0.05).

La fosfatasa sérica también parece tener un efecto leve positivo (3% por unidad), con significación marginal (p ≈ 0.0667), lo que sugiere que podría considerarse en un modelo más amplio.

En cambio, la gravedad radiográfica no mostró evidencia de ser un predictor relevante en esta muestra.

El modelo presenta un buen ajuste global (deviance baja) y converge correctamente. Sin embargo, dada la muestra pequeña, se recomienda cautela al generalizar los resultados.


### Ejercicio 2
El siguiente ejercicio nos muestra los datos de un negocio en el cual el Gerente quiere determinar si la compra de cierto producto, al 5%, depende del ingreso anual de los/as compradores/as. Para ello toma una muestra de doce clientes, les pregunta si comprarían el nuevo producto (1=sí; 0=no) y el ingreso anual. 

¿A qué conclusión llegó?

Regresión logística

Distribución: Binomial
Función de enlace: Logit

Variable dependiente: compra
Codificar como éxito a valores mayores que la media
Número de observaciones: 12
Observaciones faltantes: 13
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

 Parámetros  	 Est.  	 E.E.  	 O.R.  	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante    	  -6,13	   3,78	2,2E-03	     1,3E-06	        3,63	     2,62	 0,1053
ingreso_anual	9,9E-05	5,8E-05	   1,00	        1,00	        1,00	     2,93	 0,0871

               	Valor	gl
Log Likelihood 	-5,60	10
Deviance       	11,21	10
Escala (fijada)	 1,00	  


Pruebas de hipótesis marginales

    F.V.     	gl	-2[L0-L1]	p-valor
ingreso_anual	 1	     5,09	 0,0240

El modelo muestra que el **ingreso anual tiene un efecto positivo sobre la probabilidad de compra** del nuevo producto. Aunque el coeficiente estimado es pequeño (OR ≈ 1.0001), la prueba marginal indica que este efecto es **estadísticamente significativo al 5% (p = 0.0240)**.

Esto sugiere que, dentro de esta muestra, a mayor ingreso anual, **aumentan levemente las chances de compra**. El modelo ajusta adecuadamente a los datos y converge sin inconvenientes, aunque la pequeña muestra utilizada puede afectar la precisión de la estimación.


### Ejercicio 3
Estamos interesados en saber si el consumo de tabaco afecta a la neumonitis, al nivel del 5%. Para ello se tomó una muestra de 20 pacientes que concurrieron a un consultorio, se determinó si poseían la enfermedad (1=sí; 0=no) y se les preguntó si eran fumadores (1=sí; 0=no). 
¿A qué conclusión llegó?

Variable dependiente: enfermedad
Codificar como éxito a valores mayores que la media
Número de observaciones: 20
Observaciones faltantes: 5
Iteraciones: 5 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-0,85	0,69	0,43	        0,11	        1,66	     1,51	 0,2195
fuma      	 2,23	1,05	9,33	        1,19	       72,99	     4,53	 0,0333

               	Valor 	gl
Log Likelihood 	-11,11	18
Deviance       	 22,23	18
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

F.V.	gl	-2[L0-L1]	p-valor
fuma	 1	     5,30	 0,0213

**Conclusión**

* El coeficiente positivo (2.23) indica que fumar **aumenta la probabilidad de tener neumonitis**.

* El OR = 9.33 significa que **las odds de tener neumonitis son más de 9 veces mayores** en fumadores respecto a no fumadores.

* Ambos p-valores (Wald y marginal) son **significativos al 5%**, por lo tanto, el efecto es estadísticamente válido.

* Ajuste del modelo
 - Deviance = 22.23 con 18 gl → aceptable
 - Convergencia rápida en 5 iteraciones


### Ejercicio 4
Un instituto desea predecir si un estudiante aprobará un examen final (si=1; no=0), al nivel del 10%, en función de las horas de estudio por día (h/día) y el porcentaje de asistencia a clases.
¿A qué conclusión llegó?

Variable dependiente: aprobado
Codificar como éxito a valores mayores que la media
Número de observaciones: 14
Observaciones faltantes: 11
Iteraciones: 8 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	 O.R.  	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-5,65	3,47	3,5E-03	     3,9E-06	        3,16	     2,65	 0,1035
h_dia     	-0,12	0,32	   0,88	        0,48	        1,64	     0,15	 0,6959
asistencia	 0,09	0,05	   1,09	        0,99	        1,19	     3,43	 0,0641

               	Valor	gl
Log Likelihood 	-4,89	11
Deviance       	 9,78	11
Escala (fijada)	 1,00	  


Pruebas de hipótesis marginales

  F.V.    	gl	-2[L0-L1]	p-valor
h_dia     	 1	     0,15	 0,7001
asistencia	 1	     7,80	 0,0052

**Conclusión**

El modelo indica que **la asistencia a clases es un predictor significativo** de aprobación en el examen final. Por cada punto porcentual de asistencia, las odds de aprobar aumentan un 9%, y este efecto es estadísticamente significativo al 5% según la prueba marginal.

En cambio, las horas de estudio por día no mostraron relación significativa con la probabilidad de aprobar en esta muestra. El modelo ajusta bien a los datos, pero debe considerarse que el tamaño muestral es reducido y puede influir en la estabilidad de las estimaciones.


### Ejercicio 5
Una compañía de streaming desea predecir, con un nivel del 10%, si un cliente cancelará su suscripción (0=no; 1=sí) en función del tiempo promedio de uso semanal (h/sem) y la antigüedad en los últimos 12 meses. 
¿A qué conclusión llegó?

Variable dependiente: canceló
Codificar como éxito a valores mayores que la media
Número de observaciones: 19
Observaciones faltantes: 6
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	 0,21	1,18	1,23	        0,12	       12,41	     0,03	 0,8605
h_sem     	 0,12	0,11	1,13	        0,90	        1,41	     1,07	 0,3005
antigüedad	-0,02	0,18	0,98	        0,69	        1,38	     0,02	 0,8906

               	Valor 	gl
Log Likelihood 	-10,28	16
Deviance       	 20,56	16
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

  F.V.    	gl	-2[L0-L1]	p-valor
h_sem     	 1	     1,23	 0,2670
antigüedad	 1	     0,02	 0,8906

El modelo no muestra evidencia estadísticamente significativa de que ni el **tiempo de uso semanal** ni la **antigüedad** estén asociadas con la cancelación de la suscripción. Ambos predictores tienen p-valores mayores a 0.10, tanto en la prueba de Wald como en la marginal.



### Ejercicio 6
Una empresa desea clasificar, con una confianza del 95%, si un correo es spam (1) o no (0) en relación al porcentaje de palabras clave como “gratis” y “urgente”. spam gratis urgente spam gratis urgente REGRESIÓN LOGÍSTICA BINARIA Pág. 3/7 spam gratis urgente spam gratis urgente ¿A qué conclusión llegó?

Variable dependiente: spam
Codificar como éxito a valores mayores que la media
Número de observaciones: 20
Observaciones faltantes: 5
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-1,45	2,20	0,23	     3,1E-03	       17,36	     0,44	 0,5084
gratis    	 0,05	0,03	1,05	        1,00	        1,11	     3,29	 0,0699
urgente   	-0,01	0,02	0,99	        0,94	        1,03	     0,40	 0,5255

               	Valor 	gl
Log Likelihood 	-10,95	17
Deviance       	 21,91	17
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

 F.V.  	gl	-2[L0-L1]	p-valor
gratis 	 1	     4,30	 0,0381
urgente	 1	     0,43	 0,5123

El modelo muestra que el porcentaje de palabras “gratis” tiene un **efecto positivo y significativo** sobre la probabilidad de que un correo sea clasificado como spam. Cada punto porcentual adicional de estas palabras aumenta un 5% las odds de ser spam, y este efecto es **estadísticamente significativo al 5%** (p = 0.0381).

En cambio, el porcentaje de palabras “urgente” **no mostró asociación significativa** con la clasificación como spam.

El modelo ajusta adecuadamente a los datos y converge sin problemas, aunque debido al tamaño limitado de la muestra, se recomienda considerar estos resultados como exploratorios.

### Ejercicio 7
Se quiere predecir, al 5%, si un estudiante abandonará sus estudios universitarios (1=sí; 0=no) relacionado con las horas que trabaja por semana (h/sem) y el nº de materias reprobadas.
¿A qué conclusión llegó?

Variable dependiente: abandonó
Codificar como éxito a valores mayores que la media
Número de observaciones: 17
Observaciones faltantes: 8
Iteraciones: 7 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-3,87	5,17	0,02	     8,2E-07	      526,82	     0,56	 0,4540
h_sem     	-0,01	0,14	0,99	        0,75	        1,31	     0,01	 0,9408
reprobadas	 0,39	0,17	1,47	        1,06	        2,05	     5,33	 0,0210

               	Valor	gl
Log Likelihood 	-5,47	14
Deviance       	10,94	14
Escala (fijada)	 1,00	  


Pruebas de hipótesis marginales

  F.V.    	gl	-2[L0-L1]	p-valor
h_sem     	 1	     0,01	 0,9408
reprobadas	 1	    12,09	 0,0005

El modelo muestra que el **número de materias reprobadas** está significativamente asociado con el abandono de los estudios universitarios. Cada materia reprobada **aumenta un 47% las odds de abandonar**, y este efecto es altamente significativo (p = 0.0005).

En cambio, la cantidad de horas trabajadas por semana **no mostró relación estadísticamente significativa** con el abandono. El modelo presenta buen ajuste general y converge correctamente, aunque debe tenerse en cuenta el tamaño moderado de la muestra.


### Ejercicio 8
Se toma una muestra de vacas que forman parte de un programa de transferencia de embriones, la variable Y podría representar las condiciones: preñada (1) o vacía (0) y la variable X el tamaño del cuerpo lúteo (TCL) al momento de la siembra de los embriones.

¿Es un buen indicador de preñez, al nivel del 5%, el TCL? 
¿A qué conclusión llegó?

Variable dependiente: Condición
Codificar como éxito a valores mayores que la media
Número de observaciones: 38
Observaciones faltantes: 0
Iteraciones: 7 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-2,24	1,31	 0,11	        0,01	        1,40	     2,91	 0,0882
TCL       	 4,23	1,59	68,49	        3,02	     1552,18	     7,05	 0,0079

               	Valor 	gl
Log Likelihood 	-12,54	36
Deviance       	 25,08	36
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

F.V.	gl	-2[L0-L1]	p-valor
TCL 	 1	    11,23	 0,0008

El tamaño del cuerpo lúteo (TCL) es un predictor **altamente significativo** de preñez. Por cada unidad que aumenta el TCL, las odds de quedar preñada se multiplican por más de 68 (p = 0.0079), según la prueba de Wald, y esto se confirma con la prueba marginal (p = 0.0008).

Aunque el intervalo de confianza del OR es muy amplio, lo que refleja cierta incertidumbre sobre su magnitud exacta, el efecto es estadísticamente claro. El modelo ajusta bien a los datos y converge sin problemas, lo que respalda el uso del TCL como **indicador útil para predecir preñez** en este contexto


### Ejercicio 9
Una empresa desea pronosticar, al nivel del 5%, si un/a empleado/a dejaría la compañía (0=no; 1=sí) de acuerdo al nivel de satisfacción laboral (de 1 a 10: a mayor puntaje, menor satisfacción) y a los años trabajados en la empresa. Tenga en cuenta que la variable “frecuencia” representa el nº de trabajadores/as que puntuaron igual en las variables estudiadas. ¿A qué conclusión llegó?

Variable dependiente: dejaría (no)
Número de observaciones: 48
Observaciones faltantes: 18
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

 Parámetros 	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante   	-0,72	0,69	0,49	        0,13	        1,89	     1,08	 0,2990
satisfacción	 0,38	0,14	1,47	        1,11	        1,95	     7,18	 0,0074
años        	-0,20	0,09	0,82	        0,69	        0,98	     4,94	 0,0263

               	Valor 	gl
Log Likelihood 	-26,95	45
Deviance       	 53,90	45
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

    F.V.    	gl	-2[L0-L1]	p-valor
satisfacción	 1	     9,64	 0,0019
años        	 1	     6,42	 0,0113


El modelo indica que tanto el **nivel de satisfacción** como la **antigüedad** son predictores significativos de que un/a empleado/a deje la empresa.

A menor satisfacción (mayor puntaje), las odds de renunciar **aumentan un 47%** por punto. Por otro lado, por cada año adicional en la empresa, las odds de renunciar **disminuyen un 18%**. Ambos efectos son **estadísticamente significativos al 5%** según las pruebas de Wald y marginal.

El modelo ajusta adecuadamente y permite concluir que tanto el malestar como la escasa antigüedad se asocian con mayor riesgo de salida de personal.


### Ejercicio 10
Una nutricionista está interesada en prever, al 5%, si una persona tiene normopeso (0=no; 1=sí) a partir del índice de masa corporal (IMC) y de la actividad física diaria (minutos) que realiza. IMC actividad física normopeso Nº pacientes no si no si no no no si si si ¿A qué conclusión llegó?

Distribución: Binomial
Función de enlace: Logit
Frecuencias: N_pacientes

Variable dependiente: normopeso (1)
Número de observaciones: 34
Observaciones faltantes: 28
Iteraciones: 7 (max=20)
Tolerancia: 1E-9 (0,000000000)

   Parámetros   	Est. 	E.E.	 O.R.  	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante       	 7,66	2,99	2132,24	        6,05	   751787,83	     6,56	 0,0104
actividad_física	 0,06	0,03	   1,06	        1,00	        1,13	     3,40	 0,0652
IMC             	-0,49	0,17	   0,61	        0,44	        0,86	     8,32	 0,0039

               	Valor 	gl
Log Likelihood 	-14,63	31
Deviance       	 29,26	31
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

      F.V.      	gl	-2[L0-L1]	p-valor
actividad_física	 1	     4,96	 0,0260
IMC             	 1	    17,01	<0,0001


El modelo indica que tanto el **índice de masa corporal (IMC)** como la **actividad física diaria** son predictores significativos de tener **normopeso**.

En particular, cada punto más de IMC **reduce en un 39% las odds de estar en normopeso**, mientras que cada minuto adicional de actividad física **incrementa las odds en un 6%**. Ambos efectos son estadísticamente significativos (IMC con p < 0.01, actividad con p < 0.05 en la prueba marginal).

El modelo se ajusta adecuadamente a los datos y ofrece una base sólida para afirmar que el control del IMC y el ejercicio diario están asociados a un estado saludable de peso corporal.



### Ejercicio 11
Un banco quiere predecir, al 5%, si un cliente será moroso (0=no; 1=sí) con el pago de un préstamo, en función del monto del préstamo solicitado ($ por 10.000) y de los ingresos mensuales del cliente ($ por 10.000). 
¿A qué conclusión llegó?

Variable dependiente: mora
Codificar como éxito a valores mayores que la media
Número de observaciones: 30
Observaciones faltantes: 28
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

  Parámetros  	Est. 	E.E.	 O.R. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante     	 6,39	3,59	595,41	        0,53	   674347,15	     3,17	 0,0749
monto_prestamo	-0,13	0,15	  0,87	        0,65	        1,18	     0,79	 0,3737
sueldo        	-0,01	0,01	  0,99	        0,98	        1,00	     5,90	 0,0152

               	Valor 	gl
Log Likelihood 	-15,04	27
Deviance       	 30,08	27
Escala (fijada)	  1,00	  


Pruebas de hipótesis marginales

     F.V.     	gl	-2[L0-L1]	p-valor
monto_prestamo	 1	     0,83	 0,3612
sueldo        	 1	     8,06	 0,0045

El modelo muestra que el **sueldo mensual** del cliente está significativamente asociado con la probabilidad de morosidad. A mayor ingreso, la probabilidad de caer en mora **disminuye**, aunque el efecto es leve: por cada $10.000 adicionales, las odds de ser moroso se reducen un 1% (p = 0.0152).

En cambio, el monto del préstamo solicitado **no resultó significativo** como predictor de morosidad (p > 0.36). El modelo se ajusta razonablemente a los datos, y la convergencia fue adecuada.


### Ejercicio 12
Una empresa de tecnología desea clasificar, al nivel del 1%, a sus usuarios como "activo" (1) o "inactivo" (0) en función del tiempo de uso diario (minutos) y el uso semanal (días), de acuerdo a una aplicación determinada. 
¿A qué conclusión llegó?

Distribución: Binomial
Función de enlace: Logit
Frecuencias: usuarios

Variable dependiente: clasificación
Codificar como éxito a valores mayores que la media
Número de observaciones: 129
Observaciones faltantes: 30
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-3,47	1,11	0,03	     3,5E-03	        0,27	     9,77	 0,0018
minutos   	 0,02	0,02	1,02	        0,97	        1,07	     0,79	 0,3743
días      	 0,86	0,16	2,35	        1,72	        3,21	    29,12	<0,0001

               	Valor 	gl 
Log Likelihood 	-62,39	126
Deviance       	124,77	126
Escala (fijada)	  1,00	   


Pruebas de hipótesis marginales

 F.V.  	gl	-2[L0-L1]	p-valor
minutos	 1	     0,77	 0,3800
días   	 1	    45,88	<0,0001

El modelo muestra que la **frecuencia semanal de uso (días)** es un predictor **altamente significativo** de que un usuario sea clasificado como **activo**. Por cada día más de uso en la semana, las odds de ser activo **se multiplican por 2.35** (p < 0.0001).

En cambio, la variable **minutos diarios** no mostró una asociación estadísticamente significativa con la clasificación de usuario (p > 0.37).

El modelo tiene buen ajuste y los resultados son robustos. La empresa puede utilizar la frecuencia de uso semanal como un criterio sólido para definir perfiles de usuarios activos.


### Ejercicio 13
Prediga, al 5%, si una transacción es fraudulenta (1=sí, 0=no) basada en características como el monto ($ por 1.000) y la forma de pago (1=tarjeta, 0=transferencia). La variable “transacciones” determina el nº de personas que puntuaron igual en las variables estudiadas. monto pago fraudulenta transacciones 3,26 1,84 5,04 4,64 5,29 7,81 2,54 4,08 3,71 ¿A qué conclusión llegó?

Distribución: Binomial
Función de enlace: Logit
Frecuencias: transacciones

Variable dependiente: fraudulenta
Codificar como éxito a valores mayores que la media
Número de observaciones: 270
Observaciones faltantes: 29
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	E.E.	O.R. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-0,32	0,38	 0,73	        0,34	        1,53	     0,70	 0,4012
monto     	-0,27	0,10	 0,77	        0,63	        0,93	     6,92	 0,0085
pago      	 2,80	0,36	16,41	        8,10	       33,25	    60,26	<0,0001

               	 Valor 	gl 
Log Likelihood 	-143,14	267
Deviance       	 286,28	267
Escala (fijada)	   1,00	   


Pruebas de hipótesis marginales

F.V. 	gl	-2[L0-L1]	p-valor
monto	 1	     6,97	 0,0083
pago 	 1	    78,40	<0,0001

El modelo muestra que tanto el **monto de la transacción** como la **forma de pago** son predictores significativos de fraude. En particular:

* Las transacciones hechas con **tarjeta tienen más de 16 veces mayores odds** de ser fraudulentas que las realizadas por transferencia.

* Además, a mayor monto, la probabilidad de fraude disminuye: por cada $1.000 adicionales, las odds de fraude bajan un 23%.

Ambos efectos son estadísticamente significativos (p < 0.01), el modelo converge correctamente y se ajusta bien a los datos. Estos resultados pueden ayudar a establecer reglas automatizadas de alerta en sistemas de seguridad bancaria.


### Ejercicio 14
Pronostique, con una significación del 1%, si un cliente tiene un alto riesgo crediticio (1) o bajo riesgo crediticio (0) basado en los factores: ingresos ($) y edad (años). ¿A qué conclusión llegó?

Variable dependiente: riesgo
Codificar como éxito a valores mayores que la media
Número de observaciones: 163
Observaciones faltantes: 31
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	  Est.  	 E.E.  	 O.R. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	    4,68	   0,94	108,02	       17,01	      685,94	    24,65	<0,0001
ingresos  	-8,7E-05	1,2E-04	  1,00	        1,00	        1,00	     0,53	 0,4654
edad      	   -0,13	   0,04	  0,88	        0,82	        0,94	    13,12	 0,0003

               	Valor 	gl 
Log Likelihood 	-85,98	160
Deviance       	171,95	160
Escala (fijada)	  1,00	   


Pruebas de hipótesis marginales

  F.V.  	gl	-2[L0-L1]	p-valor
ingresos	 1	     0,54	 0,4625
edad    	 1	    14,99	 0,0001

El modelo muestra que la **edad** es un predictor **altamente significativo** de riesgo crediticio: por cada año más de edad, las odds de tener **alto riesgo** disminuyen un 12% (p = 0.0001). Esto sugiere que clientes más jóvenes presentan un riesgo mayor de incumplimiento.

En cambio, los **ingresos no resultaron significativos** como variable predictora del riesgo, al menos en este conjunto de datos. El modelo converge correctamente y tiene un ajuste aceptable. Estos resultados pueden ser útiles para perfilar clientes según su riesgo de crédito.


### Ejercicio 15
Establezca, con una confianza del 95%, si un vehículo es de tipo SUV (1) o sedán (0) en función del peso (kg) y la potencia del motor. peso potencia tipo vehículos ¿A qué conclusión llegó?

Variable dependiente: tipo
Codificar como éxito a valores mayores que la media
Número de observaciones: 104
Observaciones faltantes: 28
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros	Est. 	 E.E.  	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante 	-4,44	   2,60	0,01	     7,2E-05	        1,92	     2,92	 0,0874
peso      	 0,01	1,5E-03	1,01	        1,00	        1,01	    14,35	 0,0002
potencia  	-0,02	   0,01	0,98	        0,96	        0,99	     6,86	 0,0088

               	Valor 	gl 
Log Likelihood 	-54,89	101
Deviance       	109,77	101
Escala (fijada)	  1,00	   


Pruebas de hipótesis marginales

  F.V.  	gl	-2[L0-L1]	p-valor
peso    	 1	    18,57	<0,0001
potencia	 1	     7,52	 0,0061

 El modelo indica que tanto el **peso** como la **potencia del motor** son predictores estadísticamente significativos del tipo de vehículo.

Cada kilogramo adicional de peso **aumenta un 1% las odds** de que el vehículo sea SUV, mientras que cada unidad adicional de potencia **reduce un 2% las odds** de que sea SUV.

Esto sugiere que los SUV tienden a ser más pesados pero con motores menos potentes en promedio que los sedanes.

Ambos efectos son significativos al 5% (y uno incluso al 1%), y el modelo presenta buen ajuste. Se puede usar esta información para clasificar vehículos con base en estas dos características.


### Ejercicio 16
Prediga si una campaña publicitaria será más exitosa (1) o menos exitosa (0), con una confianza del 90%, a partir del presupuesto de la campaña ($) y clasificada por distintos medios (0=TV; 1=Internet). presupuesto medio éxito días REGRESIÓN LOGÍSTICA BINARIA Pág. 6/7 presupuesto medio éxito días ¿A qué conclusión llegó?

Variable dependiente: éxito
Codificar como éxito a valores mayores que la media
Número de observaciones: 140
Observaciones faltantes: 30
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros 	  Est.  	 E.E.  	O.R. 	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante  	    1,03	   0,74	 2,79	        0,65	       11,97	     1,91	 0,1670
presupuesto	-1,7E-04	6,3E-05	 1,00	        1,00	        1,00	     6,95	 0,0084
medio      	    3,21	   0,59	24,70	        7,85	       77,76	    30,04	<0,0001

               	Valor 	gl 
Log Likelihood 	-74,02	137
Deviance       	148,05	137
Escala (fijada)	  1,00	   


Pruebas de hipótesis marginales

   F.V.    	gl	-2[L0-L1]	p-valor
presupuesto	 1	     7,53	 0,0061
medio      	 1	    41,95	<0,0001

El modelo muestra que tanto el **medio de difusión** como el **presupuesto** son predictores estadísticamente significativos del éxito de una campaña publicitaria.

Las campañas realizadas por **Internet tienen casi 25 veces más probabilidades de ser exitosas** que las hechas por TV (p < 0.0001).\
Por otro lado, el **presupuesto** presenta un efecto negativo pequeño pero significativo: por cada unidad monetaria adicional, las odds de éxito **disminuyen ligeramente** (p ≈ 0.006).

Este último resultado puede parecer contraintuitivo, pero podría reflejar que **las campañas más costosas se destinan a productos más difíciles o públicos más complejos**. El modelo se ajusta adecuadamente y converge correctamente.


### Ejercicio 17
Determine, con una significación del 5%, si el tráfico de un sitio web será alto (1) o bajo (0) en función de las siguientes variables: hora del día y día de la semana (1=lunes, … 7=domingo), clasificado por dispositivo (1=celular; 0=computadora). hora día dispositivo tráfico ¿A qué conclusión llegó?

Variable dependiente: tráfico
Codificar como éxito a valores mayores que la media
Número de observaciones: 7
Observaciones faltantes: 31
Iteraciones: 7 (max=20)
Tolerancia: 1E-9 (0,000000000)

Parámetros 	Est. 	E.E.	 O.R. 	Wald LI(95%)	Wald LS(95%) 	Wald Chi²	p-valor
Constante  	 6,56	7,78	706,00	     1,7E-04	2983125633,97	     0,71	 0,3994
hora       	-0,11	0,28	  0,90	        0,52	         1,54	     0,15	 0,7004
día        	-0,89	0,77	  0,41	        0,09	         1,85	     1,35	 0,2457
dispositivo	-1,65	2,75	  0,19	     8,8E-04	        42,27	     0,36	 0,5494

               	Valor	gl
Log Likelihood 	-3,26	 3
Deviance       	 6,52	 3
Escala (fijada)	 1,00	  


Pruebas de hipótesis marginales

   F.V.    	gl	-2[L0-L1]	p-valor
hora       	 1	     0,16	 0,6913
día        	 1	     2,83	 0,0927
dispositivo	 1	     0,41	 0,5243

El modelo no permite concluir con evidencia estadísticamente significativa que la **hora del día**, el **día de la semana**, ni el **tipo de dispositivo** estén asociados al nivel de tráfico del sitio web.

Ninguna de las variables mostró significancia (todos los p > 0.24), y los intervalos de confianza de los odds ratios son extremadamente amplios, indicando alta incertidumbre. Esto se debe probablemente al **muy bajo número de observaciones (n = 7)**.

El modelo converge pero sus conclusiones **no son confiables ni aplicables**. Sería necesario aumentar el tamaño muestral para obtener inferencias válidas.


### Ejercicio 18
Un centro médico quiere predecir si un paciente padece una enfermedad (0=no, 1=sí), al nivel del 1%, en función de la presión arterial (mmHg) y los niveles de colesterol (mh/dL). ¿A qué conclusión llegó?

Variable dependiente: enfermedad
Codificar como éxito a valores mayores que la media
Número de observaciones: 133
Observaciones faltantes: 28
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

   Parámetros   	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante       	-0,37	3,59	0,69	     6,1E-04	      794,18	     0,01	 0,9191
presión_arterial	-0,04	0,03	0,96	        0,91	        1,02	     1,86	 0,1729
colesterol      	 0,02	0,01	1,03	        1,01	        1,04	    16,59	<0,0001

               	Valor 	gl 
Log Likelihood 	-78,44	130
Deviance       	156,88	130
Escala (fijada)	  1,00	   


Pruebas de hipótesis marginales

      F.V.      	gl	-2[L0-L1]	p-valor
presión_arterial	 1	     1,94	 0,1634
colesterol      	 1	    19,01	<0,0001

El modelo indica que el **nivel de colesterol** es un predictor estadísticamente significativo de la presencia de enfermedad (p < 0.0001): por cada 1 mg/dL adicional, las odds de padecer la enfermedad aumentan un 3%.

En cambio, la **presión arterial no resultó significativa** como predictor (p ≈ 0.17), por lo que no puede afirmarse que tenga un efecto claro sobre la presencia de enfermedad en esta muestra.

El modelo converge correctamente y presenta un ajuste adecuado. Por lo tanto, el colesterol puede considerarse una variable clínica importante en la predicción de esta condición.


### Ejercicio 19
Determine, al 7%, si un préstamo será aprobado (1=si, 0=no) teniendo en cuenta los ingresos ($) y clasificado por el tipo de empleo (estable o esporádico) de los/as solicitantes. aprobación nº solicitantes ingresos tipo de empleo esporádico estable esporádico esporádico estable esporádico estable esporádico esporádico estable ¿A qué conclusión llegó? REGRESIÓN LOGÍSTICA BINARIA Pág. 7/7

Regresión logística

Distribución: Binomial
Función de enlace: Logit
Frecuencias: n_solicitantes

Variable dependiente: aprobación
Codificar como éxito a valores mayores que la media
Número de observaciones: 254
Observaciones faltantes: 28
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

      Parámetros      	 Est.  	 E.E.  	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante             	  -1,94	   0,35	0,14	        0,07	        0,29	    30,68	<0,0001
tipo_de_empleo_estable	   0,63	   0,39	1,88	        0,87	        4,07	     2,56	 0,1099
ingresos              	6,7E-05	3,4E-05	1,00	        1,00	        1,00	     3,86	 0,0493

               	 Valor 	gl 
Log Likelihood 	-142,25	251
Deviance       	 284,49	251
Escala (fijada)	   1,00	   


Pruebas de hipótesis marginales

     F.V.     	gl	-2[L0-L1]	p-valor
tipo_de_empleo	 1	     2,64	 0,1042
ingresos      	 1	     3,84	 0,0501

El modelo indica que **los ingresos** del solicitante son un predictor **significativo al 7%** para la aprobación del préstamo: a mayores ingresos, aumenta la probabilidad de que el préstamo sea aprobado.

Por su parte, aunque el **tipo de empleo** (estable vs. esporádico) muestra una tendencia clara (OR = 1.88), **no alcanza significancia estadística** al 7% (p ≈ 0.11).

El modelo tiene un ajuste adecuado y puede usarse como base para decisiones preliminares, aunque se recomienda considerar muestras más amplias o incluir más variables para mejorar la predicción.



### Ejercicio 20
Se quiere saber, con una confianza del 95%, si un cliente permanecerá en la misma empresa de telefonía (1=sí, 0=no) de acuerdo al nivel de satisfacción (1 a 10, a mayor puntaje, mayor satisfacción) y al tiempo (meses) que lleva como cliente. permanecerá satisfacción meses nº clientes ¿A qué conclusión llegó?

Variable dependiente: permanecerá
Codificar como éxito a valores mayores que la media
Número de observaciones: 247
Observaciones faltantes: 28
Iteraciones: 6 (max=20)
Tolerancia: 1E-9 (0,000000000)

 Parámetros 	Est. 	E.E.	O.R.	Wald LI(95%)	Wald LS(95%)	Wald Chi²	p-valor
Constante   	-5,01	1,17	0,01	     6,7E-04	        0,07	    18,29	<0,0001
satisfacción	-0,03	0,05	0,97	        0,88	        1,07	     0,29	 0,5905
meses       	 0,24	0,06	1,27	        1,14	        1,42	    19,00	<0,0001

               	 Valor 	gl 
Log Likelihood 	-156,45	244
Deviance       	 312,90	244
Escala (fijada)	   1,00	   


Pruebas de hipótesis marginales

    F.V.    	gl	-2[L0-L1]	p-valor
satisfacción	 1	     0,29	 0,5903
meses       	 1	    24,46	<0,0001

El modelo muestra que **el tiempo como cliente (en meses)** es un predictor **significativo** de que el cliente **permanecerá en la empresa**: por cada mes más de antigüedad, las odds de permanencia aumentan un **27%** (p < 0.0001).

En cambio, el **nivel de satisfacción declarado** **no se asoció significativamente** con la permanencia (p ≈ 0.59), lo que podría indicar que esta variable no está bien medida, o que no refleja el verdadero compromiso del cliente.

El modelo converge correctamente y tiene un ajuste razonable, por lo que puede usarse para decisiones basadas en la antigüedad del cliente, aunque sería recomendable revisar cómo se mide la satisfacción.

