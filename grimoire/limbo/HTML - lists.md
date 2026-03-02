---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :luc_list: Listas
Se usan para enumerar elementos.
El formato es la etiqueta de apertura de la lista, y los diferentes ítems englobados en su etiqueta  < li > ítem </ li>
==Se puede cambiar el estilo del li con CSS (incluso para poner una imagen) o con atributos==
Se define el estilo de la lista con type="estilo"
Se puede poner un estilo a un li unicamente con el atributo type="estilo"

## Hay 3 Tipos:
- Listas ordenadas
	- Se abre con la etiqueta < ol > 
	- Se puede invertir el orden con el atributo reversed (sin =" ")
	- Se puede empezar en un número o letra especifica usando el atributo start="número"
	- Como su nombre indica los ítems van con un orden especifico
	- Tipos de lista ordenada
		- type="a" --> lista alfabética en minúsculas
		- type="A" --> lista alfabética en mayúsculas
		- type="i" --> lista de números romanos en minúsculas
		- type="I" --> lista de números romanos en mayúsculas
		- type="1" --> lista numerada
```html cpp title:Ejemplo_ol
<ol type="1">
		<li>Este es el primer ítem de la lista</li>
		<li type="a">Este es el segundo ítem de la lista</li>
		<li>Este es el tercer ítem de la lista</li>
</ol>
```
<ol type="1">
		<li>Este es el primer ítem de la lista</li>
		<li type="a">Este es el segundo ítem de la lista</li>
		<li>Este es el tercer ítem de la lista</li>
</ol>
- Listas desordenadas
	- Se abre con la etiqueta < ul> (Se usa el atributo type para definir el marcador de la lista)
	- Los ítems van desordenado
	- Se puede poner un type a un li pero solo cambiara ese en concreto
	- Tipos de lista desordenada
		- type="circle" --> marcador circular (○)
		- type="disc" --> marcador de punto (●)
		- type ="square" --> marcador cuadrado (■)
```html cpp title:Ejemplo_ul
<ul type="square">
	<li>Este es el primer ítem de la lista</li>
	<li type="disc">Este es el segundo ítem de la lista</li>
	<li>Este es el tercer ítem de la lista</li>
</ul>
```
<ul type="square">
	<li>Este es el primer ítem de la lista</li>
	<li type="disc">Este es el segundo ítem de la lista</li>
	<li>Este es el tercer ítem de la lista</li>
</ul>

- Listas de términos
	- Crea una lista de definiciones de términos se usa con la etiqueta < dl > 
	- Termino a definir ==< dt > termino </ dt>== y su definición ==< dd > Definición </ dd >==
```html cpp title:Ejemplo_dl
<dl>
	<dt>Listas ordenadas</dt>
		<dd> Se abren con un ol y tienen varios tipos (numeros normales, romanos y letras</dd>
		
	<dt>Listas desordenadas</dt>
		<dd>Se abren con un ul y tienen varios tipos (circulo, cuadrado y disco)</dd>
		
	<dt>Lista de terminos</dt>
		<dd>Se usan para definir terminos con dt y su definicion con dd </dd>
</dl>
```
<dl>
	<dt>Listas ordenadas</dt>
		<dd> Se abren con un ol y tienen varios tipos (numeros normals, romanos y letras</dd>
		
	<dt>Listas desordenadas</dt>
		<dd>Se abren con un ul y tienen varios tipos (circulo, cuadrado y disco)</dd>
		
	<dt>Lista de terminos</dt>
		<dd>Se usan para definir terminos con dt y su definicion con dd </dd>
</dl>


