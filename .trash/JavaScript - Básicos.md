---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# :dev_javascript_original: Javascript - Basicos
- Lenguaje de programación creado por la empresa Netscape
- Es el mas utilizado para añadir interactividad a las páginas web, sirve para validar datos en formularios y capturar eventos.
- EL código Javascript :dev_javascript_original: se integra en una página web (entre el codigo html :dev_html5_original:) y es el navegador el que lo interpreta y ejecuta (**Lenguaje interpretado**)
- Para empezar con JavaScript :dev_javascript_original: necesitamos conocer el [[DOM - Modelo de objetos del documento|DOM]] :obs_documents: : el modelo de objetos del documento donde se aplica 
- JavaScript utiliza **tipado dinámico**, es decir, **no es necesario declarar el tipo de dato** de una variable al definirla.

### Inserción

```html cpp title:Insercion_JavaScript
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Ejercicio1</title>
</head>
	<body>
	    <main>
	        <h1>Titulo principal</h1>
	        <section>
	            <h2>Titulo 2</h2>
	            <p id="para" style="color: blue;">Ejemplos varios de Javascript</p>
	        </section>
	        <script type="text/Javascript">
	            alert("Hola Mundo");
	            console.log("Para depurar...");
	        </script>
	    </main>
	</body>
</html>
```



