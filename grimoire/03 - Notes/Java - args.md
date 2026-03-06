---
cssclasses: pageGrid
tags:
  - java
---

# :dev_java_original: Args
Cuando creamos un main siempre tiene esta estructura

```java title="Main"
public static void main(String[] args){
	(Instrucciones);
}
```

`String[] args` Es un [[java - arrays]] de strings que contiene [[java - args|argumentos]] que se le pasan al main
Estos argumentos pueden ser por ejemplo comandos de la linea de comandos del sistema y podemos trabajar con ellos usando cualquiera de los metodos asociados a los Arrays de Strings

```java title=Ejemplo args"
package ejemplo_args;

public class Principal {
	public static void main(String[] args) {
		if(args.length < 2) {
			System.out.println("[MAIN] Se esperaban mas de 2 argumentos de entrada");
		System.exit(-3);
		}else {
			String nombre = args[0];
			String palabra = args[1];
			System.out.println(palabra + " " + nombre);
			System.out.println("Programa finalizado correctamente");
			System.exit(0);
		}
}
}
```

# Lanzamiento con argumentos
Argumentos : Javi Hola

```batch prompt:cmd title="Ejemplo lanzamiento por comandos" group:bash
cd Exercises\2nd Quarter\ejemplo_args\bin
java ejemplo_args.Principal Javi Hola
```
```shell prompt:bash title="Ejemplo lanzamiento por comandos" group:bash
cd /javi/Exercises/2nd Quarter/ejemplo_args
java -cp bin ejemplo_args.Principal Javi Hola
```

