---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# Módulos De la Aplicación

> [!attention] Importante INFORMACIÓN GENERAL
> TODOS los datos deben ser procesados en la aplicación, pero vienen del arduino.

## 1. Apertura De la Bolsa
Registrar los datos como un patrón para crear rutinas, y mandar avisos si el intervalo entre aperturas supera “x“ tiempo (depende de parámetros como sexo, altura y actividad física)

## 2. [[Cantidad De Agua Botella]] / Agua bebida
Cuando el sensor de peso devuelve una medida menor que 0 (la botella vacía también pesa y es = 0, esto significa que la botella ya no esta en su posición) se guarda la medición inmediatamente anterior y se coteja al devolver la botella a su posición original, este contraste se guarda y asigna como medida total del agua bebida, de manera que se pueda trabajar con el dato, mandar alertas si se necesita beber mas agua, y llevar un registro del agua bebida.

## 2.1 [[Agua total bebida]]
Se interpretan los datos de la [[#2. Cantidad De Agua Botella / Agua bebida]] y se calcula la cantidad de agua que ha bebido el usuario, con respecto al agua total que debe beber 
(depende de parámetros como sexo altura y actividad física)
## 3. Detección de la botella
Aparte del sensor de peso, implementar un sensor midiendo si hay o no hay botella mediante un infrarrojo, o un sensor de luz, y así poder detectar si la botella esta colocada o no en su posición

## 4. [[Parametrización]]
Cambio de los parámetros por parte del usuario, modificación del peso, altura, actividad física.

## 5. Almacenamiento de datos diarios en la BBDD
Al finalizar el día se guardan los datos del usuario en la base de datos, para permitir registros y rachas, estos datos deben ser accesibles por el usuario con un plazo máximo de un mes atrás.
## 6. Creación de estadísticas
A partir de los [[#4. Almacenamiento de datos diarios en la BBDD| Datos diarios]] se pueden crear medias de agua bebida al día/semana/mes, veces rellenada la botella…
## 7. Exportación de los datos
Estos datos deberían poder exportarse, con persistencia mensual en formato excel, xml o pdf, para poder ofrecer al usuario un almacenamiento de su información. 


## 8.Notificaciones
Se recogen datos del propio programa, y cuando los criterios se cumplen, se mandan distintas notificaciones a la aplicación
Las cosas que se pueden notificar pueden ser: 
- Botella no colocada
- Botella vacía
- Recordatorio de beber
- Fallo de los sensores
- Bolsa abierta (durante mucho tiempo)
- Cantidad de agua en la botella
- Agua total bebida
- Rachas
- Registro mensual

