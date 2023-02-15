# Packet Tracer: Conectarse a un servidor web

## Objetivos
Observar cómo se envían los paquetes a través de Internet usando direcciones IP.

## Instrucciones
### Parte 1: Verifique la conectividad con el servidor Web
a.     Abra la ventana de la petición de entrada de comandos del host de origen. Seleccione PC0.

b.     Seleccione la ficha Desktop (Escritorio) > Command Prompt (Línea de comandos).

c.     Verificar la conectividad al servidor Web. En la línea de comandos, haga ping en la dirección IP del servidor web ingresando ping 172.33.100.50.

PC> ping 172.33.100.50

 

Pinging 172.33.100.50 with 32 bytes of data:

 

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

 

Ping statistics for 172.33.100.50:

Packets: Sent = 4, Received = 3, Lost = 1 (25% loss),

Approximate round trip times in milli-seconds:

Minimum = 0ms, Maximum = 0ms, Average = 0ms

Una respuesta verifica la conectividad desde el cliente al servidor web de destino. Inicialmente se puede agotar el tiempo de espera de la respuesta mientras se cargan los dispositivos y se ejecuta ARP.

d.     Cierre solamente la ventana de la línea de comandos haciendo clic en la cruz que se encuentra dentro de la ventana de la línea de comandos. Asegúrese de dejar abierta la ventana de configuración de PC0.

### Parte 2: Conéctese con el servidor Web a través del cliente Web
a.     En la ficha Desktop (Escritorio) de PC0, seleccione Web Browser (Navegador web).

b.     Escriba 172.33.100.50 en la URL y haga clic en Go (Ir). El cliente web se conectará al servidor web a través de la dirección IP y abrirá la página web.




#### Mensaje de la página web

**Welcome to the Learn IP Web Site**

You were able to reach this website because you had the IP address of the web server. The connecting PC also had a web client running on the device.