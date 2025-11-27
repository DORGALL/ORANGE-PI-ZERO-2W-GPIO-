# ORANGE-PI-ZERO-2W-GPIO-
MANUAL DE USO DE GPIO EN ORANGE PI ZERO 2W (ARMBIAN MINIMAL)
Control de GPIO y pantalla ST7789 usando C y libgpiod 2.x

Este repositorio documenta los paso que seguí para controlar GPIO y manejar una pantalla SPI ST7789 en una Orange Pi
Zero 2w usando lenguaje C y la librería libgpiod.


1) Actualizar el sistema: Antes de instalar paquetes o compilar código, es recomendable actualizar los respositorios y
   paquetes del sistema:
   
    $ sudo apt update
    $ sudo apt upgrade

3) Instalar dependencias necesarias: Permitirán acceder a libgpiod desde lenguaje C y poder compilar el codigo:
    $ sudo apt install libgpiod-dev
    $ sudo apt install libgpiod-tools
    $ sudo apt install build-essential

4) Identificamos los chips GPIO del sistema: Los GPIO en linux se organizan en bloques llamados "gpiochip*", cada uno es
   manejado por un controlador interno.
   
    $ sudo gpiodetect
   
   Aquí saldrá algo similar a:

     gpiochip0 [7022000.pinctrl] (32 lines)
     gpiochip1 [300b000.pinctrl] (288 lines)

   Alternativa:

     $ ls /dev/gpiochip*

   En nuestra Orange Pi Zero 2W, el chip que normalmente maneja los GPIO del header es "/dev/gpiochip1".

4) Información del gpiochip1: Si queremos más información de cada uno de los pines y su estado, listamos con:
     $ sudo gpioinfo






















