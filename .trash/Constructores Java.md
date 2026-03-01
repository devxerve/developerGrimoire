---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# :dev_java_original:🚧Constructores
Los constructores en Java son métodos especiales que inicializan objetos al crearlos con **new** 
Siempre tienen el mismo nombre que la clase y no devuelven valor.
## Características Principales
- <mark style="background: #FF5582A6;">Pueden tener instrucciones</mark>
- Se llaman automáticamente con **new**.
- Sin constructor, Java crea uno por defecto sin parámetros.
- Pueden tener parámetros y sobrecargarse (varios constructores).

## Tipos De Constructores
```java cpp title:Tipos_Constructores
class Persona {     
	Persona() {} // Sin parámetros (por defecto)    
	Persona(String nombre){} // Con parámetros
	Persona(String nombre, int edad){}    // Sobrecarga
}
```

## Sobrecarga de constructores 
(Constructores con mismo nombre, diferentes parámetros, ya sea en número, tipo, nombre u orden)




