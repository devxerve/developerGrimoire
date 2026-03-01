---
título: Colecciones en Java
lenguaje: Java
categoría: Estructuras de datos
fecha: 2025-01-01
tags:
  - java
  - colecciones
estado: borrador
---

# Java — Collections

## Resumen
> El framework de colecciones de Java para almacenar y gestionar grupos de objetos.

## Concepto

### Tipos principales
| Colección | Descripción | Duplicados | Ordenado |
|---|---|---|---|
| `ArrayList` | Lista dinámica | ✅ | Por índice |
| `LinkedList` | Lista enlazada | ✅ | Por índice |
| `HashSet` | Conjunto hash | ❌ | No |
| `TreeSet` | Conjunto árbol | ❌ | Sí |
| `HashMap` | Mapa clave-valor | ❌ claves | No |
| `TreeMap` | Mapa ordenado | ❌ claves | Sí |

## Ejemplos
```java
import java.util.*;

// ArrayList
List<String> lista = new ArrayList<>();
lista.add("uno");
lista.add("dos");

// HashMap
Map<String, Integer> mapa = new HashMap<>();
mapa.put("edad", 20);
mapa.get("edad"); // → 20

// Iterar
for (String item : lista) {
    System.out.println(item);
}
```

## Ver también
- [[Notes/Java - OOP Basics|OOP en Java]]

## Referencias
- 
