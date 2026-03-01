---
cssclasses:
  - center-images
  - center-titles
  - page-grid
  - pen-red
---

# Legibilidad Del Código

> [!attention] REGLAS
> MAXIMO 120 CARACTERES POR LINEA, 4 ESPACIOS DE IDENTACION (TAB) SEGUN JERARQUIA

# Variables

## <mark style="background: #CACFD9A6;">Inicialización Y Datos</mark>

<mark style="background: #FFF3A3A6;">LAS VARIABLES SE INICIALIZAN EN EL MENOR ALCANCE POSIBLE, ES DECIR, DONDE SE VAN A USAR (SI SE USAN EN TODO EL PROGRAMA SE INICIALIZAN AL PRINCIPIO)</mark>

```cpp title="Inicialización de variables"
const char INI_CHAR = 0;
const int INI_INT = 0;
const bool INI_BOOL = 0;
const float INI_FLOAT = 0f;
const double INI_DOUBLE = 0.0;
const long INI_LONG = 0L;
const short INI_SHORT = 0;

//STRINGS
const std::string INI_STRING = "a";
```
<div class="page-break" style="page-break-before: always;"></div>
![[Datos Primitivos C++]]


<div class="page-break" style="page-break-before: always;"></div>

# Nomenclatura De Variables, Métodos Y Clases
camelCase variables y métodos
PascalCase clases

<mark style="background: #FFF3A3A6;">NOMBRES DESCRIPTIVOS, NO INTERPRETABLES</mark>

```c++ title="Nomenclatura"
class SaludarProgramador //PascalCase
	void saludoProgramador(){ //camelCase
		std::string nombreProgramador = "Ignacio"; //camelCase
			std::cout << "Hola," << nombreProgramador; // Printea Hola ignacio 
	}
```

# Comentarios
Seguimos el estándar Doxygen
Estructura:

```cpp title="Doxygen"
/**
  * @brief Resumen de la clase /metodo
  * Comentarios genericos sobre la clase/metodo
  * @param [nombre] parametros de la estructura
  * @return[nombre] valor devuelto
  */
```

Ejemplo:

```cpp title="Comentarios Doxygen"
/**
 * @brief Clase que se usa para saludar al programador 
 * @param nombreProgramador String que almacena el nombre del programador
 */
 
class SaludarProgramador //PascalCase
	void saludoProgramador(){ //camelCase
		std::string nombreProgramador = "Ignacio"; //camelCase
			std::cout << "Hola," << nombreProgramador; // Printea Hola ignacio 
	}
```
# Manejo De Errores

<mark style="background: #FFF3A3A6;">LAS INSTRUCCIONES CRITICAS SE PROTEGEN CON try/catch</mark>

> [!attention] INSTRUCCIONES A PROTEGER
> Operaciones de entrada/salida
> Sockets de transmision (procesos)
> Configuraciones de sensores/Operaciones de carga de archivos
> Operaciones con memoria (Lilypad tiene muy poca memoria)
> BLOQUE MAIN


# Gestión De Memoria
> [!attention] PROHIBIDO
>NO SE PUEDE USAR NEW/DELETE ¡NUNCA!


`{cpp} System.out.println("hello world");`
`{cpp} printf("\nHello World!")`
