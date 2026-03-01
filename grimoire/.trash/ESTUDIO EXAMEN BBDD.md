---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

NO SE PUEDE TENER APUNTES
# Bloque 1 Mer Y Mr

## Ejercicio 1
[[Ejercicio Gimnasio (Enunciado lo tiene carmen).drawio]]
![[Ejercicio Gimnasio (Enunciado lo tiene carmen).jpg]]

## Ejercicio 2
[[Ejercicio Gerentes (Ejercicio 8 Ejercicios II PDF).drawio]]
![[Ejercicio Gerentes (Ejercicio 8 Ejercicios II PDF).jpg]]

# Bloque 2 - Consultas

## Ejercicios Examen Otros Años

<mark style="background: #FF5582A6;">CREAR ESTA BASE DE DATOS</mark>

```SQL title:CREATE_MODELO_EXAMEN
DROP TABLE IF EXISTS `autores`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `autores` (
  `id_autor` varchar(9) NOT NULL,
  `nombre` varchar(20) NOT NULL,
  `apellido1` varchar(20) NOT NULL,
  `apellido2` varchar(20) DEFAULT NULL,
  `fecha_nacimiento` date NOT NULL,
  `nacionalidad` varchar(15) NOT NULL,
  PRIMARY KEY (`id_autor`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `autores`
--

LOCK TABLES `autores` WRITE;
/*!40000 ALTER TABLE `autores` DISABLE KEYS */;
INSERT INTO `autores` VALUES ('AUT001','Gabriel','García','Márquez','1927-03-06','Colombia'),('AUT002','J.K.','Rowling',NULL,'1965-07-31','Reino Unido'),('AUT003','Agatha','Christie',NULL,'1890-09-15','Reino Unido'),('AUT004','Miguel','de Cervantes','Saavedra','1547-09-29','España'),('AUT005','Isabel','Allende',NULL,'1942-08-02','Chile');
/*!40000 ALTER TABLE `autores` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `categorias`
--

DROP TABLE IF EXISTS `categorias`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `categorias` (
  `id_categoria` int NOT NULL AUTO_INCREMENT,
  `nombre_categoria` varchar(15) NOT NULL,
  `Descripcion` text,
  PRIMARY KEY (`id_categoria`),
  UNIQUE KEY `nombre_categoria` (`nombre_categoria`)
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `categorias`
--

LOCK TABLES `categorias` WRITE;
/*!40000 ALTER TABLE `categorias` DISABLE KEYS */;
INSERT INTO `categorias` VALUES (1,'Novela','Novelas de ficción literaria'),(2,'Fantasía','Obras de fantasía y magia'),(3,'Policial','Novelas de misterio y crimen'),(4,'Clásicos','Obras clásicas de la literatura universal'),(5,'Histórica','Novelas basadas en hechos históricos');
/*!40000 ALTER TABLE `categorias` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `libros`
--

DROP TABLE IF EXISTS `libros`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `libros` (
  `id_libro` varchar(13) NOT NULL,
  `titulo` varchar(30) NOT NULL,
  `num_paginas` int NOT NULL,
  `id_categoria` int NOT NULL AUTO_INCREMENT,
  `id_autor` varchar(9) NOT NULL,
  PRIMARY KEY (`id_libro`),
  UNIQUE KEY `titulo` (`titulo`),
  KEY `id_categoria` (`id_categoria`),
  KEY `id_autor` (`id_autor`),
  CONSTRAINT `libros_ibfk_1` FOREIGN KEY (`id_categoria`) REFERENCES `categorias` (`id_categoria`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `libros_ibfk_2` FOREIGN KEY (`id_autor`) REFERENCES `autores` (`id_autor`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `libros`
--

LOCK TABLES `libros` WRITE;
/*!40000 ALTER TABLE `libros` DISABLE KEYS */;
INSERT INTO `libros` VALUES ('LIB001','Cien años de soledad',417,1,'AUT001'),('LIB002','HP y la piedra filosofal',223,2,'AUT002'),('LIB003','Diez negritos',256,3,'AUT003'),('LIB004','Don Quijote de la Mancha',992,4,'AUT004'),('LIB005','La casa de los espíritus',367,5,'AUT001');
/*!40000 ALTER TABLE `libros` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `prestamos`
--

DROP TABLE IF EXISTS `prestamos`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `prestamos` (
  `id_prestamo` int NOT NULL AUTO_INCREMENT,
  `id_socio` varchar(9) NOT NULL,
  `id_libro` varchar(13) NOT NULL,
  `fecha_prestamo` date NOT NULL,
  `fecha_devolucion` date NOT NULL,
  `fecha_dev_real` date DEFAULT NULL,
  PRIMARY KEY (`id_prestamo`),
  KEY `id_socio` (`id_socio`),
  KEY `id_libro` (`id_libro`),
  CONSTRAINT `prestamos_ibfk_1` FOREIGN KEY (`id_socio`) REFERENCES `socios` (`id_socio`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `prestamos_ibfk_2` FOREIGN KEY (`id_libro`) REFERENCES `libros` (`id_libro`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `prestamos`
--

LOCK TABLES `prestamos` WRITE;
/*!40000 ALTER TABLE `prestamos` DISABLE KEYS */;
INSERT INTO `prestamos` VALUES (1,'SOC001','LIB001','2026-01-01','2026-01-15','2026-01-14'),(2,'SOC002','LIB002','2026-01-05','2026-01-20',NULL),(3,'SOC003','LIB003','2026-01-10','2026-01-25','2026-01-26'),(4,'SOC004','LIB004','2026-01-08','2026-01-22','2026-01-21'),(5,'SOC005','LIB005','2026-01-12','2026-01-27',NULL);
/*!40000 ALTER TABLE `prestamos` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `socios`
--

DROP TABLE IF EXISTS `socios`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `socios` (
  `id_socio` varchar(9) NOT NULL,
  `nombre` varchar(20) NOT NULL,
  `apellido1` varchar(20) NOT NULL,
  `apellido2` varchar(20) DEFAULT NULL,
  `email` varchar(25) NOT NULL,
  `telefono` varchar(9) DEFAULT NULL,
  `Direccion` text,
  PRIMARY KEY (`id_socio`),
  UNIQUE KEY `email` (`email`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `socios`
--

LOCK TABLES `socios` WRITE;
/*!40000 ALTER TABLE `socios` DISABLE KEYS */;
INSERT INTO `socios` VALUES ('SOC001','Juan','Pérez','García','juan.perez@email.com','612345678','Calle Mayor 1, Madrid'),('SOC002','María','López',NULL,'maria.lopez@email.com','623456789','Avenida Principal 20, Madrid'),('SOC003','Carlos','García','Martín','carlos.garcia@email.com','634567890','Plaza del Sol 5, Madrid'),('SOC004','Ana','Martínez',NULL,'ana.martinez@email.com','645678901','Calle Luna 10, Madrid'),('SOC005','Pedro','Rodríguez','Sánchez','pedro.rodriguez@email.com','656789012','Paseo Castellana 30, Madrid');
/*!40000 ALTER TABLE `socios` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2026-01-11 22:57:40
```

### Ejercicio 1
Ranking de los libros más prestados
Se debera obtener el titulo del libro, el nombre, apellido1 y apellido2 del autor, asi como las veces que ha sido prestado.En primer lugar debe aparecer el libro que más veces ha sido prestado.
```SQL title:Ejercicio_1
SELECT l.titulo, COUNT(p.id_libro) veces_prestado, a.nombre, a.apellido1, a.apellido2
FROM libros l
JOIN prestamos p ON l.id_libro = p.id_libro
JOIN autores a ON a.id_autor = l.id_autor
GROUP BY l.titulo
ORDER BY veces_prestado DESC;
```

### Ejercicio 2
Obtener los socios que han tenido más de dos multas, es decir que han devuelto el libor mas tarde de la fecha de devolución (2 puntos)

Se deberá obtener todos los datos de los socios que han obtenido más de dos multas junto con el número de multas que ha tenido.
```SQL title:Ejercicio2
SELECT s.*, COUNT(*) num_multas
FROM socios s
JOIN prestamos p on s.id_socio = p.id_socio
WHERE p.fecha_dev_real > p.fecha_devolucion
GROUP BY s.id_socio
HAVING COUNT(*) >2;
```




