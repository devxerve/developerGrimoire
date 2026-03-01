---
cssclasses:
  - center-titles
  - center-images
  - rounded-images
  - page-grid
  - pen-red
---

# :dev_java_original::luc_box:Programación Modular
La programación modular es una de las reglas de oro de la programación moderna, se basa en que pequeños trozos del código se abstraen para usarlos en diferentes contextos, en java los trozos se llaman **métodos** y el mismo método se puede usar en diferentes clases.

La sintaxis básica de un método es la siguiente

```java cpp title:Metodos_java
public tipo nombre([parametros]){ // LOS METODOS SIEMPRE EN MINUSCULA LA PRIMERA
	operaciones;
	[return]; // TODOS TIENEN RETURN SALVO LOS DEL TIPO VOID 
}
```

## Tipos De Métodos (Más Usados, la Sintaxis Es Similar Para todos)
### Método Tipo Int
Este método devuelve un dato de tipo Int (número entero)
```java cpp title:Metodo_Int
public static int sumar([int a, int b}){
	int output = 0;
	output = a+b;
	return output; // Retorna el dato tipo Int
}
```
### Método Tipo Float
Este método devuelve un dato de tipo Float (decimal simple)
```Java cpp title:Metodo_float
public static float dividir([float a, float b]){
    float output = 0.0f;
    output = a / b;
    return output;
}
```

### Método Tipo Double
Este método devuelve un dato de tipo Double (decimal con más precisión).
```java cpp title:Metodo_double
public static double redondear([double numero]){
    double output = 0.0;
    output = Math.round(numero * 100.0) / 100.0;
    return output;
}
```
### Método Tipo String
Este método devuelve un dato de tipo String (cadena de texto).
```java cpp title:Metodo_String
public static String concatenar([String a, String b]){
    String output = "";
    output = a + b;
    return output;
}
```

### Método Tipo Void
Este método no devuelve nada (solo ejecuta acciones).
```java cpp title:Metodo_void
public static void imprimir([String mensaje]){
    System.out.println(mensaje);
    // No hay return
}
```

### Método Tipo Array[] (ejemplo Con int)
Este método devuelve un dato de tipo Array.
```java cpp title:Metodo_Array
public static int[] crearArray([int tam]){
    int[] output = new int[tam];
    return output;
}
```

### Método Tipo Objeto
Este método devuelve un dato de tipo [[Introduccion a objetos Java|Objeto.]]
```java cpp title:Metodo_Objeto
public static Persona crearPersona([String nombre]){
    Persona output = new Persona(nombre);
    return output;
}
```


