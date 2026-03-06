---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Cláusulas de la sentencia select

## All | disctint
Permiten eliminar filas repetidas en la tabla resultante al ejecutar la consulta.

<mark style="background: #FFF3A3A6;">ALL</mark>: Se mostrarán todas las opciones (Repeticiones incluidas). Opción default 

<mark style="background: #FFF3A3A6;">DISCTINT</mark>: Fuerza a que solo se muestren registros únicos, es decir, elimina los repetidos. 
### Sintaxis
```SQL cpp title:Sintaxis_select
SELECT [ALL | DISCTINT] expresion [, expresion...]
[FROM tabla];
```

## Order by
Podemos querer mostrar el resultado en un orden determinado, para eso utilizamos esta cláusula, si no se especifica, las filas se muestran en cualquier orden. Argumentos:

<mark style="background: #FFF3A3A6;">ASC</mark>: Permite ordenar el resultado de la consulta de forma ascendente, Opción default.

<mark style="background: #FFF3A3A6;">DESC</mark>: Permite ordenar el resultado de la consulta de forma descendente. 

La posición de la columna que se usa para ordenar también sirve como argumento (en vez del nombre)
### Sintaxis

```SQL
SELECT [ALL | DISCTINT] expresion [, expresion...]
[FROM tabla
[ORDER BY {nombre_columna | posicion_columna} [ASC | DESC],...]
];
```

## Where
Sirve para poner condiciones sobre los registros que se mostraran, es decir, pone una condición a la consulta.

<mark style="background: #ADCCFFA6;">Las condiciones tienen estos elementos </mark>
- Nombre columna 
- Constantes (Números que no cambian o cadenas de textos fijas)
- Expresiones (Algebraicas o con funciones propias de MySQL)
- [[Predicados Avanzados - IN, BETWEEN, IS NULL, LIKE, ALL , ANY , EXISTS ]]
- Paréntesis: Permiten alterar la prioridad de los operadores 
- Operadores

```SQL title="Comparación SQL"
WHERE edad        >  18
WHERE precio      <  100
WHERE salario     >= 1500
WHERE cantidad    <= 20
WHERE nombre      =  'Juan'
WHERE tipo        != 'admin'
WHERE puntuacion  !> 80
WHERE ranking     !< 5
```


```SQL title="Operadores logicos SQL"
WHERE edad > 18 AND ciudad = 'Madrid'
WHERE precio < 100 OR cantidad > 5
WHERE NOT estado = 'activo'
```
## Group by
Realizan operaciones sobre un conjunto de todos ellos, y devuelve <mark style="background: #FF5582A6;">UN UNICO VALOR</mark> agregado de todos ellos.

> [!warning] IMPORTANTE
> SI USAS EL GROUP BY NO SE PUEDE USAR SELECT *

Casos de uso:
- AVG = calcula la media aritmética de los valores agrupados. Solo columnas numéricas
- SUM = Calcula la suma de los valores agrupados. Solo columnas numéricas.
- MAX = Devuelve el valor máximo de los valores agrupados.
- MIN = Devuelve el valor mínimo de los valores agrupados.
- COUNT = Devuelve el número de filas agrupadas.

```sql title:Group_by
SELECT profesor, COUNT(*) 
FROM asignatura 
WHERE ciclo='DAM' 
GROUP BY profesor;
-- Numero asignaturas impartidas por profesor en DAM --
```

## Having

Filtra grupos después de GROUP BY
### Sintaxis
```SQL title:Having
SELECT asignatura, AVG (nota_1Ev) AS 'Nota media en 1Ev' 
FROM alumno_asignatura 
GROUP BY asignatura 
HAVING AVG(nota_1Ev)>7  
-- Solo asinaturas cuya nota media en la primera ev sea mayor de 7
```

