---
cssclasses:
  - center-titles
  - pen-red
  - page-grid
---

# :dev_java_original:For Anidados
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
# References
Clases de JAVA
Estructuras de Selección
Estructuras de Iteración
For anidados
Estructuras Control Java.pdf
## Ejemplos
Ejemplos Programación Estructuras de iteración
Ejemplos estructuras de Selección
Clases de JAVA
## Ejercicios / Trabajos / Prácticas
Programación Tarea 4 - Estructuras de control
Programación Tarea 5 - Estructuras de control