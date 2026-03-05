---
cssclasses:
  - "centerTitles "
  - " roundedImages"
  - " centerImages"
tags:
  - java
---


# :dev_java_original:Herencia - Java
La herencia ocurre cuando una clase es un derivado de otra, compartiendo atributos pero también teniendo los suyos propios.

> [!summary] 
> Permiten definir de una clase otras clases relacionadas que compartan ciertas caracteristicas.
> 
> Las clases derivadas heredan atributos y métodos de la clase base o padre.
> 
> Sirve para crear jerarquias de clases y relaciones entre clases.

<mark style="background: #FF5582A6;">SI SE QUIERE REFERENCIAR A UN ATRIBUTO QUE ESTA SOLO DEFINIDO EN LA CLASE PADRE SE DEBE USAR LA PALABRA RESERVADA super</mark>


![[inheritance.png]]

```java title="Herencia"
public class Animal {
    protected String nombre;
    
    public Animal(String nombre) {
        this.nombre = nombre;
    }
    
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
}

public class Perro extends Animal {
    private String raza;
    
    public Perro(String nombre, String raza) {
        super(nombre);  // Constructor padre
        this.raza = raza;
    }
    
    public void hacerSonido() {
        System.out.println(nombre + " dice: GUAU!");
    }
}

// Uso correcto
Perro milu = new Perro("Milu", "Border Collie");
milu.hacerSonido();  // Milu dice: GUAU!
```

---

# :dev_java_original:Polimorfismo - Java
El polimorfismo se parece mucho a la herencia, permite que objetos de distintas clases respondan al mismo mensaje de formas distintas.

## Tipos
### Sobrecarga (Compile-time)
> [!info] Sobrecarga (Compile-time)
> Metodos con el mismo nombre pero diferentes parámetros dentro de la misma clase, Java elige los parámetros según lo que pongamos nosotros, similar a [[java - constructors#Sobrecarga de constructores|la sobrecarga de constructores]]
> 

```java title="Polimorfismo Compile-time" group="polimorfismo"
public class Animal {
    (atributos);
    public void hacerSonido(){ // Método por defecto
	    System.out.println("GRRR");
    }
    
    public void hacerSonido(perro perro){ // Método si se llama con perro como argumento
	    System.out.println("GUAU");
    }
}
```
```java title="Polimorfismo Runtime" group="polimorfismo"
public class Animal {
    (atributos);
    public void hacerSonido(){ // Método por defecto
	    System.out.println("GRRR");
    }
}
public class Perro extends Animal{
	@Override   // Asi se llama a la sobreescritura
    public void hacerSonido(){ 
	    System.out.println("GUAU");
    }
}
```
### Sobreescritura (Runtime)

> [!info] Sobreescritura (Runtime)
> Clase hija reescribe el método de la superclase ([[java - inheritance_polimorphism#Herencia|Herencia]]) con la anotación @Override
> Se ejecuta la versión correcta según el objeto que la llama
> En el ejemplo de arriba si lo ejecuta Animal se mostrara GRRR, si lo ejecuta Perro se mostrara GUAU

![[polymorphism.png]]






