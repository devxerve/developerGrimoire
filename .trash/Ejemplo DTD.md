---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

```xml cpp title:Ejemplo_DTD
<!-- DTD de ejemplo para una Academia de Formación -->

<!-- 1. DECLARACIÓN DE ENTIDADES -->
<!-- Entidad interna: funciona como una constante de texto [1, 2] -->
<!ENTITY copyright "© 2024 Academia Digital">

<!-- Entidad de parámetro: permite reutilizar grupos de elementos o atributos 
     dentro del propio DTD [3] -->
<!ENTITY % datos_contacto "telefono, email?">

<!-- 2. DEFINICIÓN DE ELEMENTOS -->
<!-- Elemento raíz que contiene otros elementos [4] -->
<!ELEMENT academia (curso+, estudiante*, logo)>

<!-- Elemento con hijos obligatorios y opcionales usando operadores de 
     cardinalidad (?, +, *) [5, 6] -->
<!ELEMENT curso (nombre, descripcion, creditos)>
<!ELEMENT estudiante (nombre, apellidos, (%datos_contacto;))>

<!-- Elementos terminales que contienen solo texto (#PCDATA) [4, 7] -->
<!ELEMENT nombre (#PCDATA)>
<!ELEMENT apellidos (#PCDATA)>
<!ELEMENT descripcion (#PCDATA)>
<!ELEMENT creditos (#PCDATA)>
<!ELEMENT telefono (#PCDATA)>
<!ELEMENT email (#PCDATA)>

<!-- Elemento vacío (EMPTY): no contiene texto ni subelementos [8, 9] -->
<!ELEMENT logo EMPTY>

<!-- 3. DECLARACIÓN DE LISTAS DE ATRIBUTOS (ATTLIST) -->
<!-- Aquí se muestran todos los tipos y modificadores posibles según las fuentes [9-13] -->

<!ATTLIST curso
    /* ID: Identificador único que no puede repetirse en el documento [9, 13] */
    /* #REQUIRED: El atributo es obligatorio [13] */
    id_curso ID #REQUIRED
    
    /* Enumeración: El valor debe ser uno de los de la lista [10, 11] */
    /* #IMPLIED: El atributo es opcional [12, 13] */
    modalidad (presencial | online | hibrida) #IMPLIED
    
    /* CDATA: Cadena de texto simple [11] */
    /* #FIXED: El valor siempre será el indicado, se incluya o no en el XML [13] */
    idioma CDATA #FIXED "Español"
    
    /* Valor por defecto: Si no se especifica, toma este valor literal [14] */
    nivel CDATA "basico"
>

<!ATTLIST estudiante
    /* NMTOKEN: Una sola palabra con caracteres permitidos por XML [11, 12] */
    usuario NMTOKEN #REQUIRED
    
    /* IDREF: Referencia a un ID existente en el documento para crear vínculos [9] */
    curso_inscrito IDREF #REQUIRED
>

<!ATTLIST logo
    /* Atributo CDATA opcional para la ruta de la imagen */
    url CDATA #IMPLIED
>
```

Explicación de los components clave según las fuentes:

 **Tipos de Datos en Atributos:**
	◦ **CDATA:** Se usa para texto general que el procesador no necesita analizar profundamente
	◦ **ID:** Es crítico para la integridad, ya que garantiza que un elemento tenga un nombre único que no empiece por números
	◦ **IDREF:** Permite establecer relaciones entre elementos, como conectar a un estudiante con un curso específico
	◦ **NMTOKEN:** Es más restrictivo que CDATA, pues solo acepta caracteres válidos para nombres (sin espacios)
	◦ **Enumeración:** Limita las opciones del usuario a una lista cerrada definida entre paréntesis y separada por el operador |

• **Modificadores de Atributos:** van con un # delante
	◦ **EQUIRED:** Obliga a que el atributo aparezca siempre en la etiqueta
	◦ **IMPLIED:** Ofrece flexibilidad al permitir que el atributo sea omitido
	◦ **FIXED:** Asegura la consistencia al forzar un valor único inmutable
	◦ **Literal:** Actúa como un valor "de fábrica" si el author del XML no escribe nada
