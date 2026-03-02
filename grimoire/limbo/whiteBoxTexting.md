---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :rif_test_tube:Pruebas Unitarias - Caja Blanca
Van ligadas al procedimiento en sí.
Se centran en el funcionamiento interno del programa, se las conoce también como pruebas estructurales.
### <mark style="background: #FF5582A6;">IMPORTANTE</mark>
- Se garantiza que se ejecutan al menos una vez todos los caminos independientes de cada módulo.
- Todas las sentencias se ejecutan al menos una vez.
- Ejecutan todas las decisiones lógicas en TRUE y FALSE.
- Ejecutan todos los bucles en sus límites.
- Utilizan todas las estructuras de datos internas.
---
## Forma De Hacer Las Pruebas
### Asignación De Pasos
Lo primero es asignar un número a cada instrucción del código
![[Tarea 3 - Ejercicio Realización Pruebas#Ejercicio 1#Código]]

### Construcción Del Grafo
Después esos números se pasan a un grafo, donde se representa el flujo de instrucciones, así podremos determinar todos los caminos posibles mediante este mismo grafo, además haremos una tabla con los caminos, los valores de entrada y el resultado esperado.
![[Tarea 3 - Ejercicio Realización Pruebas#Ejercicio 1#Grafo]]

### Complejidad Ciclomatica
La complejidad ciclomatica determina cuantos caminos se deben probar para haber completado todos los escenarios y que todo esté probado, se calcula de la siguiente manera (ver ejemplo)

![[Tarea 3 - Ejercicio Realización Pruebas#Ejercicio 1#Calculo complejidad ciclomática]]

> [!info] Nodos predicados
> Los nodos predicados son aquellos nodos de los que salen 2 o más caminos (o aristas)


