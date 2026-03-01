---
título: JOINs en SQL
lenguaje: SQL
categoría: Bases de datos
fecha: 2025-01-01
tags:
  - sql
  - joins
  - bases-de-datos
estado: borrador
---

# SQL — JOINs

## Resumen
> Combinación de filas de dos o más tablas basada en una condición relacionada.

## Tipos de JOIN

| JOIN              | Descripción                                     |
| ----------------- | ----------------------------------------------- |
| `INNER JOIN`      | Solo filas con coincidencia en ambas tablas     |
| `LEFT JOIN`       | Todas las filas de la izquierda + coincidencias |
| `RIGHT JOIN`      | Todas las filas de la derecha + coincidencias   |
| `FULL OUTER JOIN` | Todas las filas de ambas tablas                 |
|                   |                                                 |

## Ejemplos
```sql
-- Tablas: pedidos(id, cliente_id, total) y clientes(id, nombre)

-- INNER JOIN: pedidos con su cliente
SELECT p.id, c.nombre, p.total
FROM pedidos p
INNER JOIN clientes c ON p.cliente_id = c.id;

-- LEFT JOIN: todos los clientes, tengan o no pedidos
SELECT c.nombre, p.total
FROM clientes c
LEFT JOIN pedidos p ON c.id = p.cliente_id;
```

## Ver también
- [[Notes/SQL - Basics|Fundamentos de SQL]]

## Referencias
- 
