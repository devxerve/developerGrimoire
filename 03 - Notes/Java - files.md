---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# :dev_java_original: java.io
El paquete java.io de [[01 - Languages/Java/Index|Java]] dispone de varias clases para dar soporte al trabajo de ficheros, dependen de:
 - Tipo de contenido
 - Modo de acceso al fichero

## Según tipo de contenido
***
> [!note] Ficheros con caracteres (texto)
> Son accesibles desde cualquier editor que ofrezca el sistema operativo, tienen exclusivamente caracteres

> [!note] Ficheros binarios (bytes)
> Son aquellos ficheros que no contienen caracteres, sino bytes, solo se pueden abrir por programas específicos, que saben decodificar esos bytes

## Según modo de acceso
***
> [!note] Ficheros Secuenciales
> La información se guarda como una cadena continua de bytes, por lo que para acceder a 1 se debe acceder a todos los anteriores a ese

> [!note] Ficheros Aleatorios
> Se puede acceder directamente a una posición especifica del archivo sin tener que recorrer datos previos, por ejemplo usar Arrays es un modo de acceso aleatorio

# Clase file (java.io)
***
Con independencia del tipo de fichero, Java define una clase dentro del paquete que java.io que representa un archivo o directorio dentro de un sistema de ficheros


## Jfilechooser
Es una clase como el [[Clases de JAVA#Scanner|Scanner]], funciona con diferentes métodos, consultarlos aquí:
https://docs.oracle.com/javase/8/docs/api/javax/swing/JFileChooser.html
```java title="Ejemplo JFileChooser"
private File abrirFichero(){ //Método tipo FILE
	JFileChooser selector = new JFileChooser();
	selector.setMultiSelectionEnabled(false);
	File fichero = null;
	int seleccion = selector.showOpenDialog(null);
	try {
		if(seleccion == JFileChooser.APPROVE_OPTION){
			fichero = selector.getSelectedFile();
		}
	}catch(HeadlessException e){
		return null;
	}
	
	return fichero;
}
```

```java title="Explicación Parte 1"
private File abrirFichero(){ //Método tipo FILE.
        JFileChooser selector = new JFileChooser(); // Declaración del selector.
	(Instrucciones);
	return File (variable)
```

```java title="Explicación parte 2"
selector.setMultiSelectionEnabled(false); //Desactiva la multiselección
	File fichero = null; //Variable fichero tipo File inicializada a null
	int seleccion = selector.showOpenDialog(null); //Muestra ventana dialogo (tipo abrir fichero show(Open)Dialog), y asigna lo que ocurra con ella a la variable selección.
	
```

```java title="Explicación parte 3"
try {
	if(seleccion == JFileChooser.APPROVE_OPTION){ // Si en la ventana se da a ACEPTAR.
		fichero = selector.getSelectedFile(); //Fichero = archivo seleccionado.
	}
	}catch(HeadlessException e){ //Catch de
		return null;
}
```

