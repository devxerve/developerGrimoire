---
cssclasses: pageGrid
tags:
  - java
---

# :dev_java_original:Introduccion A objetos
## Clases
En Java el código fuente se divide en clases, cada clase tiene sus [[java - methods|Métodos y atributos específicos]], así como su [[java - constructors|Constructor o Constructores.]]
```java cpp title:Ejemplo_clase
public class Animal {
    protected String nombre;
    Animal(String nombre) {
        this.nombre = nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
}
```
## Objetos
Un objeto en java es una instancia de una clase, con sus atributos (Cada uno con su [[java - accesModifiers|tipo]]) y métodos definidos en la clase. Los objetos se crean mediante constructores.
> [!Tip] Consejo
> Podemos imaginar que una clase es un molde de galletas, y un objeto es cada una de las galletas que podemos formar con ese molde, con características casi idénticas entre sí, pero son galletas distintas.
<div class="page-break" style="page-break-before: always;"></div>

### Ejemplo de un objeto (Creación y llamada)
## Constructor
```java cpp title:Ejemplo_objeto_Constructor
class Persona {
	public void saludo() { 
		System.out.println("Hola " + nombre);
	}
	Persona(String nombre); // Constructor que indica que solo necesitas un String nombre para crear un objeto Persona
};
```

```java cpp title:Ejemplo_objeto_Creación y llamada
Persona p = new Persona("Ana");
Ana.saludo(); // Imprimira Hola Ana
```


