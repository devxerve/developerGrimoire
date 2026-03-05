---
cssclasses:
  - "centerTitles "
  - " centerImages "
  - " roundedImages"
---

# Programación En Arduino
La idea principal es simple
Aquí hay un ejemplo de un código para un botón que enciende una luz y su  explicación

![[Ejemplo_circuito.png|Ejemplo Circuito Simple|500x500]]
<div class="page-break" style="page-break-before: always;"></div>

```c++ title="Ejemplo Arduino"
// C++ code
int buttonState = 0;
int led = 10;
void setup() {
  pinMode(2, INPUT);
  pinMode(10, OUTPUT);
}

void loop(){
  buttonState = digitalRead(2);
  Serial.begin(9600);
  if (buttonState == HIGH) {
    delay(1000);
    Serial.println("Boton pulsado");
    digitalWrite(led, HIGH);
    delay(1000);
  } else {
    digitalWrite(led,LOW); 
  }
  delay(10); 
}
```

---
# Pasos Iniciales
> [!warning] AVISO
> SUPER IMPORTANTE DEFINIR VARIABLES/ALIAS (Asignandolos a pines de la placa)
SUPER IMPORTANTE DEFINIR LO QUE HACE CADA PIN (INPUT/OUTPUT) DENTRO DEL METODO void setup()


```c++ title="Inicio programa"
int buttonState = 0; //declaracion VARIABLES (LOS DATOS CAMBIAN) en funcion del pin de conexion
int led = 10;
void setup() {
  pinMode(2, INPUT);
  pinMode(10, OUTPUT); //definicion pines
}
```


<div class="page-break" style="page-break-before: always;"></div>

# Método Loop (main)

```c++ title="Metodo loop (main)"
void loop(){
  buttonState = digitalRead(2); // Quiere decir que la variable buttonState se basa en la lectura del pin 2 (digital)
  Serial.begin(9600); // Para imprimir entrada se crea un monitor serial
  if (buttonState == HIGH) { //Condicion if (LECTURA DIGITAL = HIGH / LOW)
    Serial.println("Boton pulsado"); //Trazado para comprobar que va bien
    delay(1000); // Delay para ejecucion mas suave
    digitalWrite(led, HIGH);
    delay(1000); // Delay para ejecucion mas suave
  } else {
    digitalWrite(led,LOW); 
  }
  delay(10); 
}
```

> [!attention] Importante
> EL TIPADO DE LOS METODOS ES MUY SIMILAR O EL MISMO QUE EN JAVA

