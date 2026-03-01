---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

Documentos Bien Formados y Válidos

Un documento se considera **bien formado** si cumple estrictamente con todas las reglas sintácticas del estándar XML, como tener un único elemento raíz
Por otro lado, un documento es **válido** si, además de estar bien formado, cumple con la estructura y semántica definidas específicamente en un **DTD o un XML Schema**

Validación: DTD y XML Schema

Existen dos herramientas principales para asegurar que un XML sigue las reglas impuestas:
**DTD:** Es el método más tradicional; define qué elementos y atributos pueden aparecer, pero no soporta tipos de datos complejos ni espacios de nombres
**XML Schema (XSD):** Es la alternativa moderna que, al set un documento XML en sí mismo, permite restricciones mucho más precisas y el uso de **tipos de datos específicos** como números o cadenas de texto

Uso de Entidades

Las **entidades** actúan como constantes que permiten definir valores que se repiten en el documento
El intérprete XML sustituye automáticamente la entidad por su valor definido al procesar el archivo. Existen entidades **internas** para caracteres especiales (como `&lt;` para el signo menor que) y entidades **externas** que permiten vincular contenido de otros archivos mediante una URL.


