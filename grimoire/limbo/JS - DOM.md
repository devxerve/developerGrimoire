---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :dev_javascript_plain: Dom - Modelo De Objetos Del Documento
Estructura de un documento HTML o XML como un árbol de nodos en memoria.
Permite que JavaScript acceda, modifique, añada o elimine elementos, contenido y estilos de la página web de forma dinámica
El navegador crea este árbol automáticamente al cargar la página, convirtiendo cada etiqueta HTML en un objeto accesible mediante métodos como `getElementById()` o `querySelector()`.
## Estructura Básica
El DOM organiza el documento en una jerarquía:
- **Nodo raíz**: El objeto `document`.
- **Elementos**: Etiquetas HTML como `<h1>`, `<p>`, `<div>`.
- **Texto**: Contenido dentro de las etiquetas.
- **Atributos**: Propiedades como `id`, `class`, `style`.

# Ejemplo
![[JavaScript - Básicos#Inserción]]

```
document (raíz)
└── #document
    └── html (lang="es")
        ├── head
        │   ├── meta (charset="UTF-8")
        │   └── title → "Ejercicio1"
        └── body
            └── main
                ├── h1 → "Titulo principal"
                ├── section
                │   ├── h2 → "Titulo 2"
                │   └── p (id="para", style="color: blue;")
                │       └── Text: "Ejemplos varios de Javascript"
                └── script (type="text/Javascript")
                    └── Text: alert("Hola Mundo"); console.log("Para depurar...");

```





