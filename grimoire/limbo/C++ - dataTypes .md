---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

Son datos muy similares a los [[Datos Primitivos java]] pero pueden tener modificadores, y tienen tamaños dependientes del compiler o la plataforma

```cpp title="Datos primitivos C++"
char dato 1 = 0;

short dato2 = 0;

int dato 3 = 0;

long dato 4 = 0L;

long long dato_5 = 0LL;

float dato6 = 0f;

double dato7 = 0.0;

bool dato8 = false;

//STRINGS

std::string dato9 = "a";
```

```cpp title="Modificadores de datos"
signed(default) int x = -1;  //Significa que el rango del int es completo (positivos y negativos)
unsigned int x = 1; //Solo puede ser mayor/igual a 0
short int x = 0; //El dato ocupa max 16bits
long int x = 0; //El dato ocupa entre 32 y 64 bits
long long int x = //El dato ocupa 64 bits
```
