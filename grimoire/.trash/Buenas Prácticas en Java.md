---
cssclasses:
  - center-titles
  - pen-red
  - page-grid
---

# :dev_java_original::luc_check_circle: Buenas prácticas en java
##  :dev_java_original: 1. Nombres Claros Y Consistentes

Usa nombres descriptivos, siguiendo las convenciones de nomenclatura de Java.

```java title="nombres"
public class GestorDeUsuarios {
    private String nombreUsuario;
    private final int MAX_USUARIOS = 100;
}
```
## :dev_java_original: 2. Mantén Un Código Legible

Usa indentación (4 espacios), líneas cortas y separa bloques lógicamente.

```java title="identacion"
if (saldo > 0) {
    procesarPago();
} else {
    mostrarError();
}
```
## :dev_java_original: 3. Declara Variables Con El Alcance Mínimo Necesario

Declara variables lo más cerca posible de donde se usan.

```java title="Variables_alcance_reducido"
for (int i = 0; i < lista.size(); i++) {
    String elemento = lista.get(i);
    System.out.println(elemento);
}
```
<div class="page-break" style="page-break-before: always;"></div>

## 4. Usa Constantes Y Modificadores Adecuadamente

Declara constantes con final y encapsula los datos.

```java title="Constantes y encapsulación"
public class Banco {
    private static final double TASA_INTERES = 0.05;
    private double saldo;
    public double calcularInteres() {
        return saldo * TASA_INTERES;
    }
}
```

## 5. Manejo Correcto De Excepciones
 
Usa bloques try y captura solo excepciones específicas.

```java title="Bloque try"
try  {
    Scanner.nextInt();
} catch (InputMismatchException ex) {
    System.err.println("Error al leer el dato int ");
}
```

## 6. Documenta Con Javadoc

Documenta la intención del código con @param y @return.

```java title="Documentación javadoc"
/**
 * Calcula el promedio de una lista de enteros.
 * @param numeros Lista de enteros para calcular el promedio.
 * @return Promedio como valor double.
 */
public double calcularPromedio(List<Integer> numeros) {
    int suma = 0;
    for (int n : numeros) {
        suma += n;
    }
    return (double) suma / numeros.size();
}

```
## Variables

## <mark style="background: #FFF3A3A6;">Los Nombres De Las Variables Y Los Métodos Deben Ser Descriptivos Y consistentes</mark>

```java title:MAL
void checkearPar(int num){
boolean temp = false;
	do{
		if (num%2 == 0){
			temp = true;
		}
	}while(!temp)	
}
```
 
```java title:Bien
void checkearPar(int num){
boolean control = false;
	do{
		if (num%2 == 0){
			control = true;
		}
	}while(!control)	
}
```

### <mark style="background: #FFF3A3A6;">LAS Variables Se Inicializan Siempre a Estos Datos En Funcion De Su TIPO</mark>

```java title:variables
int = 0;
float = OF;
double = 0.0;
boolean = false;
char = \u0000;
```

### <mark style="background: #FFF3A3A6;">DECLARAR Las Variables En El Ambito Mas Reducido POSIBLE</mark>

Si vas a usar una variable SOLO en un ámbito (por ejemplo un for) ,  declárala dentro del for

```java title:MAL
int i = 0;
for(i;i<10;i++){
	System.out.println("Esto esta mal");
}
```

```java title:BIEN
for(int i = 0; i<10; i++){
	System.out.println("Esto esta bien");
}
```

### <mark style="background: #FFF3A3A6;">SELECCIONAR Tipo De Dato Adecuado Acorde a la VARIABLE</mark>
