# SAM-L21-Xplained-PRO
Proyecto para configurar la tarjeta SAML21 Xplained PRO junto con el módulo de Sigfox ATA8520E.

## Equipo y software necesario ##
<br />
-Atmel Studio (http://www.atmel.com/tools/ATMELSTUDIO.aspx, Unicamente para Windows. Durante la instalación, puede requerir que se instalen algunas actualizaciones de Windows.)
<br />
-Tarjeta Atmel SAML21 Xplained Pro.

![saml21](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/saml21.png?raw=true)

<br />
-Módulo de conectividad Sigfox ATA8520E.

![mod_sigfox](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/mod_sigfox.png?raw=true)

<br />
-2 pilas AAA.
<br />
-Porta pilas AAA.

![portapilas1](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/portapilas1.jpg?raw=true)

## Configuración de la tarjeta Atmel SAML21 Xplained Pro ##

Una vez instalado el programa Atmel Studio, procedemos a configurar la tarjeta SAML21. 
Conectamos la tarjeta a través del puerto "DEBUG USB" por medio de un cable hacia la computadora. Al conectarla, encenderan 2 leds

![sam1](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam1.png?raw=true) 

Ir al administrador de dispositivos y cambiar las propiedades del puerto (Baud rate = 38400, bit de datos= 8, paridad = ninguno, Bits de parada = 1) 

![sam2](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam2.png?raw=true) 

Ahora, abrimos el programa Atmel Studio. El programa automáticamente nos mostrará el dispositivo que está conectado. En la parte superior derecha debemos cambiar el perfil de "ESTANDAR" a "AVANZADO".

![sam3](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam3.png?raw=true) 

Una de las ventajas que tiene la tarjeta de Atmel, es que aparecerá una unidad externa llamada "XPLAINED" por lo que podemos cargarle programas unicamente arrastrando y soltando los archivos .bin en la unidad externa

![sam4](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam4.png?raw=true)

 
