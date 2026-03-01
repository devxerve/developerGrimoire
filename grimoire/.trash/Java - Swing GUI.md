---
título: Swing — Interfaces gráficas en Java
lenguaje: Java
categoría: GUI
fecha: 2025-01-01
tags:
  - java
  - swing
  - gui
estado: borrador
---

# Java — Swing GUI

## Resumen
> Librería de Java para crear interfaces gráficas de escritorio.

## Concepto

### Componentes principales
| Componente | Descripción |
|---|---|
| `JFrame` | Ventana principal |
| `JPanel` | Contenedor de componentes |
| `JButton` | Botón |
| `JLabel` | Etiqueta de texto |
| `JTextField` | Campo de texto |
| `JTable` | Tabla de datos |

### Layouts
- `BorderLayout` — Norte, Sur, Este, Oeste, Centro
- `FlowLayout` — Izquierda a derecha
- `GridLayout` — Cuadrícula

## Ejemplos
```java
import javax.swing.*;

public class MiVentana extends JFrame {
    public MiVentana() {
        setTitle("Mi app");
        setSize(400, 300);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        JButton btn = new JButton("Haz clic");
        btn.addActionListener(e -> System.out.println("Clic!"));

        add(btn);
        setVisible(true);
    }

    public static void main(String[] args) {
        new MiVentana();
    }
}
```

## Ver también
- [[Notes/Java - OOP Basics|OOP en Java]]

## Referencias
- 
