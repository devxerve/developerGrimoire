---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Modificación en la definición de las tablas sentencia alter table
Sirve para modificar la estructura de la tabla, hay diferentes tipos
## Sintaxis

```sql cpp title:Alter_table
ALTER TABLE {nombre_tabla}
alter_especification [, alter_especification ...];
```

## alter_especification
```sql title:Alter_especification
ADD [COLUMN] especificación_columna
ADD [CONSTRAINT [symbol]] PRIMARY KEY (index_col_name,...) 
ADD [CONSTRAINT [symbol]] UNIQUE [name] (col_name,...) 
ADD [CONSTRAINT [symbol]] FOREIGN KEY [name] (col_name,...) [reference_definition]
CHANGE [COLUMN] old_col_name especificación_columna 
DROP [COLUMN] col_name
```
