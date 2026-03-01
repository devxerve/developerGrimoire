---
título: C++ en Arduino
lenguaje: C++
categoría: Embedded / Arduino
fecha: 2025-01-01
tags:
  - cpp
  - arduino
  - hardware
estado: borrador
---

# C++ — Arduino

## Resumen
> Programación de microcontroladores Arduino usando C++. Aplicado al proyecto Serious Games con Arduino Lilypad.

## Estructura básica de un sketch
```cpp
// Variables globales y librerías
#include <Arduino.h>

// Configuración inicial — se ejecuta una vez
void setup() {
    Serial.begin(9600);
    pinMode(LED_BUILTIN, OUTPUT);
}

// Bucle principal — se ejecuta continuamente
void loop() {
    digitalWrite(LED_BUILTIN, HIGH);
    delay(1000); // ms
    digitalWrite(LED_BUILTIN, LOW);
    delay(1000);
}
```

## Funciones esenciales
| Función | Descripción |
|---|---|
| `pinMode(pin, modo)` | Configura un pin como INPUT u OUTPUT |
| `digitalWrite(pin, valor)` | Escribe HIGH o LOW en un pin |
| `digitalRead(pin)` | Lee el valor digital de un pin |
| `analogRead(pin)` | Lee un valor analógico (0-1023) |
| `delay(ms)` | Pausa en milisegundos |
| `Serial.println(val)` | Imprime por el monitor serie |

## Arduino Lilypad
Versión de Arduino para wearables y textiles.
- Voltaje: 3.3V
- Pines cosibles, diseño circular

## Ver también
- [[Projects/Serious Games - Hydration Bag/Architecture|Proyecto Serious Games]]

## Referencias
- https://www.arduino.cc/reference/en/
