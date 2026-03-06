---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
tags:
  - java
---

# :dev_java_original:🔒Modificadores De acceso Java
Los modificadores de acceso en Java controlan la visibilidad de atributos y métodos en clases. Existen cuatro niveles principales: public, protected, default (sin especificar) y private.

- **public**: Accessible desde cualquier clase, en cualquier paquete.
- **protected**: Accessible dentro del mismo paquete y por subclases (incluso en otros paquetes).
- **default** (sin modificador): Solo accessible dentro del mismo paquete.​
- **private**: Solo accessible dentro de la misma clase.

```java cpp title:Modificadores_Acceso
class Persona {
    public String nombre;      // Accesible desde cualquier lugar
    protected int edad;        // Paquete + subclases
    String ciudad;             // Solo mismo paquete (default)
    private double salario;    // Solo dentro de Persona
}
```
