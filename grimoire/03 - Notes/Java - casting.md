---
date: 2026-02-28T14:20
cssclasses:
  - centerTitles
  - " centerImages "
  - " roundedImages"
tags:
  - java
---

# :dev_java_original:Casting
 
El casting es el proceso de convertir de un tipo de dato a otro
2 tipos
## Casting implícito
Conversión automática, ocurre cuando java convierte automáticamente, sin que el programador tenga que hacerlo de manera explicita.
```java cpp title:Casting_implicito
int n = 42;
long m = n; //Conversión implícita de int a long
```

## Casting explícito
Manual, ocurre cuando el programador indica explícitamente que se debe realizar la conversión. Necesario cuando se convierte de un tipo de dato más grande a otro más pequeño, para evitar perdida de datos.
```java cpp title:Casting_explicito
double n = 42.7;
int m = (int) n; //Conversion explicita de double a int, se carga la parte decimal y el valor sera 42 
```

