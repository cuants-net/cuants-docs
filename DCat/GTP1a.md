# Ejercicios de prueba chi-cuadrado a dos vías

Este documento contiene los enunciados completos de los 20 ejercicios de prueba χ2 a dos vías, para ser resueltos con InfoStat.

En estos ejercicios de dos vías, **la mecánica central es simple** y se resume en tres pasos clave:

1. **Mirar el p-valor** del test χ².

2. **Compararlo con el nivel de significancia** (α), normalmente 0.05 o 0.01.

3. **Tomar la decisión**:

   * Si p < α, se **rechaza la independencia**: hay asociación.

   * Si p ≥ α, **no se rechaza**: no hay evidencia de asociación.

La única capa extra de análisis viene cuando también tenés el **odds ratio (OR)**:

* El test χ² **te dice si hay asociación**.

* El OR **te dice qué tan fuerte es** y **en qué dirección va**.

Y si además el OR viene con **intervalo de confianza**, podés juzgar si esa fuerza es **estadísticamente confiable** (si no incluye al 1).



---

## Ejercicio 1

Un profesor considera que la predisposición de los estudiantes a elegir cursar en la comisión del turno “mañana” implica mayor responsabilidad y se refleja en mejores resultados en las evaluaciones. ¿Se corrobora empíricamente la suposición del profesor según los resultados entre turno mañana y tarde?

| Resultado     | Turno Mañana | Turno Tarde |
|---------------|--------------|-------------|
| No aprobaron  | 77           | 49          |
| Regularizaron | 15           | 12          |
| Promocionaron | 8            | 4           |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 0,49	 2	0,7841

**Conclusión:** No se rechaza la hipótesis de independencia. No hay evidencia estadística de que el turno esté asociado al resultado académico.


## Ejercicio 2

Se quiere determinar si existe relación entre la asistencia a clases teórico-prácticas y los resultados del primer parcial de Estadística.

| Asistencia | Aprobó | No aprobó |
| ---------- | ------ | --------- |
| Asistió    | 25     | 14        |
| No asistió | 38     | 62        |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson  	 7,71	 1	0,0055

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 2,91	  1,36	  6,23
Odds Ratio 2/1	 0,34	  0,16	  0,73

**Conclusión:** Se rechaza la hipótesis de independencia. Existe evidencia estadísticamente significativa de que asistir a clases mejora las probabilidades de aprobar el examen. El odds ratio estimado es 2,91 (IC 95%: 1,36 a 6,23), lo que indica una asociación real y relevante.


## Ejercicio 3

En una encuesta preelectoral a 500 personas, se registró intención de voto (Partido A, B, C, D) según edad (18–35, 35–50, 50 o más). ¿Está asociada la intención de voto con la edad?

| Partido | 18–35 | 35–50 | 50+ |
| ------- | ----- | ----- | --- |
| A       | 10    | 40    | 60  |
| B       | 15    | 70    | 90  |
| C       | 45    | 60    | 35  |
| D       | 30    | 30    | 15  |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	70,85	 6	<0,0001

**Conclusión:** Se rechaza la independencia. La intención de voto está fuertemente asociada al grupo etario.


## Ejercicio 4

¿Existe relación entre tiempo de residencia de inmigrantes y su percepción de integración, al 10%?

| Residencia   | Integración alta | Integración baja |
| ------------ | ---------------- | ---------------- |
| Más tiempo   | 40               | 40               |
| Menos tiempo | 0                | 90               |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson  	58,85	 1	<0,0001

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	   sd	    sd	    sd

**Conclusión:** Se rechaza la hipótesis de independencia. La percepción de integración depende significativamente del tiempo de residencia. El OR no puede calcularse por celdas vacías, pero la asociación es evidente.

## Ejercicio 5

Se evalúa si hay asociación entre nivel de actividad física (Baja, Media, Alta) y consumo de bebidas azucaradas (Sí/No) en niños de primaria.

| AF          | Consume | No consume |
| ----------- | ------- | ---------- |
| Baja o nula | 32      | 12         |
| Media       | 14      | 22         |
| Alta        | 6       | 9          |

Chi Cuadrado Pearson	10,71	 2	0,0047

**Conclusión:** Se rechaza la hipótesis de independencia. Hay asociación entre nivel de actividad física y consumo de bebidas azucaradas.

## Ejercicio 6

¿Son independientes el tipo de película vista y el consumo de snacks, al 10%?

| Película | Snacks | No snacks |
| -------- | ------ | --------- |
| Acción   | 50     | 75        |
| Comedia  | 125    | 175       |
| Familiar | 90     | 30        |
| Terror   | 45     | 10        |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	65,01	 3	<0,0001

**Conclusión:** Se rechaza la hipótesis de independencia. El tipo de película está fuertemente asociado al consumo de snacks.

## Ejercicio 7

¿Existe independencia entre práctica de deporte y estado de ánimo (con/sin depresión) en jóvenes, al 1%?

| Actividad     | Sin depresión | Con depresión |
| ------------- | ------------- | ------------- |
| Deportista    | 31            | 9             |
| No deportista | 38            | 22            |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson  	 2,25	 1	0,1335

Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 0,50	  0,21	  1,22
Odds Ratio 2/1	 1,99	  0,82	  4,87

**Conclusión:** No hay evidencia suficiente para afirmar asociación entre práctica deportiva y estado de ánimo. El OR = 0,50 (IC 95%: 0,21 a 1,22), sugiere posible efecto protector, pero no es estadísticamente confiable.


## Ejercicio 8

Se analiza si el número de horas de voluntariado semanal depende del tipo de voluntario (secundario, universitario, no estudiante), al 5%.

| Tipo          | 1-2 h | 3-4 h | 5-6 h |
| ------------- | ----- | ----- | ----- |
| Secundario    | 111   | 96    | 48    |
| Universitario | 96    | 133   | 61    |
| No estudiante | 91    | 150   | 53    |

Chi Cuadrado Pearson	12,99	 4	0,0113

**Conclusión:** Se rechaza la hipótesis de independencia. El tipo de voluntario está relacionado con las horas semanales que dedica.

## Ejercicio 9

¿Es independiente el tipo de empleo respecto del año (2010, 2015, 2020)?

| Sector                         | 2010 | 2015 | 2020 |
| ------------------------------ | ---- | ---- | ---- |
| Agricultura, caza y pesca      | 240  | 214  | 201  |
| Asalariados industria privada  | 14   | 11   | 11   |
| Autónomos                      | 196  | 144  | 152  |
| Trabajo familiar no remunerado | 931  | 894  | 972  |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	11,37	 6	0,0777

**Conclusión:** No se rechaza la independencia al 5%, aunque el valor es marginal. No hay evidencia contundente de relación.


## Ejercicio 10

¿Es independiente el nivel de ansiedad respecto a la necesidad de éxito en los estudios, al 5%?

| Necesidad éxito | Alto | Medio alto | Medio | Medio bajo | Bajo |
| --------------- | ---- | ---------- | ----- | ---------- | ---- |
| Alta            | 35   | 42         | 53    | 15         | 10   |
| Media           | 18   | 48         | 63    | 33         | 31   |
| Baja            | 4    | 5          | 11    | 15         | 17   |

    Estadístico     	Valor	gl	  p    
Chi Cuadrado Pearson	48,42	 8	<0,0001

**Conclusión:** Se rechaza la independencia. El nivel de ansiedad está claramente asociado con la necesidad de éxito.


## Ejercicio 11

¿Es independiente la detección de una bacteria del tipo de análisis de laboratorio usado (1 o 2), con α = 0.01?

| Análisis | Sí | No |
| -------- | -- | -- |
| 1        | 11 | 39 |
| 2        | 8  | 42 |

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 0,58	 1	0,4444

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 0,68	  0,25	  1,81
Odds Ratio 2/1	 1,48	  0,55	  3,97

**Conclusión:** No se rechaza la hipótesis de independencia. No se encontró diferencia significativa entre métodos de análisis. El OR = 0,68 (IC 95%: 0,25 a 1,81), sugiere una leve diferencia no significativa.

## Ejercicio 12

¿Es independiente el género de los consumidores respecto a su preferencia por marcas de café (A, B, C, D), al 5%?

| Marca | Femenino | Masculino |
| ----- | -------- | --------- |
| A     | 18       | 32        |
| B     | 25       | 15        |
| C     | 15       | 10        |
| D     | 12       | 12        |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 7,41	 3	0,0598

**Conclusión:** No hay evidencia suficiente al 5% pero podría considerarse marginal al 10%. La relación es débil.


## Ejercicio 13

¿Está asociada la práctica deportiva con la sensación de bienestar en estudiantes, con α = 0.10?

| Bienestar | Práctica sí | Práctica no |
| --------- | ----------- | ----------- |
| Sí        | 7           | 6           |
| No        | 10          | 24          |

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 2,43	 1	0,1189

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 2,80	  0,78	 10,02
Odds Ratio 2/1	 0,36	  0,10	  1,28

**Conclusión:** No se rechaza la hipótesis de independencia. Aunque el OR = 2,80 sugiere posible asociación, su intervalo [0,78; 10,02] incluye el 1, indicando que no es concluyente.

## Ejercicio 14

Se quiere determinar si el género está asociado al rendimiento en comprensión lingüística. Se evalúa una muestra de 32 estudiantes.

| Género    | Aprobó | No aprobó |
| --------- | ------ | --------- |
| Masculino | 5      | 7         |
| Femenino  | 12     | 8         |

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 1,01	 1	0,3144

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 2,10	  0,52	  8,55
Odds Ratio 2/1	 0,48	  0,12	  1,94

**Conclusión:** No se rechaza la independencia. Aunque el OR = 2,10 podría insinuar mayor rendimiento en mujeres, el intervalo [0,52; 8,55] es demasiado amplio para afirmarlo con certeza.



## Ejercicio 15

¿Son independientes los resultados preuniversitarios (insuficiente a muy buena) respecto al tipo de establecimiento (público/privado), con una confianza del 90%?

| Resultado    | Público | Privado |
| ------------ | ------- | ------- |
| Insuficiente | 30      | 6       |
| Regular      | 32      | 14      |
| Buena        | 12      | 17      |
| Muy buena    | 3       | 9       |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	20,39	 3	0,0001

**Conclusión:** Se rechaza la hipótesis de independencia. El tipo de institución está asociado al desempeño previo.

## Ejercicio 16

¿Es independiente el género respecto a la preferencia de tipo de vivienda universitaria, con un 95% de confianza?

| Vivienda     | Varones | Mujeres |
| ------------ | ------- | ------- |
| Pensión      | 72      | 91      |
| Departamento | 84      | 86      |
| Con padres   | 49      | 88      |
| Otros        | 45      | 35      |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	10,13	 3	0,0175

**Conclusión:** Se rechaza la hipótesis de independencia. Las preferencias de vivienda difieren entre géneros.

## Ejercicio 17

¿Es independiente el uso del cinturón de seguridad respecto al nivel socioeconómico del conductor, al 5%?

| NSE   | Usa cinturón | No usa cinturón |
| ----- | ------------ | --------------- |
| Bajo  | 8            | 12              |
| Medio | 15           | 15              |
| Alto  | 27           | 13              |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 4,65	 2	0,0980

**Conclusión:** Se rechaza la hipótesis de independencia. Las preferencias de vivienda difieren entre géneros.

## Ejercicio 17

\[...] Chi Cuadrado Pearson 4,65 2 0,0980

**Conclusión:** No se rechaza la independencia al 5%, aunque se acerca al 10%. La relación es débil o marginal.

## Ejercicio 18

¿Es independiente el rango etario respecto al uso de plataformas de streaming (Netflix, Max, Disney, Otros), al 10%?

| Plataforma    | 15–25 | 25–35 | 35–45 |
| ------------- | ----- | ----- | ----- |
| Netflix       | 25    | 23    | 20    |
| Max           | 29    | 30    | 33    |
| Disney        | 11    | 13    | 12    |
| Otros/Ninguno | 16    | 24    | 26    |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 2,93	 6	0,8170

**Conclusión:** No se encuentra asociación entre edad y uso de plataformas de streaming.

## Ejercicio 19

¿Son iguales las preferencias de tipo de automóvil entre familias con hijos y sin hijos, con un nivel de confianza del 99%?

| Tipo de auto | Con hijos | Sin hijos |
| ------------ | --------- | --------- |
| Deportivo    | 5         | 45        |
| Sedán        | 15        | 65        |
| Utilitario   | 35        | 37        |
| Camioneta    | 17        | 46        |
| SUV          | 28        | 7         |

    Estadístico     	Valor	gl	  p    
Chi Cuadrado Pearson	62,91	 4	<0,0001

**Conclusión:** Se rechaza la independencia. Las familias con hijos tienen preferencias muy distintas a las sin hijos.

## Ejercicio 20

¿Depende del género la opinión sobre la actuación del intendente, al 1%?

| Opinión       | Mujeres | Hombres |
| ------------- | ------- | ------- |
| En desacuerdo | 84      | 118     |
| De acuerdo    | 78      | 62      |
| No contesta   | 37      | 25      |

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 9,79	 2	0,0075

**Conclusión:** Se rechaza la independencia. La opinión sobre el intendente varía significativamente entre géneros.
