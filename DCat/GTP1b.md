## Ejercicio 1.
En un estudio transversal donde intervinieron 676 estudiantes, se tuvo en cuenta la condición
de aprobación o no del examen de ingreso (Y = “aprobó examen”: Si – No) y el tipo de
preparación para el examen: el/la estudiante se preparó solo/a o en una academia (X =
“Preparación”: solo/a – academia). Como los/as estudiantes provenían de dos facultades, se
desea estudiar (al 0,05) la relación entre la aprobación y el tipo de preparación estratificado
por la unidad académica de origen (Z = “Facultad”:1 – 2). Los resultados obtenidos se
presentan en la siguiente tabla:

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,3286. No se rechaza la hipótesis de independencia entre tipo de preparación y aprobación del examen. Sin considerar la facultad, las variables parecen independientes.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,0383. Se rechaza la independencia al tener en cuenta la facultad. La relación entre tipo de preparación y aprobación depende de la facultad de origen.

c) ¿Cómo interpreta los OR de acuerdo a la facultad?

El OR de MH muestra que, **ajustando por facultad**, quienes se prepararon en una academia tuvieron **el doble de chances de aprobar el examen** en comparación con quienes se prepararon solos/as.
Como el intervalo no incluye al 1, **la aprobación del examen y el tipo de preparación no son independientes** al considerar la facultad.

| Facultad | Preparacion | Resultado | Frecuencia |
|----------|-------------|-----------|------------|
| 1        | Solo        | Aprobo    | 414        |
| 1        | Solo        | No_aprobo | 37         |
| 1        | Academia    | Aprobo    | 53         |
| 1        | Academia    | No_aprobo | 11         |
| 2        | Solo        | Aprobo    | 20         |
| 2        | Solo        | No_aprobo | 135        |
| 2        | Academia    | Aprobo    | 1          |
| 2        | Academia    | No_aprobo | 5          |

Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 0,95	 1	0,3286

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 1,34	  0,75	  2,38
Odds Ratio 2/1	 0,75	  0,42	  1,33

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       4,29	 1	0,0383

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 0,49	  0,32	  0,75
MH Odds Ratio(2/1)	 2,04	  1,33	  3,12

---

## Ejercicio 2.
Se quiere estudiar si están asociadas la práctica deportiva y la sensación de bienestar en
empleados/as de dos empresas distintas (X e Y). Para ello, se tomó una muestra aleatoria de
105 trabajadores/as provenientes de ambas empresas. Los datos los datos obtenidos aparecen
en la siguiente tabla:

a) ¿Cuál es el p-valor para la tabla marginal?

El p-valor = **0,0025**. Se rechaza la hipótesis de independencia entre práctica deportiva y bienestar. Sin considerar la empresa, las variables están asociadas.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

* El p-valor CMH = **0,0028**. También se rechaza la independencia al considerar la empresa. El resultado se mantiene.

c) ¿Cómo interpreta, al 5%, los OR de acuerdo a la empresa?

El OR de MH muestra que, **ajustando por empresa**, quienes practican deporte tienen **más del triple de chances de tener bienestar** que quienes no lo hacen.
Como el intervalo no incluye al 1, **la práctica deportiva y la sensación de bienestar no son independientes**, aun considerando la empresa.

| Empresa | Practica_deportiva | Bienestar | Frecuencia |
|---------|--------------------|-----------|------------|
| X       | Si                 | Si        | 8          |
| X       | Si                 | No        | 11         |
| X       | No                 | Si        | 7          |
| X       | No                 | No        | 25         |
| Y       | Si                 | Si        | 12         |
| Y       | Si                 | No        | 9          |
| Y       | No                 | Si        | 7          |
| Y       | No                 | No        | 26         |

Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 9,16	 1	0,0025

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 3,64	  1,56	  8,48
Odds Ratio 2/1	 0,27	  0,12	  0,64

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       8,96	 1	0,0028

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 3,62	  1,64	  7,99
MH Odds Ratio(2/1)	 0,28	  0,13	  0,61

---

## Ejercicio 3.
Supongamos que nos interesa evaluar la asociación entre uso de cinturón de seguridad en
vehículos particulares y el nivel socioeconómico (NSE), estratificado por género de quien
conduce. Para ello se tomó una muestra aleatoria de 174 conductores/as obteniendo los datos
presentados en la siguiente tabla.

a) ¿Cuál es el p-valor para la tabla marginal?

El p-valor = 0.0009. Se rechaza la hipótesis de independencia entre nivel socioeconómico y uso del cinturón.


b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

El p-valor = 0.001. También se rechaza la independencia al tener en cuenta el género.


c) ¿A qué conclusión llegó, al nivel del 10%?

Tanto el análisis general (p = 0,0009) como el análisis corregido por género (p = 0,0010) indican que **las personas con diferente nivel socioeconómico no usan el cinturón de la misma forma**.



| Genero    | NSE   | Usa_cinturon | Frecuencia |
|-----------|-------|---------------|------------|
| Femenino  | Bajo  | Si            | 8          |
| Femenino  | Bajo  | No            | 12         |
| Femenino  | Medio | Si            | 15         |
| Femenino  | Medio | No            | 15         |
| Femenino  | Alto  | Si            | 27         |
| Femenino  | Alto  | No            | 13         |
| Masculino | Bajo  | Si            | 9          |
| Masculino | Bajo  | No            | 10         |
| Masculino | Medio | Si            | 11         |
| Masculino | Medio | No            | 14         |
| Masculino | Alto  | Si            | 32         |
| Masculino | Alto  | No            | 8          |

Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	14,10	 2	0,0009
Chi Cuadrado MV-G2  	14,41	 2	0,0007
Coef.Conting.Cramer 	 0,20	  	      
Coef.Conting.Pearson	 0,27	  	      

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
      13,83	 2	0,0010

---

## Ejercicio 4.
El CEO de un supermercado está interesado en determinar si la elección de la marca (A, B) de
un mismo producto es independiente del rango etario de los/as clientes, de acuerdo al género.
Para ello, durante un tiempo determinado, tomó una muestra aleatoria de clientes, obteniendo
los siguientes resultados:

a) ¿Cuál es el p-valor para la tabla marginal?

p = 0,7765. No se rechaza la independencia entre rango etario y marca elegida.


b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p = 0,7871. Tampoco se rechaza al considerar el género.

c) ¿A qué conclusión llegó, al nivel del 5%?

Con un nivel de significación del 5%, se concluye que **no hay evidencia de relación entre el rango etario de los clientes y la marca elegida**.\
Esto se verifica tanto en el análisis general (p = 0,7765) como en el análisis por género (p = 0,7871).



| Genero    | Marca | Rango_etario | Frecuencia |
|-----------|--------|---------------|------------|
| Masculino | A      | 18_30         | 32         |
| Masculino | A      | 31_50         | 21         |
| Masculino | A      | 51_mas        | 18         |
| Masculino | B      | 18_30         | 30         |
| Masculino | B      | 31_50         | 24         |
| Masculino | B      | 51_mas        | 15         |
| Femenino  | A      | 18_30         | 25         |
| Femenino  | A      | 31_50         | 26         |
| Femenino  | A      | 51_mas        | 21         |
| Femenino  | B      | 18_30         | 28         |
| Femenino  | B      | 31_50         | 20         |
| Femenino  | B      | 51_mas        | 17         |

Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 0,51	 2	0,7765


Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       0,48	 2	0,7871

---

## Ejercicio 5.
Un investigador quiere estudiar si hay relación entre el nivel de actividad física y el hábito de
fumar, estratificado por género y, para ello se tomó una muestra aleatoria de 310 personas.
Los datos se resumen en la siguiente tabla de contingencia:

a) ¿Cuál es el p-valor para la tabla marginal?

p = 0,7404. **No se rechaza la hipótesis de independencia** entre fumar y nivel de actividad física (sin tener en cuenta el género).

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p = 0,6731. **Tampoco se rechaza la independencia** al considerar el género.


c) ¿A qué conclusión llegó, al nivel del 5%?

Con un nivel del 5%, **no se rechaza la independencia** entre el hábito de fumar y el nivel de actividad física.
Esto se mantiene incluso al separar por género. Se concluye que, en esta muestra, **fumar y actividad física son variables independientes**.



| Genero    | Fuma | Actividad_fisica | Frecuencia |
|-----------|------|------------------|------------|
| Masculino | Si   | Baja             | 20         |
| Masculino | Si   | Media            | 25         |
| Masculino | Si   | Alta             | 15         |
| Masculino | No   | Baja             | 30         |
| Masculino | No   | Media            | 35         |
| Masculino | No   | Alta             | 25         |
| Femenino  | Si   | Baja             | 10         |
| Femenino  | Si   | Media            | 20         |
| Femenino  | Si   | Alta             | 10         |
| Femenino  | No   | Baja             | 40         |
| Femenino  | No   | Media            | 50         |
| Femenino  | No   | Alta             | 30         |

Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 0,60	 2	0,7404

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       0,79	 2	0,6731

---
## Ejercicio 6
Un grupo quiere evaluar si existe relación entre el rango etario y el nivel educativo
estratificado por el estado civil, de un grupo de personas seleccionadas al azar. La tabla es la
siguiente:

a) ¿Cuál es el p-valor para la tabla marginal?
p-valor marginal = 0,3709. No se rechaza la hipótesis de independencia entre rango etario y nivel educativo. Las variables parecen independientes en el total.


b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?
p-valor CMH = 0,5601. Tampoco se rechaza la independencia al considerar el estado civil. El resultado se mantiene en ambos grupos.


c) ¿A qué conclusión llegó, al nivel del 5%?
Con un nivel de significación del 5%, se concluye que **el rango etario y el nivel educativo son independientes**, incluso al tener en cuenta el estado civil.


Estadísticos para la tabla marginal

    Estadístico     	 Valor  	gl	  p   
Chi Cuadrado Pearson	    4,27	 4	0,3709 

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       2,99	 4	0,5601


| Estado_civil | Nivel_educativo | Rango_etario | Frecuencia |
|--------------|------------------|---------------|------------|
| Soltero/a     | Primario         | Joven         | 15         |
| Soltero/a     | Primario         | Adulto_a      | 20         |
| Soltero/a     | Primario         | Mayor         | 5          |
| Soltero/a     | Secundario       | Joven         | 25         |
| Soltero/a     | Secundario       | Adulto_a      | 30         |
| Soltero/a     | Secundario       | Mayor         | 10         |
| Soltero/a     | Universitario    | Joven         | 30         |
| Soltero/a     | Universitario    | Adulto_a      | 25         |
| Soltero/a     | Universitario    | Mayor         | 5          |
| Casado/a      | Primario         | Joven         | 10         |
| Casado/a      | Primario         | Adulto_a      | 25         |
| Casado/a      | Primario         | Mayor         | 15         |
| Casado/a      | Secundario       | Joven         | 20         |
| Casado/a      | Secundario       | Adulto_a      | 35         |
| Casado/a      | Secundario       | Mayor         | 10         |
| Casado/a      | Universitario    | Joven         | 10         |
| Casado/a      | Universitario    | Adulto_a      | 20         |
| Casado/a      | Universitario    | Mayor         | 10         |

---

## Ejercicio 7.
Un estudio analiza, en un grupo de sujetos seleccionados de manera aleatoria, si hay asociación entre el uso de redes sociales y el rango etario, acorde al género.

a) ¿Cuál es el p-valor para la tabla marginal?

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

c) ¿Cómo interpreta, al 5%, los OR de acuerdo al género?

Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 4,68	 1	0,0306

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 0,50	  0,27	  0,94
Odds Ratio 2/1	 2,00	  1,07	  3,75

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       0,10	 1	0,7553

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 0,89	  0,53	  1,50
MH Odds Ratio(2/1)	 1,13	  0,67	  1,90



| Genero    | Redes_sociales | Rango_etario | Frecuencia |
|-----------|----------------|---------------|------------|
| Masculino | Si             | Adolescente   | 30         |
| Masculino | Si             | Adulto        | 40         |
| Masculino | No             | Adolescente   | 20         |
| Masculino | No             | Adulto        | 30         |
| Femenino  | Si             | Adolescente   | 50         |
| Femenino  | Si             | Adulta        | 30         |
| Femenino  | No             | Adolescente   | 10         |
| Femenino  | No             | Adulta        | 20         |

---
## Ejercicio 8.
Una empresa quiere analizar la relación entre el tipo de producto y la zona, **de acuerdo con el
canal de venta** (estrato), para un grupo de familias elegidas al azar. Los datos se muestran en la siguiente
tabla:

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,4715. No se rechaza la hipótesis de independencia entre tipo de producto y zona. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,4821. Tampoco se rechaza la independencia al considerar el canal de venta. El resultado se mantiene en ambos canales.

c) ¿A qué conclusión llegó, al nivel del 5%?

Con un nivel del 5%, se concluye que **el tipo de producto y la zona son independientes**, incluso al tener en cuenta el canal de venta.

Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 1,50	 2	0,4715

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p
       1,46	 2	0,4821

| Zona   | Canal_venta | Producto          | Frecuencia |
|--------|-------------|-------------------|------------|
| Urbana | Online      | Electrodomesticos | 50         |
| Urbana | Presencial  | Electrodomesticos | 80         |
| Urbana | Online      | Muebles           | 40         |
| Urbana | Presencial  | Muebles           | 60         |
| Urbana | Online      | Alimentos         | 30         |
| Urbana | Presencial  | Alimentos         | 50         |
| Rural  | Online      | Electrodomesticos | 30         |
| Rural  | Presencial  | Electrodomesticos | 40         |
| Rural  | Online      | Muebles           | 20         |
| Rural  | Presencial  | Muebles           | 50         |
| Rural  | Online      | Alimentos         | 20         |
| Rural  | Presencial  | Alimentos         | 30         |

---
# Ejercicio 9.
Un hospital analiza la relación, con una significación del 5%, entre el género y el rango etario, **de acuerdo al estado de salud** de un grupo de personas que concurrieron a un Centro Asistencial el mes pasado.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,6701. No se rechaza la hipótesis de independencia entre género y rango etario. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,6220. Tampoco se rechaza la independencia al considerar el estado de salud. El resultado se mantiene en personas sanas y enfermas.

c) ¿Cómo interpreta los resultados obtenidos, acorde al estado de salud?

Con un nivel del 5%, se concluye que **el género y el rango etario son independientes**, incluso al tener en cuenta si la persona estaba sana o enferma.

Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 0,80	 2	0,6701  

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       0,95	 2	0,6220


| Genero | Estado  | Rango_etario | Frecuencia |
|--------|---------|---------------|------------|
| Hombre | Sano    | Niño          | 30         |
| Hombre | Sano    | Adulto        | 50         |
| Hombre | Sano    | Anciano       | 40         |
| Hombre | Enfermo | Niño          | 20         |
| Hombre | Enfermo | Adulto        | 30         |
| Hombre | Enfermo | Anciano       | 20         |
| Mujer  | Sano    | Niño          | 40         |
| Mujer  | Sano    | Adulto        | 60         |
| Mujer  | Sano    | Anciano       | 50         |
| Mujer  | Enfermo | Niño          | 10         |
| Mujer  | Enfermo | Adulto        | 40         |
| Mujer  | Enfermo | Anciano       | 20         |

---
## Ejercicio 10.
Una encuesta quiere evaluar, en estudiantes universitarios/as, si existe relación entre la
preferencia de infusión y el rango etario, estratificado por el horario de consumo.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal < 0,0001. Se rechaza la hipótesis de independencia entre infusión preferida y rango etario. Las variables no son independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH < 0,0001. También se rechaza la independencia al considerar el horario. El resultado se mantiene tanto en la mañana como en la tarde.

c) ¿A qué conclusión llegó, al 1%, de los OR por horario?

El OR de MH indica que, **ajustando por horario**, las personas jóvenes tienen más de 3 veces más chances de preferir mate respecto a café, en comparación con personas adultas.

Como el intervalo no incluye al 1 y el p-valor es menor al 1%, se concluye que **la preferencia de infusión y el rango etario no son independientes**, incluso considerando el horario.

Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p    
Chi Cuadrado Pearson  	25,84	 1	<0,0001

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 3,30	  2,07	  5,26
Odds Ratio 2/1	 0,30	  0,19	  0,48

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p    
      25,78	 1	<0,0001

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 3,31	  2,20	  4,99
MH Odds Ratio(2/1)	 0,30	  0,20	  0,45


| Horario | Infusion | Rango_etario | Frecuencia |
|---------|----------|---------------|------------|
| Mañana  | Café     | Joven         | 35         |
| Mañana  | Café     | Adulto_a      | 65         |
| Tarde   | Café     | Joven         | 25         |
| Tarde   | Café     | Adulto_a      | 45         |
| Mañana  | Mate     | Joven         | 50         |
| Mañana  | Mate     | Adulto_a      | 25         |
| Tarde   | Mate     | Joven         | 40         |
| Tarde   | Mate     | Adulto_a      | 25         |

---
## Ejercicio 11.
Una consultora está interesada en analizar si existe relación entre el tipo de contrato laboral y
el departamento al cual pertenecen los/as trabajadores/as de una empresa, en relación al nivel educativo alcanzado. Los datos obtenidos fueron:

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,1273. No se rechaza la hipótesis de independencia entre contrato laboral y departamento. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,1261. Tampoco se rechaza la independencia al considerar el nivel educativo. El resultado se mantiene.

c) ¿A qué conclusión llegó, al 10%, de los OR por nivel educativo?

El OR de MH es 1,57 y su intervalo de confianza (1,06 a 2,30) **no incluye al 1**, por lo tanto, al 10% de significación, **sí hay evidencia de dependencia**.\
Se concluye que **el tipo de contrato y el departamento no son independientes**, considerando el nivel educativo.


Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 2,33	 1	0,1273

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 0,64	  0,36	  1,13
Odds Ratio 2/1	 1,56	  0,88	  2,75

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       2,34	 1	0,1261

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 0,64	  0,43	  0,94
MH Odds Ratio(2/1)	 1,57	  1,06	  2,30


| Nivel_educativo | Departamento | Contrato        | Frecuencia |
|------------------|--------------|------------------|------------|
| Secundario       | Ventas       | Tiempo_completo  | 20         |
| Secundario       | Ventas       | Medio_tiempo     | 15         |
| Secundario       | Produccion   | Tiempo_completo  | 25         |
| Secundario       | Produccion   | Medio_tiempo     | 10         |
| Universitario    | Ventas       | Tiempo_completo  | 35         |
| Universitario    | Ventas       | Medio_tiempo     | 25         |
| Universitario    | Produccion   | Tiempo_completo  | 50         |
| Universitario    | Produccion   | Medio_tiempo     | 25         |

---
## Ejercicio 12.
Se tomó una muestra aleatoria de 330 deportistas que concurren a un club y se desea analizar si existe relación entre el tipo de deporte y el género, estratificado por rango etario. Los datos obtenidos fueron:

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal < 0,0001. Se rechaza la hipótesis de independencia entre tipo de deporte y género. Las variables no son independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH < 0,0001. También se rechaza la independencia al considerar el rango etario. El resultado se mantiene tanto en jóvenes como en adultos.

c) ¿Cómo interpreta, al 7%, los resultados obtenidos en relación al rango etario?

Al nivel del 7%, se concluye que **el tipo de deporte y el género no son independientes**, incluso al considerar el rango etario.
Hay evidencia estadística suficiente para afirmar que la elección de deporte varía según el género en ambos grupos etarios.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p    
Chi Cuadrado Pearson	33,07	 2	<0,0001	  	       

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p    
      32,96	 2	<0,0001


| Rango_etario | Genero    | Deporte    | Frecuencia |
|--------------|-----------|------------|------------|
| Joven        | Masculino | Futbol     | 50         |
| Joven        | Femenino  | Futbol     | 20         |
| Adulto/a     | Masculino | Futbol     | 30         |
| Adulto/a     | Femenino  | Futbol     | 10         |
| Joven        | Masculino | Basquet    | 40         |
| Joven        | Femenino  | Basquet    | 30         |
| Adulto/a     | Masculino | Basquet    | 20         |
| Adulto/a     | Femenino  | Basquet    | 15         |
| Joven        | Masculino | Natacion   | 30         |
| Joven        | Femenino  | Natacion   | 50         |
| Adulto/a     | Masculino | Natacion   | 10         |
| Adulto/a     | Femenino  | Natacion   | 25         |

---

## Ejercicio 13.
Se quiere estudiar la relación entre el tipo de comida y la frecuencia de consumo, según rango etario. Los datos son:

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,1007. No se rechaza la hipótesis de independencia entre tipo de comida y frecuencia de consumo. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,1052. Tampoco se rechaza la independencia al considerar el rango etario. El resultado se mantiene en los distintos grupos de edad.

c) ¿A qué conclusión llegó, al 5%, por rango etario?

Con un nivel del 5%, se concluye que **el tipo de comida y la frecuencia de consumo son independientes**, incluso al tener en cuenta el rango etario.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 4,59	 2	0,1007
Chi Cuadrado MV-G2  	 4,61	 2	0,0997
Coef.Conting.Cramer 	 0,08	  	      
Coef.Conting.Pearson	 0,11	  	      

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       4,50	 2	0,1052


| Rango_etario | Tipo_comida | Consumo    | Frecuencia |
|--------------|-------------|------------|------------|
| Niño/a       | Vegetariana | Diario     | 10         |
| Niño/a       | Vegetariana | Ocasional  | 15         |
| Adulto/a     | Vegetariana | Diario     | 25         |
| Adulto/a     | Vegetariana | Ocasional  | 30         |
| Anciano/a    | Vegetariana | Diario     | 20         |
| Anciano/a    | Vegetariana | Ocasional  | 10         |
| Niño/a       | Carnivora   | Diario     | 20         |
| Niño/a       | Carnivora   | Ocasional  | 15         |
| Adulto/a     | Carnivora   | Diario     | 30         |
| Adulto/a     | Carnivora   | Ocasional  | 20         |
| Anciano/a    | Carnivora   | Diario     | 20         |
| Anciano/a    | Carnivora   | Ocasional  | 25         |
| Niño/a       | Mixta       | Diario     | 30         |
| Niño/a       | Mixta       | Ocasional  | 10         |
| Adulto/a     | Mixta       | Diario     | 40         |
| Adulto/a     | Mixta       | Ocasional  | 30         |
| Anciano/a    | Mixta       | Diario     | 30         |
| Anciano/a    | Mixta       | Ocasional  | 20         |


---
### Ejercicio 14.
¿Es razonable suponer que existe una relación entre el uso de tecnología y la frecuencia de
uso, de acuerdo al nivel educativo?

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,0031. Se rechaza la hipótesis de independencia entre el tipo de tecnología y la frecuencia de uso. Las variables no son independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,0027. También se rechaza la independencia al considerar el nivel educativo. El resultado se mantiene en los distintos niveles.

c) ¿A qué conclusión llegó, al 5%, por nivel educativo?

Con un nivel del 5%, se concluye que **el tipo de tecnología y la frecuencia de uso no son independientes**, incluso al tener en cuenta el nivel educativo.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	11,58	 2	0,0031  

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
      11,79	 2	0,0027


| Nivel_educativo | Tecnologia   | Frecuencia_uso | Frecuencia |
|------------------|--------------|----------------|------------|
| Primario         | Computadora  | Frecuente      | 15         |
| Primario         | Computadora  | Poco_frecuente | 20         |
| Secundario       | Computadora  | Frecuente      | 25         |
| Secundario       | Computadora  | Poco_frecuente | 15         |
| Universitario    | Computadora  | Frecuente      | 40         |
| Universitario    | Computadora  | Poco_frecuente | 20         |
| Primario         | Telefono     | Frecuente      | 30         |
| Primario         | Telefono     | Poco_frecuente | 10         |
| Secundario       | Telefono     | Frecuente      | 35         |
| Secundario       | Telefono     | Poco_frecuente | 15         |
| Universitario    | Telefono     | Frecuente      | 50         |
| Universitario    | Telefono     | Poco_frecuente | 10         |
| Primario         | Tablet       | Frecuente      | 10         |
| Primario         | Tablet       | Poco_frecuente | 10         |
| Secundario       | Tablet       | Frecuente      | 20         |
| Secundario       | Tablet       | Poco_frecuente | 10         |
| Universitario    | Tablet       | Frecuente      | 15         |
| Universitario    | Tablet       | Poco_frecuente | 10         |

---

## Ejercicio 15.
Una encuesta compara la relación entre el medio de transporte y el género, estratificado por
frecuencia de uso.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,1207. No se rechaza la hipótesis de independencia entre medio de transporte y género. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,1245. Tampoco se rechaza la independencia al considerar la frecuencia de uso. El resultado se mantiene en los distintos niveles de frecuencia.

c) ¿Cómo interpreta, al 5%, el OR de Mantel-Haenszel?

El OR de MH es 1,46 y su intervalo de confianza (1,02 a 2,10) **no incluye al 1**, por lo tanto, al 5% de significación, **sí hay evidencia de dependencia**.\
Se concluye que **el medio de transporte y el género no son independientes**, incluso al considerar la frecuencia de uso.


Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 2,41	 1	0,1207
Chi Cuadrado MV-G2    	 2,41	 1	0,1205
Irwin-Fisher bilateral	 0,10	  	0,1417
Coef.Conting.Cramer   	 0,07	  	      
Kappa (Cohen)         	 0,09	  	      
Coef.Conting.Pearson  	 0,09	  	      
Coeficiente Phi       	 0,09	  	      

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 1,46	  0,91	  2,37
Odds Ratio 2/1	 0,68	  0,42	  1,10

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       2,36	 1	0,1245

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 1,46	  1,02	  2,10
MH Odds Ratio(2/1)	 0,68	  0,48	  0,98


| Transporte            | Genero     | Frecuencia_uso | Frecuencia |
|-----------------------|------------|----------------|------------|
| Auto                  | Masculino  | Diario         | 40         |
| Auto                  | Masculino  | Ocasional      | 27         |
| Auto                  | Femenino   | Diario         | 48         |
| Auto                  | Femenino   | Ocasional      | 35         |
| Transporte_publico    | Masculino  | Diario         | 42         |
| Transporte_publico    | Masculino  | Ocasional      | 23         |
| Transporte_publico    | Femenino   | Diario         | 30         |
| Transporte_publico    | Femenino   | Ocasional      | 25         |

---
## Ejercicio 16.
Un cine analiza la relación entre el tipo de película y la edad, estratificado de acuerdo al día
de la semana.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal < 0,0001. Se rechaza la hipótesis de independencia entre tipo de película y edad. Las variables no son independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH < 0,0001. También se rechaza la independencia al considerar el día de la semana. El resultado se mantiene tanto en días laborables como en fines de semana.

c) ¿A qué conclusión llegó, al nivel del 1%?

Con un nivel del 1%, se concluye que **el tipo de película y la edad no son independientes**, incluso al tener en cuenta el día de la semana.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p    
Chi Cuadrado Pearson	30,31	 4	<0,0001
Chi Cuadrado MV-G2  	30,12	 4	<0,0001
Coef.Conting.Cramer 	 0,16	  	       
Kappa (Cohen)       	-0,06	  	       
Coef.Conting.Pearson	 0,27	  	       

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p    
      29,85	 4	<0,0001



| Pelicula | Edad     | Momento         | Frecuencia |
|----------|----------|------------------|------------|
| Accion   | Niños    | Fin_de_semana    | 20         |
| Accion   | Niños    | Dia_laborable    | 10         |
| Accion   | Adultos  | Fin_de_semana    | 40         |
| Accion   | Adultos  | Dia_laborable    | 20         |
| Accion   | Mayores  | Fin_de_semana    | 10         |
| Accion   | Mayores  | Dia_laborable    | 15         |
| Comedia  | Niños    | Fin_de_semana    | 30         |
| Comedia  | Niños    | Dia_laborable    | 20         |
| Comedia  | Adultos  | Fin_de_semana    | 35         |
| Comedia  | Adultos  | Dia_laborable    | 25         |
| Comedia  | Mayores  | Fin_de_semana    | 20         |
| Comedia  | Mayores  | Dia_laborable    | 15         |
| Drama    | Niños    | Fin_de_semana    | 10         |
| Drama    | Niños    | Dia_laborable    | 5          |
| Drama    | Adultos  | Fin_de_semana    | 25         |
| Drama    | Adultos  | Dia_laborable    | 20         |
| Drama    | Mayores  | Fin_de_semana    | 30         |
| Drama    | Mayores  | Dia_laborable    | 25         |

---
## Ejercicio 17.
Un estudio evalúa si existe relación entre el consumo energético y el tipo de electrodoméstico, estratificado por el tipo de residencia.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,3063. No se rechaza la hipótesis de independencia entre el consumo energético y el tipo de electrodoméstico. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,3048. Tampoco se rechaza la independencia al considerar el tipo de residencia. El resultado se mantiene en zonas rurales y urbanas.

c) ¿A qué conclusión llegó, al nivel del 5%?

Con un nivel del 5%, se concluye que **el consumo energético y el tipo de electrodoméstico son independientes**, incluso al tener en cuenta la residencia.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 2,37	 2	0,3063 	      

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       2,38	 2	0,3048


| Electrodomestico | Uso  | Residencia | Frecuencia |
|------------------|------|------------|------------|
| Heladera         | Alto | Rural      | 50         |
| Heladera         | Alto | Urbana     | 100        |
| Heladera         | Bajo | Rural      | 30         |
| Heladera         | Bajo | Urbana     | 50         |
| Lavarropas       | Alto | Rural      | 40         |
| Lavarropas       | Alto | Urbana     | 90         |
| Lavarropas       | Bajo | Rural      | 20         |
| Lavarropas       | Bajo | Urbana     | 30         |
| Microondas       | Alto | Rural      | 10         |
| Microondas       | Alto | Urbana     | 50         |
| Microondas       | Bajo | Rural      | 15         |
| Microondas       | Bajo | Urbana     | 15         |

---
## Ejercicio 18.
Una editorial analiza la relación entre el tipo de libro y la frecuencia de lectura, estratificado por género.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,8194. No se rechaza la hipótesis de independencia entre tipo de libro y frecuencia de lectura. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,8171. Tampoco se rechaza la independencia al considerar el género. El resultado se mantiene en ambos grupos.

c) ¿A qué conclusión llegó el editor, al nivel del 10%?

Con un nivel del 10%, se concluye que **el tipo de libro y la frecuencia de lectura son independientes**, incluso al tener en cuenta el género.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 0,40	 2	0,8194
Chi Cuadrado MV-G2  	 0,40	 2	0,8184
Coef.Conting.Cramer 	 0,02	  	      
Coef.Conting.Pearson	 0,03	  	      

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       0,40	 2	0,8171


| Tipo_de_libro | Genero | Frecuencia_lectura | Frecuencia |
|---------------|--------|---------------------|------------|
| Novela        | Hombre | Alta                | 40         |
| Novela        | Hombre | Baja                | 30         |
| Novela        | Mujer  | Alta                | 60         |
| Novela        | Mujer  | Baja                | 40         |
| Ensayo        | Hombre | Alta                | 30         |
| Ensayo        | Hombre | Baja                | 20         |
| Ensayo        | Mujer  | Alta                | 40         |
| Ensayo        | Mujer  | Baja                | 30         |
| Cuento        | Hombre | Alta                | 20         |
| Cuento        | Hombre | Baja                | 10         |
| Cuento        | Mujer  | Alta                | 30         |
| Cuento        | Mujer  | Baja                | 20         |

---
## Ejercicio 19.
Un estudio analiza el uso de dispositivos electrónicos y la frecuencia de uso, estratificado por
grupo etario.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,8194. No se rechaza la hipótesis de independencia entre el tipo de dispositivo y la frecuencia de uso. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,8171. Tampoco se rechaza la independencia al considerar el grupo etario. El resultado se mantiene en jóvenes, adultos y mayores.

c) ¿A qué conclusión llegó, al nivel del 10%?

Con un nivel del 10%, se concluye que **el tipo de dispositivo electrónico y la frecuencia de uso son independientes**, incluso al tener en cuenta el grupo etario.

Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p   
Chi Cuadrado Pearson	 0,40	 2	0,8194
Chi Cuadrado MV-G2  	 0,40	 2	0,8184
Coef.Conting.Cramer 	 0,02	  	      
Coef.Conting.Pearson	 0,03	  	      

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       0,40	 2	0,8171


| Dispositivo | Frecuencia_uso     | Grupo_etario | Frecuencia |
|-------------|---------------------|--------------|------------|
| Smartphone  | Frecuente           | Jovenes      | 50         |
| Smartphone  | Frecuente           | Adultos      | 40         |
| Smartphone  | Frecuente           | Mayores      | 20         |
| Smartphone  | Poco_frecuente      | Jovenes      | 20         |
| Smartphone  | Poco_frecuente      | Adultos      | 25         |
| Smartphone  | Poco_frecuente      | Mayores      | 15         |
| Laptop      | Frecuente           | Jovenes      | 30         |
| Laptop      | Frecuente           | Adultos      | 35         |
| Laptop      | Frecuente           | Mayores      | 15         |
| Laptop      | Poco_frecuente      | Jovenes      | 15         |
| Laptop      | Poco_frecuente      | Adultos      | 20         |
| Laptop      | Poco_frecuente      | Mayores      | 10         |
| Tablet      | Frecuente           | Jovenes      | 20         |
| Tablet      | Frecuente           | Adultos      | 15         |
| Tablet      | Frecuente           | Mayores      | 10         |
| Tablet      | Poco_frecuente      | Jovenes      | 10         |
| Tablet      | Poco_frecuente      | Adultos      | 10         |
| Tablet      | Poco_frecuente      | Mayores      | 5          |

---
## Ejercicio 20.
En un gimnasio se estudia la relación entre el tipo de ejercicio y la frecuencia de concurrencia,
estratificado por género.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,1893. No se rechaza la hipótesis de independencia entre tipo de ejercicio y frecuencia de concurrencia. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,2040. Tampoco se rechaza la independencia al considerar el género. El resultado se mantiene en ambos grupos.

c) ¿Cómo interpreta, al 5%, los OR de acuerdo al género?

El OR de Mantel-Haenszel tiene un intervalo de confianza que **incluye al 1**, lo que indica que **no es estadísticamente significativo** al nivel del 5%.
Por lo tanto, se concluye que **el tipo de ejercicio y la frecuencia de concurrencia son independientes**, incluso al considerar el género.


Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 1,72	 1	0,1893
Chi Cuadrado MV-G2    	 1,73	 1	0,1883
Irwin-Fisher bilateral	-0,09	  	0,1966
Coef.Conting.Cramer   	 0,06	  	      
Kappa (Cohen)         	-0,09	  	      
Coef.Conting.Pearson  	 0,09	  	      
Coeficiente Phi       	-0,09	  	      

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 0,68	  0,39	  1,21
Odds Ratio 2/1	 1,47	  0,83	  2,59

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       1,61	 1	0,2040

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%


| Ejercicio | Frecuencia | Genero     | Frecuencia_valor |
|-----------|------------|------------|------------------|
| Cardio    | Alta       | Masculino  | 23               |
| Cardio    | Alta       | Femenino   | 45               |
| Cardio    | Baja       | Masculino  | 20               |
| Cardio    | Baja       | Femenino   | 24               |
| Fuerza    | Alta       | Masculino  | 50               |
| Fuerza    | Alta       | Femenino   | 18               |
| Fuerza    | Baja       | Masculino  | 18               |
| Fuerza    | Baja       | Femenino   | 12               |

---
## Ejercicio 21.
Un restaurante analiza las preferencias entre el tipo de comida rápida y el rango etario según
el día de la semana.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal < 0,0001. Se rechaza la hipótesis de independencia entre tipo de comida y rango etario. Las variables no son independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH < 0,0001. También se rechaza la independencia al considerar el día de la semana. El resultado se mantiene tanto entre semana como en fines de semana.

c) ¿A qué conclusión llegó, al nivel del 10%?

Con un nivel del 10%, se concluye que **el tipo de comida rápida y el rango etario no son independientes**, incluso al tener en cuenta el día de la semana.


Estadísticos para la tabla marginal

    Estadístico     	Valor	gl	  p    
Chi Cuadrado Pearson	30,11	 4	<0,0001
Chi Cuadrado MV-G2  	29,85	 4	<0,0001
Coef.Conting.Cramer 	 0,15	  	       
Kappa (Cohen)       	-0,07	  	       
Coef.Conting.Pearson	 0,26	  	       

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p    
      29,90	 4	<0,0001


| Comida      | Dia             | Grupo_etario | Frecuencia |
|-------------|------------------|--------------|------------|
| Hamburguesa | Entre_semana     | Niños        | 25         |
| Hamburguesa | Entre_semana     | Adultos      | 30         |
| Hamburguesa | Entre_semana     | Mayores      | 10         |
| Hamburguesa | Fin_de_semana    | Niños        | 35         |
| Hamburguesa | Fin_de_semana    | Adultos      | 40         |
| Hamburguesa | Fin_de_semana    | Mayores      | 15         |
| Pizza       | Entre_semana     | Niños        | 20         |
| Pizza       | Entre_semana     | Adultos      | 25         |
| Pizza       | Entre_semana     | Mayores      | 15         |
| Pizza       | Fin_de_semana    | Niños        | 30         |
| Pizza       | Fin_de_semana    | Adultos      | 35         |
| Pizza       | Fin_de_semana    | Mayores      | 20         |
| Ensalada    | Entre_semana     | Niños        | 10         |
| Ensalada    | Entre_semana     | Adultos      | 20         |
| Ensalada    | Entre_semana     | Mayores      | 25         |
| Ensalada    | Fin_de_semana    | Niños        | 15         |
| Ensalada    | Fin_de_semana    | Adultos      | 25         |
| Ensalada    | Fin_de_semana    | Mayores      | 30         |

---
## Ejercicio 22.
Un banco estudia la relación entre el tipo de servicio y la frecuencia de uso, estratificado por tipo de cliente.

a) ¿Cuál es el p-valor para la tabla marginal?

p-valor marginal = 0,2244. No se rechaza la hipótesis de independencia entre tipo de servicio y frecuencia de uso. Las variables parecen independientes en el total.

b) ¿Cuál es el p-valor de la prueba de CMH corregido por el estrato?

p-valor CMH = 0,3043. Tampoco se rechaza la independencia al considerar el tipo de cliente. El resultado se mantiene en clientes particulares y empresas.

c) ¿A qué conclusión llegó, al 5%, según cliente?

Con un nivel del 5%, se concluye que **el tipo de servicio y la frecuencia de uso son independientes**, incluso al tener en cuenta el tipo de cliente.


Estadísticos para la tabla marginal

     Estadístico      	Valor	gl	  p   
Chi Cuadrado Pearson  	 1,48	 1	0,2244
Chi Cuadrado MV-G2    	 1,49	 1	0,2224
Irwin-Fisher bilateral	-0,09	  	0,2350
Coef.Conting.Cramer   	 0,06	  	      
Kappa (Cohen)         	-0,09	  	      
Coef.Conting.Pearson  	 0,09	  	      
Coeficiente Phi       	-0,09	  	      

Cocientes de chance (odds ratio)

 Estadístico  	Estim	LI 95%	LS 95%
Odds Ratio 1/2	 0,69	  0,38	  1,25
Odds Ratio 2/1	 1,45	  0,80	  2,62

Estadísticos corregidos por efecto de estrato
Prueba de Cochran-Mantel-Haenszel
Estadístico	gl	  p   
       1,06	 1	0,3043

Cocientes de chance (odds ratio) de Mantel-Haenszel
   Estadístico    	Estim	LI 95%	LS 95%
MH Odds Ratio(1/2)	 0,73	  0,48	  1,13
MH Odds Ratio(2/1)	 1,36	  0,89	  2,10



| Servicio    | Frecuencia | Cliente    | Frecuencia |
|-------------|------------|------------|------------|
| Ahorros     | Alta       | Particular | 50         |
| Ahorros     | Alta       | Empresa    | 23         |
| Ahorros     | Baja       | Particular | 30         |
| Ahorros     | Baja       | Empresa    | 18         |
| Inversiones | Alta       | Particular | 20         |
| Inversiones | Alta       | Empresa    | 35         |
| Inversiones | Baja       | Particular | 15         |
| Inversiones | Baja       | Empresa    | 10         |

---

