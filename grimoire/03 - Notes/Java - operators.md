---
cssclasses:
  - centerTitles
  - " centerImages "
  - " roundedImages"
tags:
  - java
---

# :luc_code: :dev_java_original:Operadores Java
## Operadores aritméticos
Los operadores aritméticos son utilizados para realizar operaciones matemáticas
> [!NOTE] Operadores aritméticos
> suma +
> resta -
> multiplicación *
> división / 
> módulo % (Calcula el resto de una division)

```java title="Operadores aritméticos"
int n1=2, n2= 0 , n3 = 4;
n2 = n1 * n2; //n2 = 4
n2 = n2-n1; //n2 = 2
n2 = n2 + n1 + 15; //n2 = 19
n2 = n2/n1; //n2 = 9
n2 = 17 % n3; //n2 = 1 (17 entre 4 es 4 y sobra 1)
```


## Operadores relacionales / de comparación

Evalúan la igualdad y la magnitud 
#### Comparación
> [!NOTE] Operadores relaciones
> Menor que <
> Mayor que <
> No Menor que !<
> No mayor que !>
> Menor o igual que <=
> Mayor o igual que >=
> Distinto de !=
> Igual que ==

#### Java
```java title="Relacionales java"
int m = 2, n = 5;
boolean res = false;
res = m > n; //res = false
res = m < n; //res = true
res = m >= n; //res = false
res = m <= n; //res = true
res = m == n; //res = false
res = m != n; //res = true
```

## Operadores lógicos
### Lógicos
> [!NOTE] Operadores Lógicos
> AND && o & (El resultado es true si ambos lo son)
> OR || (El resultado es false salvo que uno de los operandos sea true)
> NOT ! (Si el operando es true el resultado será false )
> XOR ^ (Si un operando es true y el otro false el resultado será true)

### Operadores lógicos

```java title="Operadores logicos java"  group="Operadores Logicos"
int m = 2, n = 5;
boolean res;
res = m > n && m >= n; //res = false
res = !(m < n || m != n); // res = false
```

## Operadores unitarios
Se aplican sobre un único operando.
> [!NOTE] Operadores Unitarios
> Complemento a 1 del operando ~ 
> Cambio de signo del operando - 
> Decremento del operando --
> Incremento del operando ++
> No operando !

```java title="Operadores unitarios"
int m = 2, n = 5;
m++; //m=3
n--: //n=4
```
## Operadores de asignación
Permiten asignar los valores a los distintos operandos
> [!NOTE] Operadores Unitarios
> Asignación  = 
> Multiplicación y asignación * = (A* = B Equivale a A = A * B)
> División y asignación / = (Igual)
> Módulo y asignación % = (Igual)
> Suma y asignación + = (Igual)
> Resta y asignación - = (Igual)

```java cpp title:Operadores_asignación
int num = 5;
num += 5; //num = 10, equivale a num = num +5
num -= 2; //num = 3, equivale a num = num -2
num *= 3; //num = 15, equivale a num = num *3
num /= 2; //num = 2, equivale a num = num/2 (resto = 1)
num %= 2; //num = 1, equivale a num = num % 2 
```


