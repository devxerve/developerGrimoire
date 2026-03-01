---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# Fases Del Desarrollo De Software
### Fase 1: Análisis De Requisitos
- Objetivos: <mark style="background: #FFF3A3A6;">Identificar y documentar los requisitos del sistema</mark>
- Actividades:
	- Reunión con el cliente para comprender necesidades
	- Documentación de los requisitos funcionales y no funcionales
	- Creación de un documento de especificación de requisitos.
- Entregables: <mark style="background: #FFF3A3A6;">Documento de especificación de Requisitos</mark>
### Fase 2: Diseño
- Objetivos : Diseñar la arquitectura y la estructura del sistema.
- Actividades:
	- Diseño de Arquitectura de software
	- Diseño UI
	- Diseño BBDD
	- Creación Documentación Técnica
- Entregables: <mark style="background: #D2B3FFA6;">Documentación Técnica</mark>
#### Diseño De la Arquitectura De Software
#### Diseño De la Ui
Se describe la interfaz de usuario completa mediante bocetos
<mark style="background: #D2B3FFA6;"><b style="color:black">USABILIDAD</b></mark> : Facilidad con la que los usuarios pueden interactuar y lograr sus objetivos a través de la UI de un producto digital. 
#### Diseño De la Bbdd
Se diseña el Modelo Entidad-Relación (MER) y el [[Traducción Modelo Entidad-Relación a Modelo Relacional|Modelo Relacional]] de la base de datos del Software

<mark style="background: #FFF3A3A6;">TODO ESTO SE DETALLA EN LA DOCUMENTACION TECNICA </mark>

### Fase 3: Implementación
#### Codificación Del Sistema
**Entornos de desarrollo:** Se preparan los distintos entornos de trabajo, teniendo en cuenta que a lo largo del ciclo de desarrollo para cualquier aplicación informática, se requieren entornos de trabajo para cada etapa. 

Los equipos comienzan con la codificación de cada uno de los components por separado, teniendo en cuenta los requisitos funcionales y el diseño de cada uno de los components.

En este periodo de [[#Codificación del sistema|Codificación]] los desarrolladores utilizan **Entornos de trabajo de desarrollo**, donde se programa el software, puede ir desde un ordenador hasta un servidor compartido por los desarrolladores.
##### Control De Versiones
Esta herramienta permite el desarrollo colaborativo, lo que permite que muchos programadores trabajen de manera simultánea en el mismo proyecto. 
#### Pruebas Unitarias
Se establecen **Casos de prueba** de cada componente del sistema, son pruebas que realiza el programador sobre el código que está implementando.

Se puede preparar un <u>Plan de pruebas unitarias</u> para que, cada vez que se añade una funcionalidad al código, se vuelvan a pasar todas las pruebas de nuevo.

Hay herramientas automáticas para realizar las pruebas --> JUnit en java mediante Eclipse.

##### Integración De Components Y Pruebas De Integración.
**Integración:** Se prueba como interaccionan los distintos módulos probados en las pruebas unitarias. Podrán set incrementales, o no incrementales.
Las incrementales van añadiendo módulos progresivamente, y las no incrementales todo a la vez (no recomendable).
##### Entorno De Integración
Ha de set diferente del entorno de desarrollo pero ya muy parecido al entorno final de producción o pre-producción (donde haremos la siguiente fase de validación y de sistemas).
##### Entregables : Código Fuente Del Sistema.
El entregable final es el sistema ya instalado en un entorno final en el que se podrán realizar las pruebas de la siguiente fase. Aún no es la versión definitiva, ya que hay que realizar la [[#Fase 4 Pruebas|Fase de Pruebas]]. 
El código debe estar instalado en un entorno muy similar al de producción (Se llama entorno de pre-producción).

### Fase 4: Pruebas
##### Objetivos
Probar el sistema completo para verificar que cumple con los requisitos 
##### Actividades
<mark style="background: #FFF3A3A6;">Pruebas de sistema para evaluar el funcionamiento general</mark>
Suele constar de varias pruebas del siguiente tipo: 
- **Recuperación**: Se fuerza el fallo de software y se comprueba la recuperación
- **Seguridad**: Se verifica que el sistema esta protegido contra accesos ilegales.
- **Resistencia** o Stress: Se enfrenta al sistema con situaciones que demandan gran cantidad de recursos.
<mark style="background: #FFF3A3A6;">Pruebas de aceptacion con el cliente</mark>
Consta de pruebas realizadas por el cliente, hay 2 tipos:
**Pruebas alfa:** las pruebas se hacen en presencia del desarrollador, quien tomara nota de los fallos.
**Pruebas beta:** El cliente prueba solo, anota los fallos y manda un informe al desarrollador. 
<mark style="background: #FFF3A3A6;">Corrección de errores y ajustes según sea necesario.</mark>
##### Entregables: Informe De Pruebas.
Informe que verifica que las pruebas se han realizado, los errores resueltos y que el cliente está conforme con el funcionamiento del sistema: es decir, have lo que estaba en el contrato. 
#### Fase 5: Mantenimiento
##### Objetivos:
Mantener y mejorar el sistema despúes de su implementación. 
##### Actividades
**Corrección de errores**
**Implementación de mejoras y actualizaciones**
**Soporte tecnico continuo**
##### Entregables
<mark style="background: #FFF3A3A6;">Versiones actualizadas del software</mark> 
> [!Info] Importante
> Es importante tener una comprensión sólida de los requisitos desde el principio, ya que cualquier cambio después del análisis puede resultar en retrasos y costos adicionales.

