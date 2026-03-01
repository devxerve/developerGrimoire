---
References:
  - "[[bbdd_relacionales.pdf]]"
cssclasses:
  - center-titles
  - page-grid
  - pen-red
tags:
  - databases
---

# :fas_database: Traducción modelo entidad-relación a modelo relacional
## Reglas de traducción
### 1. Entidad --> tabla
Todas las entidades son directamente una tabla, por cada entidad existe una tabla en el modelo relacional.
### 2. Normas
#### Primera norma:
el orden de los atributos no es significativo
#### Segunda norma: relaciones:
##### 1:N
migro la clave primaria de la entidad que es 1 a la entidad que es N (el código de departamento va a pasar a nombre)
##### N:N
se traducirá en una tabla nueva, en la cual migraremos las dos claves primarias, que serán ajenas
##### 1:1
se puede migrar hacia el sentido que genere menos nulos (en este caso genera menos nulos si migramos la clave primaria de empleado a departamento, creando un atributo empleado_jefe para la tabla departamento). 
