---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Actualización de registros sentencia update

Permite modificar el contenido de cualquier columna/fila de las tablas de la base de datos, su sintaxis es

```sql title:Sentencia_update
UPDATE nombre_tabla
SET nombre_col1={expr1|DEFAULT}[,nombre_col2={expre2 | DEFAULT}...]
[WHERE condicion]
[ORDER BY orden_solicitado];
```

> [!WARNING]
> SI SE OMITE EL WHERE SE MODIFICAN TODAS LAS FILAS DE LA TABLA

# Ejemplo

<mark style="background: #FF5582A6;">Aumenta 10 horas a cada una de las asignaturas del ciclo formativo de DAM</mark>

```sql title:Ejemplo_Update
UPDATE asignatura
SET horas = horas+10
WHERE ciclo = 'DAM';
```


