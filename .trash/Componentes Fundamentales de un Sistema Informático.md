---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# Components Fundamentales De Un Sistema Informático

## Definición De Sistema Informático

Un sistema informático es un conjunto de elementos interrelacionados que have possible el tratamiento automático de la información. Es el sistema encargado de recoger datos, procesarlos y transmitir la información una vez procesada.

## Components Principales

- **Hardware (Físico)**: Todos los components tangibles del ordenador

- **Software (Lógico)**: Sistemas operativos, aplicaciones, programas

- **Usuarios (Humano)**: Personas que interactúan con el sistema
## Components Físicos Internos De Un Ordenador

## Placa Base (Motherboard)

Circuito impreso que conecta todos los components internos del ordenador. Contiene:

- Zócalo (socket) para instalar el procesador (CPU)

- Ranuras de memoria (slots DIMM) para módulos RAM

- Ranuras de expansión (slots PCI Express) para tarjetas gráficas, sonido, red

- Controladoras integradas para unidades de almacenamiento (IDE, SATA, M.2/NVMe)

- Chipset Northbridge: controla comunicación entre CPU, RAM y tarjeta gráfica

- Chipset Southbridge: controla puertos USB, IDE, disquetera, PCI, BIOS, red, audio

- Chip BIOS: contiene el firmware de arranque

- Conectores internos y externos

- Batería CMOS para mantener alimentación del reloj y BIOS


## Factores De Forma

Estándares mundiales que determinan el tamaño y orientación de la placa con respecto a la caja. Los más extendidos son:

- **Standard-ATX**: Para PC de uso general

- **Micro-ATX**: Más compacta

- **Mini-ITX**: Muy pequeña

- **E-ATX (Extended-ATX)**: Para equipos de gama alta

- **Pico-ITX y Nano-ITX**: Sistemas embebidos


## Chasis O Caja

Estructura metálica o de plástico que contiene todos los components internos. Tipos según tamaño:

- **Mini Torre**: 30-45 cm

- **Media Torre**: 45-60 cm

- **Full Tower**: 55-68 cm

- **Super/Ultra Torre**: Más de 68 cm


---

## Procesador (CPU)

## Definición

Circuito integrado que actúa como el cerebro del ordenador. Encargado de interpretar y ejecutar las instrucciones del software, realizando operaciones lógicas, aritméticas y de control.

## Parámetros Del Procesador

- **Frecuencia de Reloj**: Determina la velocidad de ejecución de instrucciones (Hz, GHz)

- **Velocidad del Bus**: Comunicación que establece con el resto del sistema

- **Memoria Caché**: L1, L2 y L3 (memoria interna de alta velocidad)

- **Número de Núcleos**: Unidades de procesamiento independientes

- **Número de Hilos**: Permite manejar más procesos simultáneamente (Hyper-Threading en Intel, SMT en AMD)


## Criterios De Selección

- Consumo energético

- Frecuencia de reloj base y turbo

- Número de núcleos y hilos

- Memoria caché

- Tipo de bus

- Integración de GPU (iGPU)


## Fabricantes Principales

- **Intel**: Procesadores Core, Xeon, Atom

- **AMD**: Procesadores Ryzen (arquitecturas Zen, Zen 2, Zen 3, Zen 4)

- **Qualcomm**: Snapdragon para móviles

- **Apple**: M1, M2, M3 para Mac; A-Series para iPhone/iPad

- **IBM**: POWER10 para servidores


---

## Memoria

## Función

Almacenan tanto los datos como los programas que la CPU está procesando o va a procesar en un determinado memento.

## Memoria Rom (Read-Only Memory)

Memoria de Solo Lectura. Los datos almacenados no se pueden modificar.

**Tipos de ROM:**

- **PROM** (Programmable ROM): Programmable una única vez

- **EPROM** (Erasable PROM): Se borra con luz ultravioleta

- **EEPROM** (Electrically Erasable PROM): Se reprograma eléctricamente


**Funciones de la BIOS:**

- Rutina del BIOS (Basic Input-Output System): Activa periféricos de entrada/salida

- Rutina de arranque o POST (Power On Self Test): Autodiagnóstico de encendido

- Rutina Setup: Configuración de opciones básicas del sistema


## Memoria Ram (Random Access Memory)

Memoria de Lectura-Escritura. Memoria del usuario que contiene temporalmente el programa, datos y resultados siendo usados. Es memoria volátil, pierde contenido al apagar el ordenador.

**Variante especial:**

- **CMOS RAM**: Almacena información sobre configuración del sistema


**Tipos de RAM:**

- **DRAM** (Dynamic RAM): Necesita actualizarse periódicamente, más económica

- **SRAM** (Static RAM): No require actualizaciones, más rápida pero costosa

- **SDRAM** (Synchronous DRAM): Sincronizada con bus del sistema

- **DDR SDRAM, LPDDR, HBM, GDDR**: Variantes modernas


**Generaciones DDR:**

- DDR, DDR2, DDR3, DDR4, DDR5


**Formatos físicos:**

- DIMM (sobremesa)

- SODIMM (portátiles)


---

## Unidades De Almacenamiento Secundario

## Discos Duros

Dispositivos de almacenamiento no volátil que guardan los datos incluso cuando el ordenador está apagado.

**Tipos tecnológicos:**

- **HDD (Hard Disk Drive)**: Mecánico, utilize platos y cabezales magnéticos

- **SSD (Solid State Drive)**: Sin partes móviles, más rápido y silencioso, utilize memoria flash

- **SSHD (Solid State Hybrid Drive)**: Combina HDD + SSD


**Tipos de conexión:**

- **IDE (PATA)**: Antiguo, cables anchos y lentos

- **SCSI**: Usado en servidores, alto rendimiento

- **SATA**: Actual y común, cables finos, conexión individual

- **SAS**: Versión professional de SATA para servidores

- **PCIe/NVMe**: Tecnología moderna de alta velocidad para SSD M.2


## Evolución De Controladoras

IDE → SATA → M.2/NVMe (mejoras progresivas en velocidad y capacidad)

## Components Periféricos

## Dispositivos De Entrada

- Ratón, Teclado

- Pantalla táctil

- Escáner

- Joystick

- Micrófono


## Dispositivos De Salida

- Monitor/Pantalla

- Impresoras

- Altavoces

- Proyector


## Dispositivos De Entrada/Salida

- Impresoras multifuncionales

- Pantallas táctiles

- Otros sistemas (módem, router, etc.)


## Dispositivos De Red

- Tarjetas de red

- Módem

- Hub, Switch, Router