---
References:
  - "[[almacenamiento_informacion.pdf]]"
cssclasses:
  - center-titles
  - page-grid
  - pen-red
tags:
  - databases
---

# :fas_database: Elementos de una bbdd
## Niveles de abstracción/estructura de una base de datos

### Nivel interno
Es la estructura física de una base de datos, define básicamente como están guardados los datos en disco.
### Nivel global/conceptual
La teoría de como se organizan los datos, básicamente la estructura interna de la base de datos, con sus campos y la descripción de cada uno de ellos. Aquí se definen las relaciones entre datos. 
### Nivel externo
Como percibe los datos el usuario final, a través de los Sistemas Gestores de Bases de datos.
## Tipo de bases de datos
- Jerárquicas: Estructura padres-hijos.
- Base de datos en red: Estructura padres-hijos (Un hijo puede tener varios padres)
- Relacionales: Existen relaciones entre distintas tuplas de datos mediante un modelo relacional basado en claves primarias, secundarias y foráneas. 
- Base de datos orientada a objetos: un objeto es una entidad con un estado o datos asociados, y un comportamiento determinado. 
## Sistemas gestores de bases de datos (SGBD)
- Permiten almacenar, acceder y modificar datos.
- Garantizan integridad y consistencia de los datos.
- Proporcionan un sistema de seguridad 
- Proporcionan un diccionario de datos
- Se puede monitorizar la base de datos desde ellos
- Permiten el uso de transacciones (una acción ocurre en una parte de la base de datos, y si no ocurre en la parte receptora entonces se revierte a la situación anterior)
- Permiten el uso simultaneo de las bases de datos (Concurrencia)
- Cumplen con los estándares ANSI en cuanto la abstracción o estructura de las bases de datos.
- Tienen herramientas de backup
