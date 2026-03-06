---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_java_plain::rif_test_tube: Junit
JUnit es un framework para automatizar pruebas unitarias, funciona mediante anotaciones (Se hacen con la @)

## Anotaciones junit 5

### @Test
Marca un método de prueba
```Java cpp title:JUnit_Test
@Test
void testSuma(){
assertEquals(8,calculadora.add(5,3)); //AssertEquals es un metodo que compara un valor que nosotros decidimos con el valor resultante de una instruccion (como otro metodo)
} 
```

### @Before/AfterEach
Marcan instrucciones para la prueba, pueden set instrucciones anteriores a cada Test (BeforeEach) o posteriores a cada Test(AfterEach)

```java cpp title:JUnit_Before/AfterEach
int contador = 0;
@BeforeEach
void before(){
contador++;
System.out.println("Inicio del test" + contador+1);
calculadora = new Calculadora();
}
@After
void after(){
System.out.println("Fin del test" + contador+1);
}
```

## Directivas junit 5
### @Before/After All
Marcan instrucciones para la prueba, pueden set instrucciones anteriores (BeforeAll) o posteriores (After all) a todos los test (en conjunto)

```java cpp title:Before/AfterAll
@BeforeAll
void start{
System.out.println("Empiezan las pruebas Unitarias con JUnit5")
}

@AfterAll
void finish{
System.out.println("Acaban las pruebas Unitarias con JUnit5")
}
```

## Aserciones más comunes en junit 5
### assertEquals(valor Esperado, valor recibido)
Se compara el esperado con el recibido
```java cpp title:assertEquals()
assertEquals(8, 5 + 3); // Pasa (true)
assertEquals("Hola", "Hola"); // Pasa
```

### assertNotEquals(valor Esperado, valor recibido)
Se verifica que el valor esperado NO sea igual al recibido.
```java cpp title:assertNotEquals
assertNotEquals(5, 3 + 3); // Pasa (false esperado)
assertNotEquals("Hola", "Adios"); // Pasa
```
### assertTrue(Condición)
Verifica que la condición sea verdadera.
```java cpp title:assertTrue
assertTrue(5 > 3); // Pasa
assertTrue(numero % 2 == 0); // Pasa si numero es par
```
### assertFalse(Condición)
Verifica que la condición sea falsa.
```java cpp title:assertFalse()
assertFalse(5 < 3); // Pasa
assertFalse(numero % 2 == 0); // Pasa si numero es impar
```
### assertNull(valor)
Comprueba que el valor sea null.
```java cpp title:assertNull()
assertNull(resultado); // Pasa si es null
```
### assertNotNull(valor)
```java cpp title:assertNotNull()
assertNull(resultado); // Pasa si no es null
```
### assertThrows(Exception.class, ejecutable)
Verifica que se lance una excepción específica al ejecutar código.
```java cpp title:assertThrows
assertThrows(InputMismatchException.class, () -> {     Scanner scanner = new Scanner("abc");  // Input no numérico
scanner.nextInt(); // Lanza InputMismatchException });`
```

