---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---


# Propiedades Y Selectores Css Más Comunes

## Selectores Básicos

Los selectores básicos permiten apuntar a elementos HTML de forma directa. Incluyen tipos de etiqueta, clases, IDs y el universal.[^2][^6][^10]

- **Selector de tipo**: Selecciona todas las etiquetas específicas, como `p` para párrafos o `h1` para títulos.
- **Selector de clase**: Usa `.clase` para elementos con esa clase, reutilizable en múltiples elementos.
- **Selector de ID**: Usa `#id` para un elemento único en la página.
- **Selector universal**: `*` aplica estilos a todos los elementos del DOM.[^6]

Ejemplo de uso:

```css title:selectores-basicos
p { color: blue; }
.mi-clase { font-size: 16px; }
#header { background: gray; }
* { margin: 0; }
```


## Selectores De Combinación

Estos selectores usan relaciones entre elementos para mayor precisión.

- **Descendiente** (`sel1 sel2`): Selecciona `sel2` dentro de `sel1`, aunque no directo.
- **Hijo directo** (`sel1 > sel2`): Solo hijos inmediatos de `sel1`.
- **Hermano adyacente** (`sel1 + sel2`): `sel2` justo después de `sel1`.
- **Hermanos generales** (`sel1 ~ sel2`): Todos los `sel2` hermanos después de `sel1`.

Ejemplo:

```css title:selectores-combinacion
div p { margin: 10px; } /* Todos los p dentro de div */
ul > li { list-style: none; } /* Solo hijos li de ul */
h2 + p { font-weight: bold; }
```


## Selectores De Atributo

Seleccionan elementos por presencia o valor de atributos HTML.

- `[attr]`: Elementos con atributo `attr`.
- `[attr="valor"]`: Valor exacto.
- `[attr*="texto"]`: Contiene "texto".
- `[attr^="inicio"]`: Comienza con "inicio".
- `[attr$="final"]`: Termina con "final".

Ejemplo:

```css title:selectores-atributo
input[type="text"] { border: 1px solid; }
a[href*="example"] { color: red; }
[disabled] { opacity: 0.5; }
```


## Selectores Pseudo-clases

Añaden estilos dinámicos basados en estado o posición.

- `:hover`: Al pasar el cursor.
- `:active`: Al activar (click).
- `:first-child`, `:last-child`: Primer/último hijo.
- `:nth-child(n)`: Enésimo hijo.

Ejemplo:

```css title:pseudo-clases
a:hover { text-decoration: underline; }
li:first-child { font-weight: bold; }
tr:nth-child(even) { background: #f0f0f0; }
```


## Propiedades De Texto Y Fuente

Controlan tipografía y contenido textual.


| Propiedad | Descripción | Valores comunes |
| :-- | :-- | :-- |
| `color` | Color del texto | `red`, `#hex`, `rgb()`  |
| `font-size` | Tamaño de fuente | `16px`, `1rem`, `medium`  |
| `font-family` | Familia de fuente | `'Arial', sans-serif` |
| `font-weight` | Grosor | `bold`, `400`, `normal` |
| `text-align` | Alineación | `center`, `left`, `justify`  |

Ejemplo:

```css title:propiedades-texto
h1 { font-size: 2em; font-weight: bold; color: #333; }
p { text-align: justify; line-height: 1.5; }
```


## Propiedades De Caja (Box Model)

Definen espacio, tamaño y bordes.


| Propiedad | Descripción | Valores comunes |
| :-- | :-- | :-- |
| `width`/`height` | Dimensiones | `100%`, `auto`, `300px` |
| `margin` | Espacio exterior | `0 auto`, `10px`  |
| `padding` | Espacio interior | `15px`, `0 10px`  |
| `border` | Borde | `1px solid black`  |
| `border-radius` | Esquinas redondeadas | `5px`  |

Ejemplo:

```css title:box-model
div { width: 200px; margin: 20px auto; padding: 15px; border: 2px solid; border-radius: 8px; }
```


## Propiedades De Fondo Y Visuales

Estilos de fondo y visibilidad.

- `background-color`: Color de fondo (`lightblue`).
- `background-image`: Imagen (`url('img.jpg')`).
- `display`: Tipo de caja (`block`, `flex`, `grid`).
- `position`: Posicionamiento (`relative`, `absolute`, `fixed`).
- `z-index`: Orden Z (números enteros).

Ejemplo:

```css title:fondo-visuales
.box { background: linear-gradient(blue, white); display: flex; position: relative; z-index: 10; }
```


## Propiedades Flexbox/Grid (Layout Moderno)

Para diseños flexibles.

- Flexbox: `display: flex`, `justify-content: center`, `align-items: center`.
- Grid: `display: grid`, `grid-template-columns: 1fr 1fr`.

Ejemplo Flexbox:

```css title:flexbox
.container { display: flex; justify-content: space-between; align-items: center; }
```



