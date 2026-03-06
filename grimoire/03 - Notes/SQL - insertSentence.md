---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Inserción - sentencia insert

La sentencia insert permite insertar una o varias filas en una tabla de la base de datos
## Tipos de sintaxis

### Insert simple
```sql title:Insert_Simple
INSERT INTO{nombre_tabla | nombre_vista} [(lista_columnas)]
VALUES (lista_valores);
```

**nombre_tabla** --> Corresponde a la tabla o vista donde vamos a insertar los datos
**lista_columnas** --> Lista de columnas en las cuales vamos a introducir datos
**lista_valores** --> Lista de valores a introducir en la tabla

### Insert simple sin especificar columnas
> [!example] Ejemplo de valores a insertar
>  Inserta en la tabla profesroes a César Mateos con DNI 65987452N, email cesar.materos@gmail.com y teléfono 652321452

```SQL title:Insert_simple_sin-columnas 
INSERT INTO profesor 
VALUES 
('65987452N', 'César', 'Mateos', 'cesar.materos@gmail.com', '652321452', NULL)
```

### Insert múltiple

> [!example] Ejemplo de valores a insertar
> Inserta los profesores: 
> • Julia Pérez con DNI 12457843N, email julia.perez@ufv.es y número de teléfno 698745487. 
> • Blanca Sánchez, con DNI 54123654B, email b.sanchez@gmail.com,número de teléfono 632145854 y dirección Rúa Mayor, 15, Madrid. 
> • Pedro, con DNI 74854521L, teléfono 652145487 y email pedro@gmail.com.

```SQL title:Insert_Multiple
INSERT INTO profesor 
VALUES 
('12457843N', 'Julia', 'Pérez', 'julia.perez@ufv.es', '698745487', NULL), 
('54123654B', 'Blanca', 'Sánchez', 'b.sanchez@gmail.com', '632145854', 'Rúa Mayor, 15, Madrid'),
('74854521L', 'Pedro', NULL, 'pedro@gmail.com', '652145487', NULL);
```


