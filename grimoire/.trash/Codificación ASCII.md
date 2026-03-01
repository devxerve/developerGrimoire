---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

## Codificación Ascii

## Proceso De Codificación

1. Convertir cada carácter a su código ASCII (número decimal)

2. Convertir el número decimal a binario (división sucesiva)

3. Utilizar 7 u 8 bits según sea necesario


**Ejemplo**: "María"

- M = 77 = 1001101

- a = 97 = 1100001

- r = 114 = 1110010

- í = 161 = 10100001

- a = 97 = 1100001


## Proceso De Decodificación

1. Dividir la secuencia binaria en bloques de 8 bits

2. Convertir cada bloque a su equivalente decimal

3. Buscar en la tabla ASCII el carácter correspondiente
## Código Ascii Y Unicode

## Código Ascii

- **Definición**: American Standard Code for Information Interchange - Código Standard Norteamericano para Intercambio de Información

- **Función**: Códigos para caracteres alfanuméricos (letras, símbolos, números y acentos)

- **Versión original**: Utilize 7 bits para representar caracteres (máx 127), el octavo bit como bit de paridad para detectar errores

- **ASCII extendido**: Utilize 8 bits para representar 256 caracteres, permite tildes y más símbolos


## Caracteres Ascii

- Caracteres Alfabéticos: Letras mayúsculas (A, B, C...) y minúsculas (a, b, c...)

- Caracteres Numéricos: 0, 1, 2, 5...

- Caracteres Especiales: !, @, (, ñ, ...

- Caracteres de Control: Fin de línea /n

- Caracteres Gráficos: Figuras, components gráficos


## Unicode

Sistema de codificación de caracteres creado para abordar la limitación del estándar ASCII. Permite representar caracteres de idiomas como chino, japonés, árabe, cirílico, hebreo y muchos otros. Se implementa mediante UTF-8, UTF-16 y UTF-32.