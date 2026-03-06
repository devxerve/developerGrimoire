---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Inserción grandes cantidades de registros
Se realiza con el comando 

```SQL cpp title:Comandos_variables_sistema_insercion_archivos
SET SQL_SAFE_UPDATES = 0;
SHOW VARIABLES LIKE 'secure_file_priv';
```

```SQL cpp title:Insercion_archivo_texto_plano
LOAD DATA INFILE "C:\\ProgramData\\MySQL\\MySQL Server 8.0\\Uploads\\alumnos2.txt"
REPLACE 
INTO TABLE alumno
FIELDS TERMINATED BY "\t"
IGNORE 2 LINES;
```

```SQL cpp title:Insercion_archivo_XML
LOAD XML INFILE "C:\\ProgramData\\MySQL\\MySQL Server 8.0\\Uploads\\alumnos.xml"
REPLACE 
INTO TABLE alumno
ROWS IDENTIFIED BY "<row>";
```
