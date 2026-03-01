---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# Elementos Estructurales Semánticos ## Header
Marca la cabecera de la página, no confundir con Head, simplemente marca una series de párrafos como cabecera.
- Si esta a nivel de la etiqueta body indica que el contenido es la cabecera de la pág. completa
- Dentro de un elemento de sección indica que el contenido es la cabecera de ese elemento.
```html
<header>
    <h1>Ejemplos_Visualización_Información</h1>
    <a href="/"><img src="logo.png" alt="Logo de la página"></a> <!--Esto es el logo como enlace a la página principal-->
    <nav>
        <!--Aquí van enlaces de navegación-->
    </nav>
</header>
```
## Footer
Es como el Header pero marca el pie de una página, no puede estar dentro de un elemento header o Address.
- Si esta al nivel de la etiqueta body indica el pie general de la página
- Dentro de un elemento de sección indica que el contenido es el pie de página de ese elemento 
```html
<footer>
    <h3>Contacto</h3>
    <p>Teléfono: 123-456-7890</p>
    <p>Email: contacto@dominio.com</p>
</footer>
```
# Main
Permite indicar una sección de forma que se entienda que es la sección principal del documento.
No puede colocarse dentro de secciones article, footer, header, aside o nav.

==SOLO PUEDE HABER UN ELEMENTO MAIN POR CADA WEB==

```html
<main> 
	<p>Ejemplos_Visualización_Información</p>
	<img src="ejemplo1" alt="ejemplo1_blablabla"/>
</main>
```

# Section
Divide partes de la página web. ==EL ID ES OPCIONAL==
```html
<main>
    <p>Ejemplos_Visualización_Información</p>
    <img src="ejemplo1" alt="ejemplo1_blablabla"/>
    <section id="Seccion_1">
        <h2>Sección 1 - Ejemplos_Visualización_Información</h2>
    </section>
    <section id="Seccion_2">
        <h2>Sección 2 - Ejemplos_Visualización_Información</h2>
    </section>
    <section id="Seccion_3">
        <h2>Sección 3 - Ejemplos_Visualización_Información</h2>
    </section>
</main>

```
# Nav
Marca una sección de enlaces o menú de navegación, se le puede dar mas formato con CSS a los enlaces. Solo se deberían marcar los enlaces que formen un menú dentro de un elemento nav.
```html
<nav>
    <ul>
        <li><a href="#Seccion_1">Sección 1 - Ejemplos_Visualización_Información</a></li>
        <li><a href="#Seccion_2">Sección 2 - Ejemplos_Visualización_Información</a></li>
        <li><a href="#Seccion_3">Sección 3 - Ejemplos_Visualización_Información</a></li>
    </ul>
</nav>
```
# Article
La idea es colocar elementos que sirvan para describir el mismo tema, permite estar dentro de otro article, aunque no es común.
```html
<article>
    <h2>Nuevo hardware para servidores en 2025</h2>
    <p>La última generación de procesadores mejora la eficiencia y reduce el consumo energético.</p>
</article>
```
# Aside
Sirve para marcar texto dentro de un articulo para que no se tenga en cuenta como parte de el, sino aparte para realizar declaraciones.
```html
<aside>
    <h3>Dato curioso</h3>
	<p>Linux es ampliamente usado en servidores por su estabilidad y flexibilidad.</p>
</aside>

```
# Figure
Sirve para agrupar los elementos relativos a una imagen con la propia imagen.
```html
<figure>
    <img src="servidor-nuevo.jpg" alt="Servidor de última generación">
    <figcaption>Servidor optimizado instalado en 2025.</figcaption>
</figure>

```
## Figcaption
Sirve para poner un título a la imagen dentro de un figure, haciendo como pie de imagen, se alineara igual que la imagen por defecto.
```html
<figcaption>Servidor optimizado instalado en 2025.</figcaption>
```

