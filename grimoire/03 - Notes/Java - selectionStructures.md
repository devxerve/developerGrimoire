---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
tags:
  - java
---


# :dev_java_original::luc_box_select:Estructuras De selección


# Definición
Son declaraciones que nos permiten seleccionar y ejecutar bloques específicos del código mientras otras partes son ignoradas.
## If
Comprueba una condición y ejecuta algo si esta se cumple
Si solo hay una instrucción no se have falta poner llaves (no pasa nada por ponerlas)
```java
if (llueve == true)
	System.out.println("Coge el chubasquero");
```
# If else
Comprueba una condición y ejecuta algo si esta se cumple, si no lo have ejecuta las instrucciones dentro del bloque else
```java
if (llueve == true){
	System.out.println("Coge el chubasquero");
}else{
	System.out.println("No hace falta chubasquero");
}
```
# If else if
Comprueba una condición, ejecuta algo si esta se cumple, si no se cumple ejecuta un bloque else, que tiene dentro un bloque if, que ejecutara algo si la condicion del segundo bloque se cumple
==SON CONDICIONES ANIDADAS==
```java
if(llueve == true){
	System.out.println("Coge el chubasquero");
	}else if(frio == true){
			System.out.println("Coge la chaqueta");
	}
```

## Switch

Funciona en base a una variable y su valor.
<mark style="background: #FFF3A3A6;">IMPORTANTE: Tiene que haber una sentencia</mark> `default` <mark style="background: #FFF3A3A6;"> dentro del switch, y cada</mark> `case` <mark style="background: #FFF3A3A6;">tiene que tener su</mark> `break`, <mark style="background: #FFF3A3A6;">sino no se ejecutara bien la logica del switch</mark>
```java title="Sintaxis_switch"
int opcion = 0;
opcion = sc.nextInt();

switch(opcion){
	case 1:
		System.out.println("Instrucciones del valor 1 ");
		break;
	case 2:
		System.out.println("Instrucciones del valor 2 ");
		break;
	case 3:
		System.out.println("Instrucciones del valor 3 ");
		break;
	default:
		System.out.println("Instrucciones si ninguno de los otros casos se cumplen")
		break;
}
```
