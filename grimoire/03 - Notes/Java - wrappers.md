---
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
tags:
  - java
---

# :dev_java_original:Wrappers
Son clases envoltorio de datos primitivos 
![[java - dataTypes]]

Sirven para tratar los datos primitivos como objetos

> [!danger] Importante
> Las clases Wrapper implementan objetos “inmutables” ya que estos objetos una vez convertidos no podrán ser cambiados de nuevo a datos primitivos.

Los wrapper implementan una ventaja importantísima
# <mark style="background: #FF5582A6;">Métodos Existentes para estas clases</mark>

> [!tip] Metodos disponibles
> Heredados de Object : https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html
> Heredados de Number: https://docs.oracle.com/javase/8/docs/api/java/lang/Number.html

```java title="Metodos comunes (NUMERICOS)"
valueOf(tipo) / valueOf(String) → // Devuelve el valor del objeto
parse[Tipo](String)  → lanza NumberFormatException // 
```

# Equivalencias con [[java - dataTypes]]

<mark style="background: #FF5582A6;">LO SIGUIENTE NO ES CODIGO ES UNA FORMA VISUAL DE VER LA EQUIVALENCIA</mark>

```java title="Equivalencias"
Integer = int;
Boolean = boolean;
Byte = byte;
Short = short;
Float = float;
Character = char;
Long = long;
```


#