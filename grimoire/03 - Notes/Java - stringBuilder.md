---
cssclasses:
  - "centerTitles "
  - " roundedImages"
  - " centerImages"
tags:
  - java
---

# :dev_java_original::luc_text_cursor_input: 🚧StringBuilder
Es una clase mutable que permite crear y manipular secuencias de caracteres de forma eficiente
> [!info] Métodos
> Se pueden consultar aqui https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html

```java title="StringBuilder"
StringBuilder sb = new StringBuilder ("Hola"); // objeto con hola escrito
sb.append(" Mundo :)"); //Se añade Mundo :) AL FINAL DE LA CADENA (append)
sb.insert(4, ","); // Se INSERTA EN LA POSICION 4 una "," (insert)
sb.delete(10,12); // Se ELIMINA EN EL RANGO DE LA POSICION 10-12 (delete)
System.out.println(sb.toString()); // Printeamos el objeto como string 
```



















***
# Contenido relacionado
[[StringBuilder - .Net]]