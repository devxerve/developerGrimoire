---
tags:
  - sql
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :dev_mysql_original: Subconsultas
La idea es que una consulta usa en la cláusula where o having otra consulta para la condición
<mark style="background: #FF5582A6;">REGLAS:</mark>
- La subconsulta debe ir entre paréntesis
- El resultado debe estar compuesto por una única columna 
- Puede container a su vez otras subconsultas

## Operadores de subconsultas:
Los operadores de subconsultas son los operadores de comparación y los [[Predicados Avanzados - IN, BETWEEN, IS NULL, LIKE, ALL , ANY , EXISTS]]

![[Operadores#Operadores Relacionales / De Comparación#Resumen]]

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






