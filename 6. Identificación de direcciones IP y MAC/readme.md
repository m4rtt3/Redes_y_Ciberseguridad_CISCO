# Packet Tracer: Identificación de direcciones MAC y direcciones IP

# Objetivos

Parte 1: Recopilar información de PDU para la comunicación de red local

Parte 2: Recopilar información de PDU para la comunicación de red remota

# Aspectos básicos

Si está interesado en una carrera en administración de redes o seguridad de redes, es importante que comprenda los procesos de comunicación de red normales. En esta actividad de Packet Tracer, inspeccionará las tramas de Ethernet y los paquetes IP en diferentes puntos de la red a medida que viajan del origen al destino. Se centrará en la forma en que las direcciones MAC e IP cambian según el destino (local o remoto) y el lugar donde se capturan las PDU.

Packet Tracer tiene un modo de simulación que le permitirá investigar detalles sobre cómo viajan las PDU en las redes. Le permite verificar el direccionamiento MAC de capa 2 y el direccionamiento IPv4 de capa 3 de las PDU en diferentes ubicaciones de la red a medida que las PDU fluyen del origen al destino.

Esta actividad está optimizada para ver las PDU a medida que viajan en redes locales y remotas. Reunirá información de PDU en el modo de simulación de PT y responderá una serie de preguntas sobre los datos que obtenga. No se requiere ninguna configuración de dispositivo.

# Instrucciones

## Parte 1: Recopilar información de PDU para la comunicación de red local

En esta parte, estudiará cómo un dispositivo en una red local no necesita una puerta de enlace predeterminada para comunicarse con otro dispositivo en la misma red local.

**Nota**: Revise las Preguntas de reflexión en la Parte 3 antes de continuar con esta parte. Le dará una idea del tipo de información que necesitará recopilar.Haga clic en host **172.16.31.3** y abra el símbolo del sistema.

a.     Introduzca el comando **ping 172.16.31.2**. Este comando emitirá una serie de paquetes de solicitud de eco ICMP al destino. Si los paquetes llegan al destino, enviará un paquete de mensajes de respuesta de eco al origen de las solicitudes de ping.

b.     Haga clic en el botón **Modo de simulación** para cambiar al modo de simulación. Repita el comando **ping 172.16.31.2**. Aparece un icono de sobre que representa una PDU junto a **172.16.31.3**.

c.     Haga clic en la PDU y localice la siguiente información en las pestañas **Modelo OSI** y **Detalles de PDU de salida**. La ficha **Outbound PDU Details** (Detalles de PDU de salida) muestra encabezados de paquetes y paquetes simplificados para la PDU. Debe observar los siguientes detalles sobre el direccionamiento para la PDU.

·       En el dispositivo: **172.16.31.3**

·       Dirección MAC de origen: **0060.7036.2849**

·       Dirección MAC destino:**000C:85CC:1DA7**

·       Dirección IP de origen:**172.16.31.3**

·       Dirección IP destino: **172.16.31.2**

d.     Haga clic en **Capture / Forward (la flecha derecha seguida de una barra vertical)** para mover la PDU al siguiente dispositivo. Use la pestaña del modelo OSI para recopilar la misma información del Paso 1d. Repita este proceso hasta que la PDU llegue al destino. Para cada paso de la ruta de entrega, registre la información de cada PDU en una hoja de cálculo que utilice un formato como el de la tabla que se muestra a continuación. La información para el primer paso se muestra en la tabla.

Formato de hoja de cálculo de ejemplo
| En dispositivo | MAC de origen  | MAC de destino | IPv4 de origen | IPv4 de destino |
|:--------------:|:--------------:|:--------------:|:--------------:|:---------------:|
|  172.16.31.3   | 0060.7036.2849 | 000C:85CC:1DA7 |  172.16.31.3   |   172.16.31.2   |
|    Switch 2    | 0060.7036.2849 | 000C:85CC:1DA7 |  172.16.31.3   |   172.16.31.2   |
|  172.16.31.2   | 000C:85CC:1DA7 | 0060.7036.2849 |  172.16.31.2   |   172.16.31.3   |
|    Switch 2    | 000C:85CC:1DA7 | 0060.7036.2849 |  172.16.31.2   |   172.16.31.3   |
|                |                |                |                |                 |


e.     Notará que la información para la PDU entrante no cambia.

#### Pregunta:

En la ventana de información de la PDU, haga clic en la ficha de la PDU saliente. ¿En qué se diferencia el direccionamiento y por qué? Registre el direccionamiento en su tabla.

f.       Vuelva al modo **Realtime**.

## Parte 2: Recopilar información de PDU para la comunicación de red remota

Para comunicarse con redes remotas, es necesario un dispositivo de puerta de enlace predeterminada. El dispositivo de puerta de enlace predeterminada conecta dos o más redes. En esta parte, estudiará el proceso que tiene lugar cuando un dispositivo se comunica con otro dispositivo que está en una red remota. Preste mucha atención a las direcciones MAC utilizadas.

**Nota**: Pase el mouse por el **Router**. Verá información sobre el direccionamiento de las interfaces del router. Consulte estas direcciones mientras observa el flujo de la PDU a través del router.

a.     Regrese al **símbolo del sistema** para **172.16.31.3**.

b.     Introduzca el comando **ping 10.10.10.2**. Los primeros pings pueden agotar el tiempo de espera.

c.     Cambie al **modo de simulación** y repita el comando **ping 10.10.10.2**. Aparece una PDU junto a **172.16.31.3**.

d.     Haga clic en la PDU y observe la siguiente pestaña de información:

	·       En el dispositivo: 172.16.31.3
	·       Dirección MAC de origen: 0060.7036.2849
	·       Dirección MAC destino: 00D0:BA8E:741A
	·       Dirección IP de origen: 172.16.31.3
	·       Dirección IP destino: 10.10.10.2

#### Pregunta:

¿Qué dispositivo tiene la MAC de destino que se muestra?

> Router

e.     Haga clic en **Capture / Forward (la flecha derecha seguida de una barra vertical)** para mover la PDU al siguiente dispositivo. Reúna la misma información del paso 1d. Repita este proceso hasta que la PDU llegue al destino. Registre la información de la PDU que recopiló del ping 172.16.31.5 a 10.10.10.2 en una hoja de cálculo utilizando un formato como la tabla de muestra que se muestra a continuación. Ingrese los detalles de las PDU entrantes y salientes en el router.

| En dispositivo | MAC de origen  |         MAC de destino          | IPv4 de origen | IPv4 de destino |
|:--------------:|:--------------:|:-------------------------------:|:--------------:|:---------------:|
|  172.16.31.3   | 0060.7036.2849 |         00D0:BA8E:741A          |  172.16.31.3   |   10.10.10.2    |
|    Switch 2    | 0060.7036.2849 |         00D0:BA8E:741A          |  172.16.31.3   |   10.10.10.2    |
|     Router     | 00D0.588C.2401 |         0060.2F84.4AB6          |  172.16.31.3   |   10.10.10.2    |
|    Switch 1    | 00D0.588C.2401 |         0060.2F84.4AB6          |  172.16.31.3   |   10.10.10.2    |
|  Access Point  | 0060.2F84.4AB6 | 0050.0FAB.6C82 / 00D0.588C.2401 |  172.16.31.3   |   10.10.10.2    |
|   10.10.10.2   |                |                                 |                |                 |
|                |                |                                 |                |                 |

Linea en blanco, sin información adicional

f.       Repita el proceso para el mensaje de respuesta de eco que se origina en el host 10.10.10.2. Complete la tabla para cada paso.

| En dispositivo | MAC de origen  |         MAC de destino          | IPv4 de origen | IPv4 de destino |
|:--------------:|:--------------:|:-------------------------------:|:--------------:|:---------------:|
|   10.10.10.2   | 0050.0FAB.6C82 | 0060.2F84.4AB6 / 00D0.588C.2401 |   10.10.10.2   |   172.16.31.3   |
|  Access Point  | 0060.2F84.4AB6 |         00D0.588C.2401          |   10.10.10.2   |   172.16.31.3   |
|    Switch 1    | 0060.2F84.4AB6 |         00D0.588C.2401          |   10.10.10.2   |   172.16.31.3   |
|     Router     | 00D0.BA8E.741A |         0060.7036.2849          |   10.10.10.2   |   172.16.31.3   |
|    Switch 2    | 00D0.BA8E.741A |         0060.7036.2849          |   10.10.10.2   |   172.16.31.3   |
|  172.16.31.3   |                |                                 |                |                 |

