---
cssclasses:
  - center-images
  - rounded-images
  - center-titles
  - page-grid
  - pen-red
---

# Diagrama

![[Quantity_water_bottle-Cantidad_agua_botella.jpg|418x773]]

<div class="page-break" style="page-break-before: always;"></div>

# Pseudocódigo
```java title="Peudocódigo"
cantidadAgua(pesoAntes){
	agua_bebida = 0;
	ejecutar{
		peso = medirPeso();		
	}mientras(peso < 0);
	agua_bebida = pesoAntes - peso;
	devolver agua_bebida;
}
main{
	peso = medirPeso(); //Se guarda en la aplicación el peso de la medicion inmediatamente anterior  
	
	if(peso < 0){
		agua_bebida = cantidadAgua(peso);
		agua_diaria += agua_bebida;
	}
}
```

