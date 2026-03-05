---
tags:
  - sql
cssclasses:
  - "centerTitles "
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Creacion de bases, tablas y vistas sentencia create
## Tablas
<mark style="background: #FFB86CA6;">(Código que crea el ejemplo de los apuntes)</mark>
```SQL Cpp title:CREATE_EJEMPLO_APUNTES
CREATE TABLE clientes(
codigo_cliente BIGINT NOT NULL AUTO_INCREMENT UNIQUE KEY ,
dni varchar(11) NOT NULL PRIMARY KEY, 
nombre varchar(50) DEFAULT NULL, 
apellido varchar(50) DEFAULT NULL,
direccion varchar(100) DEFAULT NULL
);

CREATE TABLE articulos(
codigo varchar(11) NOT NULL PRIMARY KEY,
descripcion text DEFAULT NULL,
stock bigint DEFAULT NULL
);

CREATE TABLE pedidos(
codigo varchar(11) NOT NULL PRIMARY KEY,
cliente bigint NOT NULL UNIQUE KEY,
fecha_pedido timestamp DEFAULT CURRENT_TIMESTAMP,
FOREIGN KEY(cliente) REFERENCES clientes(codigo_cliente)
	ON DELETE NO ACTION ON UPDATE CASCADE
);

CREATE TABLE item_pedidos(
codigo_pedido varchar(11) NOT NULL,
codigo_articulo varchar(11) NOT NULL UNIQUE KEY,
cantidad integer NOT NULL,
PRIMARY KEY(codigo_pedido, codigo_articulo),
FOREIGN KEY(codigo_pedido) REFERENCES pedidos (codigo)
	ON DELETE NO ACTION ON UPDATE CASCADE,
FOREIGN KEY(codigo_articulo) REFERENCES articulos (codigo)
	ON DELETE NO ACTION ON UPDATE CASCADE
);
```

![[ejemplo_create.png]]


