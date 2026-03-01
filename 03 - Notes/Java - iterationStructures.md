---
cssclasses:
  - centerTitles
  - " centerImages "
  - " roundedImages"
tags:
  - java
---

# :dev_java_original:Estructuras De iteración

## While
La iteración continuara hasta que la condición sea falsa
#### ==Forma==
```java cpp title:Estructura_while
while(Expresión booleana){ //Si se cumple la condicion se ejecuta el bloque, si no se cumple se omite
	instruccion1;
	instruccion2;
};
```

#### ==Ejemplo==
```java cpp title:Ejemplo_while_1
int x = 0;
while(x<10){
		System.out.println(x);
	x++;
}
```
![[Programación - 3 - Ejemplos -while.jpg]]

### Do-while
Igual que el while, pero te aseguras que las instrucciones al menos se ejecutan una vez.
#### ==Forma==
```java cpp title:Do-While
int x = 0;
do{ //Bloque de instruccion que se ejecutara al menos 1 vez 
	instruccion 1;
	instruccion 2;
}while(Expresion Booleana) // Se comprueba la condicíon y si esta se cumple se repite el Do-while, si no se cumple se sale del bloque.
```
#### ==Ejemplos==
```java cpp title:Ejemplo_Do-while
int x = 0;
do{
	System.out.println(x);
	x++;
}
while(x>100);
```
![[Programación - 3 - Ejemplos - do-while.jpg]]
### For
Permite la ejecución del mismo código un número de veces
```java cpp title:For
for (inicialización;condición;actualización){
	System.out.println("Esto es un bloque for");
}
```

```java cpp title:Ejemplo_For
package ejemplo_for

	public class For_java_main{
	
		System.out.println("Incremento");
		for(int x = 0; x < 10; x++){ //se declara la variable a 0 siempre, se mira la condición (x <10) y despúes se incrementa en 1 el valor de x
			System.out.println("Se ha incrementado x en 1" + x);
		}
		
		System.out.println("Decremento");
		for (int x =10; x> 0; x--){ // se declara la variable a 10, se mira la condicion x>0, se decrementa el valor de x
			System.out.println("Se ha decrementado x en 1" + x);
		}	
}
```
#### :dev_java_original:For Anidados
Se ejecuta el primer for, luego se ejecuta el segundo, y cuando este finaliza, se vuelve al primero y así se repite el ciclo. 
```java cpp title:For_anidados
package ejemplo_for_anidados;
	public class Ejemplo {
		public static void main(String[] args) {
			for (int x = 0; x < 3; x++) {
				for (int y = 0; y < 3; y++) {
					System.out.println(x + "" + "" + y); // esto printeara 00 01 02 10 11 12 20 21 22 (Se ejecutan 3 y por cada x)
				}
			}
	}
}
```
