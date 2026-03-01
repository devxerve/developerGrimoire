---
cssclasses:
  - center-titles
  - rounded-images
  - center-images
  - page-grid
  - pen-red
---
# Módulos de la placa 
> [!info] IMPORTANTE
> Todos los datos se envían a la aplicación(menos lo de la apertura que también se procesa aquí para modificar el estado del led) , allí se procesan, NUNCA SE PROCESAN EN EL ARDUINO (NO HAY SUFICIENTE MEMORIA)
> 
> HAY 2 TIPOS DE DATOS : Analógico (0 | 1) o Digital (Valores distintos)

## 1. Apertura de la bolsa
Se registran cambios de luz con el sensor de luz lilypad, y se registra cuanto tiempo pasa entre esos cambios de luz y cuantas veces se abre.
![[light_sensor.png|Lilypad Light Sensor]]
## 2. Medidas de la botella
El sensor de peso se conecta al módulo de procesamiento, y se mide el valor cuando se detecta la apertura de la bolsa, se debe comprobar el contraste entre el valor inicial y final (en cada apertura), así como la propia detección del peso para saber si la botella esta o no esta colocada.
![[Modulo HX711.png|Modulo procesamiento|700]]
![[Celula de carga.png|Celula de carga|750]]
### 2.1 Sensor infrarrojo / proximidad
El sensor de peso se complementa con un infrarrojo / proximidad para comprobar si la botella esta o no esta colocada 
## 3. (OPCIONAL) Sensor de humedad
Se debe registrar mediante un sensor GSR (prefabricado o hecho con tela conductora) la cantidad de humedad de las palmas de las manos del usuario
![[gsr.png|Sensor montado]]
![[cinta_cobre.png|Cinta de cobre|650]]
## 4. Led y Vibración
Usando todos los parámetros anteriores y los registrados por el usuario en la aplicación
![[zumbador.png]]
![[Pixel.png]]

## 5. Envio y recepcion de datos (Bluetooth)
Se deben enviar datos a la aplicación cada X minutos (se puede decidir mas adelante), y se reciben cada X minutos y al principio y final del día.
![[HC05.png|Modulo Bluetooth HC05]]
### 5.1 Parámetros
Los parámetros que se registren en [[App Requirements#4. Parametrización|la aplicación]] deben ser guardados como parámetros en la placa, para poder usarlos en diferentes módulos del programa.