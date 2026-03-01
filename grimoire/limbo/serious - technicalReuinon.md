---
cssclasses:
  - center-images
  - center-titles
  - page-grid
  - pen-red
---

# Implementaciones, Requisitos E Ideas
## Funciones a Cumplimentar
1. Detección de la apertura de la bolsa, y registro de la misma para avisos y crear rutinas.
2. Detección de la cantidad de agua bebida y la cantidad restante en las botellas para aviso de rellenarlas/beber.
3. Detección de la humedad en las palmas del usuario, a la hora de agarrar la mochila, para fortalecer aún más las medidas de hidratación.
4. Aviso por led y vibración en la propia mochila.
5. Aviso mediante notificaciones push en aplicación móvil conectada por bluetooth.
6. Aislamiento de los componentes susceptibles de ser estropeados por agua/polvo/agentes externos.

## Sensores E Implementación

### :dev_arduino_original: Lilypad light Sensor
![[light_sensor.png|Lilypad light sensor|700x700]]
Es un sensor de luz que emite un valor analógico de 0-5V. con la luz natural, emite 5V. Al cubrirlo con la mano emite 0V. En condiciones normales de iluminación en interiores emite entre 1-2V.

---
### Celda De Carga 10 Kg + Amplificador Voltaje Hx711 (Para Medir El Peso De Las Botellas Y Comprobar Cuanto Se bebe)
#### Links

#### Descripcion
![[Modulo HX711.png|Modulo HX711|700x504]]

Este amplificador de la señal sirve para poder darle al Arduino una señal a un voltaje con el que puede trabajar para leer datos
- Cable rojo (alimentación positiva): al pin E+ del HX-711
- Cable negro (masa): al pin E- del HX-711
- Cable blanco (señal): al pin A+ del HX-711
- Cable verde (señal): al pin A- del HX-711
- Las conexiones B+ y B- del HX-711 son para conectar una segunda celda de carga.

![[Celula de carga.png|Celula de carga|700x700]]

Mide la deformación del aluminio que la compone y saca el peso del objeto
- Alimentación: 5-10V
- Salida nominal: 1 mV/V ± 150 μV/V
- Material: Aluminio
- Medidas: 12.7 x 12.7 x 75 mm
https://electronicaymas.com/carga-y-magneticos/celula-de-carga-hasta-10kg-amplificador-hx711-10180
Precio del pack: 6.26
***
# Cables variados
Precio de cada uno: 2,65 € (hemos comprado 3)
![[image.png|197x255]]

![[image-1.png|203x262]]

![[image-2.png]]
***
### Zumbador Lilypad
Su voltaje de uso es de 5VDC.

![[zumbador.png|zumbador|700x700]]
***
### Led Lilypad Pixel
Esta placa tiene un led RGB, que se puede encadenar con otras placas y controlar cada led individualmente.
![[Pixel.png|Pixel|695x695]]
***
## Aviso Mediante App Con modulo Bluetooth

### Placa Bluetooth y Wifi ESP32

![[ESP32.png|Bluetooth + Wifi ESP32]]
Se enviarán notificaciones push mediante una app al usuario, además la app también podrá mandar mensajes al módulo Arduino al ser un módulo bluetooth Master/Slave

<mark style="background: #FFF3A3A6;">Sobre la app habrá documentación aparte</mark>
***
## Aislamiento Componentes Críticos
Implementaremos una bolsa/recubrimiento impermeable, con las juntas cubiertas por silicona o otros elementos  a los componentes susceptibles de estropearse en contacto con el agua

