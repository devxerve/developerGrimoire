---
título: OOP — Conceptos básicos en Java
lenguaje: Java
categoría: POO
fecha: 2025-01-01
tags:
  - java
  - poo
  - apunte
estado: borrador
---

# Java — OOP Basics

## Resumen
> Los cuatro pilares de la POO y cómo se implementan en Java.

## Concepto

### ¿Qué es la POO?
La Programación Orientada a Objetos organiza el código en torno a **objetos** que combinan datos (atributos) y comportamiento (métodos).

### Los 4 pilares
| Pilar | Descripción |
|---|---|
| **Encapsulación** | Ocultar los detalles internos, exponer solo lo necesario |
| **Herencia** | Una clase hereda atributos y métodos de otra |
| **Polimorfismo** | Un mismo método se comporta distinto según el objeto |
| **Abstracción** | Modelar solo lo relevante del mundo real |

## Ejemplos
```java
public class Animal {
    private String nombre; // encapsulación

    public Animal(String nombre) {
        this.nombre = nombre;
    }

    public void hacerSonido() { // sobreescribir = polimorfismo
        System.out.println("...");
    }
}

public class Perro extends Animal { // herencia
    public Perro(String nombre) {
        super(nombre);
    }

    @Override
    public void hacerSonido() {
        System.out.println("Guau");
    }
}
```

## Ver también
- [[Notes/Java - Collections|Colecciones en Java]]
- [[Concepts/OOP|Concepto general de POO]]

## Referencias
- 
