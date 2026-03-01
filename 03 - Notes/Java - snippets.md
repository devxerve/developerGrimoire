---
date: 2026-02-11T10:26
cssclasses:
  - center-titles
  - center-images
  - rounded-images
  - page-grid
  - pen-red
---

# :dev_java_original::luc_layout_template: Snippets java
# setCharset()
## <mark style="background: #FF5582A6;">Incluir Caracteres (UTF-8) en system out</mark>

```java title="setCharset()"
private static void setCharset() {
	try {
		System.setOut(new PrintStream(System.out, true, StandardCharsets.UTF_8.name()));
	} catch (UnsupportedEncodingException e) {
		e.printStackTrace();
	}
}
```

# leerInt()
## <mark style="background: #FF5582A6;">Control De número entero </mark>

```java title="LeerInt()"
public static int leerInt(Scanner entrada) {
	int output;
	boolean salir = false;
	output = INI_INT;
				
	do {
		try {
			output = entrada.nextInt();
			salir = true;
		} catch (InputMismatchException ex) {
			System.out.println("Entrada invalida, se esperaba un número entero");
			entrada.next();
		}
	} while (!salir);
	return output;
			
```

# leerFloat()
## <mark style="background: #FF5582A6;">Control De número float </mark>

```java title="leerFloat()"
public static float leerFloat(Scanner entrada) {
	float output;
	boolean salir = false;
	output = INI_FLOAT;
	do {
		try {
			output = entrada.nextFloat();
			salir = true;
		} catch (InputMismatchException ex) {
			System.out.println("Entrada invalida, se esperaba un número decimal");
			entrada.next();
		}
	} while (!salir);
	return output;
}
```

# generarNum()
## <mark style="background: #FF5582A6;">Generar Números en un rango</mark>

```java title="generarNum()" group=genNum
public static int generarNum(int max, int min) {
	int output;
	output = (int) (Math.random() * (max - min + 1) + min);
	return output;
}
```
```java title="Float generarNum()" group=genNum
public static float generarNum(int max, int min) {
	float output;
	output = (int) (Math.random() * (max - min + 1) + min);
	return output;
}
```
