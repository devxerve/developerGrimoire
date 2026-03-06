---
cssclasses: pageGrid
tags:
  - java
---

# :dev_java_original: Arrays
Son listas de datos que están almacenados consecutivamente en memoria 
HAY 3 tipos
- Unidimensionales: Listas o vectors
- Multidimensionales:
	- Tabla: 2 dimensions
	- Cubo: 3 dimensions 

## Arrays unidimensionales
Se declaran e inicializan así

```java cpp title:Arrays_Unidimensionales
int[] lista = new int [10]; // int [posicion] declara el tipo, le sigue el nombre = la capacidad (tiene 10 elementos int (0-9))
```

Para pasar valores a un array se have de la siguiente manera

```java cpp title:Paso_de_valores
lista[0] = 100; //en la posicion 0 se mete el número 100
```

Para recuperar valores se llama al array y a la posición del valor que se quiere recuperar, en este caso:

```java cpp title:Recuperar_valores
lista[0] = 100; //asignamos el valor
System.out.println(lista[0]); // Printea 100
int x = lista [0]; //Asignamos x al valor almacenado en la posicion 0 del array. 
```

## Ejemplo de array (simple)
```java cpp title:Ejemplo_array
package ejemplo_arrays;
	public class Arrays_simples {
	final static int INI_INT = 0;
	public static void main(String[] args) {
		int inicial = INI_INT;
		int[] lista = new int [10];
	
		for (int i = INI_INT; i < lista.length; i++) {
			inicial = inicial + 100;
			lista[i] = inicial;	
		}

		for (int i = 0; i < lista.length; i++) {
			System.out.println(lista[i]);
		}
	}
}
```





