---
tags:
  - sql
cssclasses: pageGrid
---


# :dev_mysql_original: Predicados avanzados - in, between, is null, like
## Predicado in
Expresa pertenencia a conjuntos, me permite comprobar si el resultado de una expresión está o no incluido en un conjunto determinado
```SQL title="Predicado IN" Group="Predicado IN"
SELECT * FROM asignatura
WHERE curso = 1 AND ciclo IN(`DAM`, `AYF`)
```
```SQL title="Predicado [NOT]IN" Group="Predicado IN"
SELECT * FROM asignatura
WHERE curso = 1 AND ciclo NOT IN(`DAM`, `AYF`)
```
## Predicado between
Permite comprobar si el resultado de una expresión está o no incluido entre dos valores dados

```SQL title="Predicado Between" Group="Between"
SELECT * FROM alumno
WHERE YEAR (fecha_nacimiento) BETWEEN 1990 AND 1999;
```
```SQL title="Predicado [NOT]BETWEEN" Group="Between"
SELECT * FROM alumno
 WHERE NOT YEAR(fecha_nacimiento) BETWEEN 1990 AND 1999;
```

## Predicado null
Comprueba si un campo es o no nulo, se usa con el operando <mark style="background: #D2B3FFA6;">IS</mark>
```SQL title="Predicado NULL" Group="Predicado NULL"
SELECT *
FROM asignatura
WHERE profesor IS NULL;
```
```SQL title="Predicado [NOT] NULL" Group="Predicado NULL"
SELECT *
FROM asignatura
WHERE profesor IS NOT NULL;
```

## Predicado all
Es una comparación que es verdadera si es cierta para todos los valores devueltos por la [[Subconsultas|subconsulta]]

```SQL title="Predicado ALL"
SELECT * FROM asignatura
WHERE curso = 2 AND ciclo = "DAM"
-- Cuando las horas sean mayores que TODAS las horas de las asignaturas de primero de DAM -- 
AND horas > ALL(SELECT horas FROM asignatura
		WHERE curso = 1 AND ciclo "DAM");
```

## Predicado any
Es verdadero si la comparación es cierta para al menos UNO de los valores de la subconsulta
```SQL title="Predicado ANY"
SELECT * FROM asignatura
WHERE curso = 2 AND ciclo = "DAM"
  AND horas > ANY (SELECT horas FROM asignatura
					WHERE curso = 1 AND ciclo = "DAM");
```

## Predicado exists
Se busca saber si la subconsulta devuelve algo o no.

```SQL title="Predicado EXISTS" group="Exists"
-- Selecciona la columna 1 de la tabla 1, si EXISTEN datos en la tabla 2
SELECT columna1 FROM t1 WHERE EXISTS(SELECT* FROM t2);
```
```SQL title="Predicado [NOT] EXISTS" group="Exists"
-- Selecciona la columna 1 de la tabla 1, si NO existen datos en la tabla 2 --
SELECT columna1 FROM t1 WHERE NOT EXISTS(SELECT* FROM t2);
```

