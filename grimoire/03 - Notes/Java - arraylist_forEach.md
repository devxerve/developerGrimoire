---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
tags:
  - java
---

# :dev_java_original: Arraylists
Sirven para crear arrays con tamaño dinámico, <mark style="background: #FF5582A6;">estos arrays solo pueden contener objetos</mark>, se deben importar con el siguiente import

```java cpp title:Import_ArrayList
import java.util.ArrayList;
```

## Creación y declaración

```java cpp title:Declaración_ArrayLists
ArrayList<Objeto> nombre = new ArrayList<Objeto>(); //el objeto de la parte derecha es OPCIONAL, funciona igual
```

## Métodos principales de los arraylists
```java cpp title:Metodos_principales_ArrayList
ArrayList<Circulo> circulos = new ArrayList<Circulo>();
Circulo circulo1 = new Circulo(radio); //CREAMOS UN OBJETO CIRCULO 1
Circulo circulo2 = new Circulo(radio); //CREAMOS UN OBJETO CIRCULO 2
circulos.add(circulo1); //AÑADIMOS EL OBJETO circulo1 A LA SIGUIENTE POSICIÓN
circulos.add(circulo2); //AÑADIMOS EL OBJETO circulo2 A LA SIGUIENTE POSICIÓN 
circulos.get(1); //PEDIMOS EL ELEMENTO EN LA PRIMERA POSICION DEL ARRAYLIST
circulos.getLast(); //PEDIMOS EL ULTIMO ELEMENTO (circulo2)
/*PASAMOS EL OBJETO circulo2 a la posicion 1, Y la posicion 2 deja de 
*existir (si intentamos recuperarla salta la excepcion IndexOutofBound)**/
circulos.set(1,circulo2); 
circulos.add(circulo1); //Volvemos a meter el circulo1
//Borra el objeto 1 del array (con su objeto dentro), el objeto 2 pasa a 1
circulos.remove(1);
circulos.size(); //Devuelve el número de elementos 
circulos.clear; //Borra todos los elementos, "Limpia el ArrayList"
circulos.isEmpty; //Devuelve un Boolean, vacio o no 
```

# :dev_java_plain: Foreach

Funciona como un for, pero en vez de iterar sobre el programa como tal o un Array, itera sobre un ArrayList<> o una coleccion, para usar atributos de cada elemento del arrayList o coleccion.

## Sintaxis
```java title="ArrayList<> - ForEach"
// Recorremos el ArrayList con for-each
for (Circulo c : circulos) {
    System.out.println("Radio: " + c.getRadio());
    System.out.println("Área: " + c.getArea());
}
```



