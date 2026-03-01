---
título: Fundamentos de SQL
lenguaje: SQL
categoría: Bases de datos
fecha: 2025-01-01
tags:
  - sql
  - bases-de-datos
estado: borrador
---

# SQL — Basics

## Resumen
> Comandos esenciales de SQL para crear, modificar y consultar bases de datos relacionales.

## Concepto

### DDL — Definición de datos
```sql
-- Crear tabla
CREATE TABLE usuarios (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE,
    fecha_registro DATE DEFAULT CURRENT_DATE
);

-- Modificar tabla
ALTER TABLE usuarios ADD COLUMN activo BOOLEAN DEFAULT TRUE;

-- Eliminar tabla
DROP TABLE usuarios;
```

### DML — Manipulación de datos
```sql
-- Insertar
INSERT INTO usuarios (nombre, email) VALUES ('Ana', 'ana@mail.com');

-- Consultar
SELECT * FROM usuarios WHERE activo = TRUE ORDER BY nombre;

-- Actualizar
UPDATE usuarios SET activo = FALSE WHERE id = 3;

-- Eliminar
DELETE FROM usuarios WHERE id = 3;
```

## Ver también
- [[Notes/SQL - JOINs|JOINs en SQL]]

## Referencias
- 
