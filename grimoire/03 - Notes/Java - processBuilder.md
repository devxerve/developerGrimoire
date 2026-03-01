---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
date: 2026-01-28T08:59
---

---
# Processbuilder en java

> [!summary] ProcessBuilder
> Sirve para lanzar procesos desde java, tiene sus propios métodos, consultarlos en el enlace a continuación
> https://docs.oracle.com/javase/8/docs/api/java/lang/ProcessBuilder.html

# Ejemplo de código con processbuilder (Secuencial)

```java title="ProcessBuilder Secuencial"
package lanzamientoEstructuradoSecuencial;
	import java.io.IOException;
	import java.util.InputMismatchException;
	import java.util.Scanner;

public class Principal {
	final static int INI_INT = 0;
	public static void lanzarProceso(int num, String ruta){
	ProcessBuilder lanzador = new ProcessBuilder(ruta);
	
	for (int i = INI_INT; i < num; i++) {
		try {
			lanzador.start();
			System.out.println("Output del proceso " + (i+1) + " = [Correcto] ");
		} catch (IOException e) {
			System.out.println("Error al lanzar el proceso");
		}
	}
}
	public static void main(String[] args) {
		System.out.println("Inicio");
		Scanner entrada = new Scanner (System.in);
		int numero_ejecucion = INI_INT;
		String ruta = "C:\\Program Files\\Oracle\\VirtualBox\\VirtualBox.exe";
		System.out.println("Introduce el número de veces que quieres lanzar el proceso");
		
		do {
			try {
				numero_ejecucion = entrada.nextInt();
			} catch (InputMismatchException ex) {
				System.out.println("Se esperaba un número entero");
				entrada.next();
			}
		} while (numero_ejecucion < 1);
		lanzarProceso(numero_ejecucion, ruta);
		System.out.println("Bye");
		entrada.close();
		}
}
```

# Ejemplo código con processbuilder (Concurrente)
```java title="Clase LanzarProceso"
package lanzamientoPOOConcurrente;

import java.io.IOException;

public class LanzarProceso {
    public static int contador_proceso = 0;
    ProcessBuilder process;
    public String ruta;
    public int numero;
    
    LanzarProceso(String ruta, int numero){
        this.ruta = ruta;
        this.numero = numero;
        contador_proceso++;
    }
    
    public void ejecutar(int numero){
        System.out.println("Ejecutando el proceso numero " + numero);
        process = new ProcessBuilder(this.ruta);
        try {
            process.start();
        } catch (IOException e) {
            e.printStackTrace();
            System.out.println("Error con el proceso " + numero);
        }
    }
}
```

```java title="Clase Principal"
package lanzamientoPOOConcurrente;

import java.util.ArrayList;
import java.util.Scanner;

public class Principal {
final static String RUTA = "\"C:\\Program Files\\Oracle\\VirtualBox\\VirtualBox.exe\"";
final static int INI_INT = 0;
public static void main(String[] args) {
    System.out.println("Inicio");
		Scanner entrada = new Scanner (System.in);
        int numero = INI_INT;
        ArrayList<LanzarProceso> lista_procesos = new ArrayList<LanzarProceso>();
		System.out.println("Introduce el número de veces que quieres lanzar el proceso");
        numero = entrada.nextInt();
        for(int i = INI_INT; i <numero; i++){
            LanzarProceso proceso = new LanzarProceso(RUTA, i+1);
            lista_procesos.add(proceso);  
        }

        for (LanzarProceso proceso : lista_procesos) {
            proceso.ejecutar(proceso.numero);
        }
        entrada.close();  
}
}
```
