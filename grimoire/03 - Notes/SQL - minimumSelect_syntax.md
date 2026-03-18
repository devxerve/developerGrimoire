---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Sentencia select - sintaxis mínima

```sql
SELECT expresion [,expresion]
[FROM tabla];
-- expresión = nombre_columna [Alias] | * | expresion [Alias] 
-- * Selecciona todo
```

### From
Indica la(s) tabla(s) afectada(s) por la consulta
### Nombre_columna
Indica el atributo de la tabla indicada en la cláusula from del que se desea mostrar su información 
### Expresión
La información que se desea mostrar puede set, en lugar de simplemente el valor de la columna una de estas opciones:
- Expresión en la que esté involucrada alguna columna de la tabla incluida en la cláusula FROM (pueden set algebraicas con estos símbolos: + , - , * , / , ^) o funciones propias de MySQL:
	- De fecha: CURRENT_DATE o DATE_ADD
	- Cadenas de caracteres: UPPERCASE, LOWERCASE o LENGTH
	- Numéricas: ABS, SQRT o MOD

