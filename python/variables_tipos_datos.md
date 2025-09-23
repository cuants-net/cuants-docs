# Variables y tipos de datos en Python

## 1. Tipos de datos en Python

Python ofrece varios tipos de datos ya listos para usar:

|Grupo |Tipo |Ejemplo |Mutable |
|-----------|-------|--------|--------|
| Numéricos  | int       | 34          | no         |
|            | float     | 1.62      | no         |
|            | complex   | 2+8j         | no         |
|Booleanos | bool | True, False | no|
| Secuencias | list      | [1, 2, 3]          | si         |
|            | tuple     | (3, 4, True)       | no         |
|            | range     | range(5)           | no         |
| Texto      | str       | "casa" | no         |
| Binarios   | bytes     | b'coche'           | no         |
|            | bytearray | bytearray(b"Hola") | si         |
| Conjuntos  | set       |  {3, True, 5}       | si         |
|            | frozenset |  frozenset([1, 2])  | no         |
| Mapas      | dict      | {'x': 1, 'y': 2}   | si         |



## 2. Literales y Variables

* **Literales**: valores escritos directamente.  42, "hola", 3.14.

* **Variables**: etiquetas que apuntan a esos objetos en memoria.

```python
puntuacion = 23
ciudad = "Nueva York"
```

La variable **no guarda el valor directamente**: guarda una **referencia** al objeto en memoria.\
Esto explica fenómenos como:

```python
a = [1, 2, 3]
b = a      # b apunta al mismo objeto
b[0] = 99
print(a)
```
[99, 2, 3]

## 3. Memoria y gestión

* Python usa **conteo de referencias**: cada objeto sabe cuántas variables lo apuntan.
* Cuando un objeto queda con 0 referencias → entra en acción el **garbage collector** y libera memoria.
* Podés borrar variables con `del nombre_variable`.


## 4. Mutabilidad

**mutables:** Se pueden modificar, métodos como .append(), .update(), .remove() modifican en el lugar.

**inmutables:** No se pueden cambiar, osea cualquier operación genera un objeto nuevo.

Ejemplo:
```python
x = "hola"
y = x
x = x.upper()  # crea un nuevo str
print(y)  # "hola" (no cambió)

lst = [1, 2, 3]
lst2 = lst
lst2.append(4) 
print(lst)
```
[1, 2, 3, 4]  (sí cambió)

## 5. Boleanos
* Dos valores especiales: True (1) y False (0).

* Cualquier objeto en Python puede evaluarse como verdadero/falso:

  * Falsos: 0, 0.0, '`, [], {}, None.

  * Verdaderos: casi todo lo demás.

Operadores lógicos:

* and (y)

* or (o)

* not (negación)

* Cortocircuito: si ya se sabe el resultado, no evalúa el resto.
