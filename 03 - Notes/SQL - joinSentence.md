---
tags:
  - sql
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :dev_mysql_original: Join
Sirve para hacer tablas intermedias

 > [!warning]
> IMPORTANTE USAR ALIAS Y EN EL WHERE QUITAR "ESPURIAS" IGUALANDO FK CON PK DE LA OTRA TABLA
 
> [!note]
> Se usan 2 tablas, y seleccionando las tablas que se quieren unir se ejecutan en una sentencia select

<mark style="background: #FF5582A6;">HAY 3 FORMAS</mark>

## Inner join
```SQL title:Inner_Join
SELECT a.*, p.nombre, p.apellido 
FROM asignatura a INNER JOIN profesor p 
ON a.profesor=p.DNI;
--Devuelve Todas las columnas de asignatura nombre y apellido del profesor Solo asignaturas con profesor (INNER JOIN excluye las que tienen profesor = NULL o sin coincidencia)-- 
```

## Left join
```sql title:Left_Join
SELECT *  FROM alumno_asignatura aa  LEFT JOIN alumno al ON aa.alumno = al.dni LEFT JOIN asignatura a ON aa.asignatura = a.codigo GROUP BY aa.dni;
-- Este ejemplo muestra todos los registros de `alumno_asignatura`, incluyendo alumnos sin asignaturas o asignaturas sin alumnos, con NULL donde no hay coincidencia.-- 
```

## Right join
```sql title:Right_Join
SELECT *  FROM alumno_asignatura aa  RIGHT JOIN alumno al ON aa.alumno = al.dni RIGHT JOIN asignatura a ON aa.asignatura = a.codigo GROUP BY al.dni;
--Aquí se incluyen todos los alumnos y asignaturas, incluso aquellos sin matrículas asociadas, usando NULL para los datos faltantes.--
```

## Diferencias clave

|Tipo JOIN|Tabla izquierda|Tabla derecha|Sin coincidencia|
|---|---|---|---|
|INNER (implícito)|Solo coincidentes|Solo coincidentes|Excluidas|
|LEFT JOIN|Todas|Coincidentes o NULL|Muestra izquierda|
|RIGHT JOIN|Coincidentes o NULL|Todas|Muestra derecha|
