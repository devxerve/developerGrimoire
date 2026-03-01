---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# :dev_mysql_original: Sentencia Select - Sintaxis Mínima

> [!INFO] ACLARACIÓN
> Los corchetes indican que lo que está dentro es opcional, el ; finaliza la instrucción (se ejecuta hasta ahí), MAYÚSCULAS = PALABRAS RESERVADAS DEL LENGUAJE SQL
> {Opcion obligatoria 1 | opcion obligatoria 2} Se debe escoger una de las opciones en la llave
> | delimita items unos de otros dentro de corchetes o llaves
## Sintaxis Mínima Sentencia Select
```SQL
SELECT expresion [,expresion]
[FROM tabla];
-- expresión = nombre_columna [Alias] | * | expresion [Alias] 
-- * Selecciona todo
```

### <mark style="background: #FF5582A6;">FROM</mark>
Indica la(s) tabla(s) afectada(s) por la consulta
### <mark style="background: #FF5582A6;">Nombre_columna</mark>
Indica el atributo de la tabla indicada en la cláusula from del que se desea mostrar su información 
### <mark style="background: #FF5582A6;">Expresión</mark>
La información que se desea mostrar puede set, en lugar de simplemente el valor de la columna una de estas opciones:
- Expresión en la que esté involucrada alguna columna de la tabla incluida en la cláusula FROM (pueden set algebraicas con estos símbolos: + , - , * , / , ^) o funciones propias de MySQL:
	- De fecha: CURRENT_DATE o DATE_ADD
	- Cadenas de caracteres: UPPERCASE, LOWERCASE o LENGTH
	- Numéricas: ABS, SQRT o MOD

