---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :rif_test_tube:Pruebas Del Código - Estrategias
Espiral en este orden:
## 1. Pruebas Unitarias:
Casos de prueba para cada unidad programada.
## 2. Pruebas De Integración:
Se observa como los distintos módulos ya probados en el paso 1 interaccionan entre sí.
2 tipos:
> [!summary] Pruebas
> 1. Incrementales: Se van añadiendo módulos progresivamente.
> 2. No Incrementales: Todo a la vez (no recomendable)

## 3. Pruebas De Validación:
Realizadas por el cliente, 2 tipos:
> [!summary] Pruebas
> 1. Alfa: Se realizan en presencia del desarrollador, que anota los fallos.
> 2. Beta: El cliente prueba solo el software, anota los fallos y pasa el informe al desarrollador.

## 4. Pruebas De Sistema:
Consta de 3 pruebas
> [!summary] Pruebas
> 1. Recuperación: Se observa como se recupera el software despues de un fallo (forzado)
> 2. Seguridad: Se verifica que no se pueda acceder ilegalmente.
> 3. Stress o Resistencia: Se prueba como se comporta el software ante situaciones de alta carga de recursos
