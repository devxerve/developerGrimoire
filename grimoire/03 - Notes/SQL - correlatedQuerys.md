---
tags:
  - sql
cssclasses:
  - centerTitles
  - " roundedImages"
  - " centerImages"
---

# :dev_mysql_original: Correlated Query

Works with aliases in a table or query, in order to use this alias in the main query

```sql cpp title:Consultas_Correlacionadas
SELECT * FROM players p1 --p1 is the alias for this table (players) -- 
WHERE p1.salario > all (SELECT pc.salario FROM jugadores jc 
	WHERE pc.captain_id = pc.player_id AND pc.team = p1.team);
	--pc is the alias for the subquery -- 
```



