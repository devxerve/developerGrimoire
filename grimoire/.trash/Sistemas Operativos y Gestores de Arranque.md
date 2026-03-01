---
cssclasses:
  - center-titles
  - page-grid
  - pen-red
---

# :dev_windows8_original: :dev_ubuntu_plain: :dev_linux_original:Sistemas Operativos

## Definición

El Sistema Operativo es el encargado de gestionar los recursos hardware y proveer servicios al resto de programas que se ejecuten sobre él. Es un intermediario entre el usuario y el hardware.

## Funciones Del so

- Proporciona servicios para facilitar ejecución y gestión eficiente de recursos

- Gestiona memoria, procesos, entrada/salida

- Gestión de archivos

- Gestión de redes

- Control de periféricos


## Arquitectura Del Sistema Operativo

APLICACIONES DE USUARIOS 
		↓
INTERFAZ DE USUARIO (SHELL) 
		↓ 
  APIs DEL NÚCLEO
		↓
	  KERNEL
		↓
	 DRIVERS
		↓
	HARDWARE
## Gestores Y Cargadores De Arranque

## Definición

El gestor de arranque (boot manager) es un pequeño programa que se ejecuta justo después de que la BIOS o UEFI terminan su autocomprobación inicial (POST).

## Función Principal

- Cargar el sistema operativo desde el disco donde está instalado

- Si hay varios sistemas (arranque múltiple), mostrar un menú para elegir cuál iniciar


## Diferencia Entre Gestor Y Cargador

|Componente|Función|Ejemplo|
|---|---|---|
|Gestor de arranque|Permite elegir qué SO iniciar|Windows Boot Manager / GRUB|
|Cargador de arranque|Carga el núcleo del SO elegido|winload.exe / GRUB (fase 2)|

## Gestores De Arranque Por Sistema

- **Windows**: Windows Boot Manager (bootmgr)

- **Linux**: GRUB (GRand Unified Bootloader)

- **macOS**: Boot Manager (EFI)


## Grub (Linux)

Detecta automáticamente otros sistemas operativos y ofrece un menú configurable. Compatible con BIOS/MBR y UEFI/EFI.

**Archivos principales:**

- `/boot/grub/grub.cfg`: Archivo de configuración del menú

- `/boot/vmlinuz`: Kernel del sistema

- `/boot/initrd.img`: Imagen de arranque inicial


---

## Secuencia De Arranque De Un Sistema Informático

1. **Botón de arranque ON**: Inicia fuente de alimentación

2. **Ejecución BIOS/UEFI**: Se ejecuta desde ROM

3. **Comprobación hardware**: Verifica components fundamentales (POST)

4. **Configuración hardware**: BIOS configura e instala components

5. **Carga del SO**: BIOS carga sistema operativo desde unidad de arranque

6. **Entrada en acción**: SO toma el control del sistema