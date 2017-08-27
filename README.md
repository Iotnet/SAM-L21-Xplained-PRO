# SAM-L21-Xplained-PRO
Proyecto para configurar la tarjeta SAML21 Xplained PRO junto con el módulo de expansión de Sigfox ATA8520E.

## Equipo y software necesario ##
<br />
-Atmel Studio (http://www.atmel.com/tools/ATMELSTUDIO.aspx, Únicamente para Windows. Durante la instalación, puede requerir que se instalen algunas actualizaciones de Windows.)
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

Algunos ejemplos se pueden descargar en el siguiente link: http://www.atmel.com/tools/atsaml21-xpro-b.aspx

## Conectando el módulo de conectividad Sigfox ATA8520E ##

Cerrar el programa Atmel Studio y desconectar la tarjeta. Conectar el módulo de expansión ATA8520E por el puerto "EXT1" y conectar el positivo y negativo del porta pilas en los pines correspondientes (Tener extremo cuidado de conectarlos correctamente y no aplicar mas de 3.3V, ya que la tarjeta no tiene protecciones por si se aplica más del voltaje indicado). 

![sam8](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam8.jpg?raw=true)

Conectar a la computadora y ejecutar Atmel Studio. Ahora deberemos cargar el proyecto que nos permitirá mandar mensajes por medio de Sigfox. El proyecto se puede descargar en el siguiente link: http://www.atmel.com/images/ata8520-ek13-f_toolpack_v1_2.zip
Descomprimir el archivo una vez descargado. 

Dentro de Atmel Studio, ir a File->Open->Project/Solution y buscar la carpeta creada al descomprimir el archivo descargado. Ya en la carpeta ir a ata8520-ek13-f_toolpack_v1_2\Software\ATA8520-EK3-F\SAML21_XplainedPRO y seleccionar el archivo SAML21_XplainedPRO_SW. 

Una vez abierto el proyecto, seleccionar la pestaña SAML21_XplainedPRO_SW->Device y cambiar el dispositivo de ATSAML21J18A a ATSAML21J18B, dando click en "Change Device" y seleccionando ATSAML21J18B.

![sam5](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam5.png?raw=true)

Ahora seleccionamos "Tool" y seleccionamos el programador "EDBG MSD ATML2241..."

![sam6](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam6.png?raw=true)

Finalmente, para correr el programa, se puede hacer de 2 formas: 

-Debug->Start Without Debugging: carga el proyecto a la tarjeta.

-Debug->Continue: permite debugear el proyecto para observar lo que esta pasando con las diferentes variables y detectar errores.

![sam7](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam7.png?raw=true)

## Mandando el primer mensaje ##

Ya que esta cargado el programa en la tarjeta, esperar unos segundos y presionar el botón SW1 de la tarjeta ATA8520E. Al presionarlo, encenderan los 2 leds (Led 1 y Power). El Led 1 parpadeara 4 veces indicando que se está mandando el mensaje, el cual contiene la información del sensor de temperatura que trae la tarjeta y el voltaje de las baterias.

![sam9](https://github.com/Iotnet/SAM-L21-Xplained-PRO/blob/master/images/sam9.png?raw=true)

Si parpadea mas de 5 veces, significa que la tarjeta de expansión no esta energizada correctamente.  


