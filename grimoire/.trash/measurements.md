---
cssclasses:
  - center-images
  - center-titles
  - rounded-images
  - page-grid
  - pen-red
---
# Diagrama
![[diagrama_measurements.jpg|407x592]]

# Pseudocodigo
```cpp title="Pseudocodigo medidas"
[tipo] valor[peso,luz,botella] = 0;
valor = medida(valor,sensor)

medida(valor,sensor){
	
	(sensor == 1){
		[tipo] medida = leer pin placa;
		valor = medida
		break
	}(sensor == 2){
		[tipo] medida = leer pin placa;
		valor = medida
		break
	}
	devolver valor
}
```
