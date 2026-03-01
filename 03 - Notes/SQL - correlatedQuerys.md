---
tags:
  - sql
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :dev_mysql_original: Consultas correlacionadas
Funcionan de manera que yo le pongo un alias a una tabla o consulta, para luego usarla en la consulta general

```SQL cpp title:Consultas_Correlacionadas
SELECT * FROM jugadores j1 --j1 es el alias de la tabla jugadores de aqui en adelante -- 
WHERE j1.salario > all (SELECT jc.salario FROM jugadores jc -- jc es el alias de la consulta que vamos a realizar --
						WHERE jc.id_capitan = jc.id_jugador AND jc.equipo = j1.equipo);

```



