---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# Funcionamiento Básico Css
## Sintaxis Css
El formato básico de CSS es el siguiente
```css cpp title:Estructura_CSS
selector{
	propiedad1: valor1;
	propiedad2: valor2;
}
```

El selector nos permite indicar el ítem al cual se le van a aplicar los estilos CSS
Las propiedades son cada una de las características que conforman el estilo CSS
## Formas De Aplicar Estilos
### En Una Etiqueta Html
```html
<p style="color:red"> Texto en rojo</p>
```
### En la Cabecera De la Página
```html
<html lang="es">
<head>
    <meta charset="UTF-8">
    <style>
        body{
            color:red;
        }
    </style>
    <title>Ejemplos</title>
</head>
<body>
    Pagina en rojo
</body>
</html>
```
### En Un Archivo Externo
```html
<html lang="es">
<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="estilos.css">
    <title>Ejemplos</title>
</head>
<body>
    SE APLICAN LOS ESTILOS DE estilos.css
</body>
</html>
```
## Orden De Aplicaciones De Estilos

> [!INFO] Orden
> - Estilos del navegador
> - Estilos externos (etiqueta link)
> - Etiqueta style
> - Atributo style

> [!Attention] IMPORTANTE
> Si 2 estilos se refieren al mismo elemento, y están en el mismo orden de prioridad (los 2 externos, en el style...) tiene preferencia el ultimo que aparece
## Herencias
Si una etiqueta está anidada dentro de otra <mark style="background: #FF5582A6;">SIEMPRE</mark> heredara las características de su etiqueta padre, y ya luego añadirá las suyas propias 

