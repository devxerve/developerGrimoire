---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# Formularios
## Métodos De Envío
### Get
Realiza una petición a un URL (Commando HTTP) los datos se pasan en la propia URL. Si un formulario es alojado en la dirección http://universidad.es/practicas/formulario/ Cuando escribas los datos, esta dirección se generará en el navegador http://universidad.es/practicas/servicio.php?nombre=Pepe&apellidos=Mateos&sexo=hombre
### Post
Funciona igual, se pasan los datos como pares (nombre =Pepe...) pero dentro del paquete de datos. Parece más seguro, pero no lo es, simplemente los mete en la cabecera, que puede set leída por cualquiera que esté haciendo Spoofing (Escuchar) en la red del cliente, aunque es más difícil obtener los datos. 

# Ejemplos
Formulario.html
