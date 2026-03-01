---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# :dev_mysql_original: Modificación En la Definición De Las Tablas Sentencia Alter Table
Sirve para modificar la estructura de la tabla, hay diferentes tipos
## Sintaxis

```sql cpp title:Alter_table
ALTER TABLE {nombre_tabla}
alter_especification [, alter_especification ...];
```

## alter_especification
```SQL title:Alter_especification
ADD [COLUMN] especificación_columna
ADD [CONSTRAINT [symbol]] PRIMARY KEY (index_col_name,...) 
ADD [CONSTRAINT [symbol]] UNIQUE [name] (col_name,...) 
ADD [CONSTRAINT [symbol]] FOREIGN KEY [name] (col_name,...) [reference_definition]
CHANGE [COLUMN] old_col_name especificación_columna 
DROP [COLUMN] col_name
```
