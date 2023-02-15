# **Packet Tracer: Usar el comando ping**

# Objetivos

Usar el comando **ping** para identificar configuraciones incorrectas en una PC.

# Aspectos básicos/situación

El dueño de una pequeña empresa descubre que algunos usuarios no pueden acceder a un sitio web. Todas las PC están configuradas con direcciones IP estáticas. Use el comando **ping** para identificar el problema.

# Instrucciones

## Parte 1: Verificar la conectividad

Acceda a la ficha **Desktop** (Escritorio) > **Web Browser** (Navegador web) de cada PC e introduzca la URL **www.cisco.pka**. Identifique las PC que no se pueden conectar con el servidor Web.

**Nota**: Todos los dispositivos requieren un tiempo para realizar el proceso de arranque. Deje pasar hasta un minuto para recibir una respuesta de la Web.

#### Pregunta:

¿Cuáles PC tienen problemas para conectarse al servidor Web?
> PC2

## Parte 2: Hacer ping al servidor web desde la PC con problemas de conectividad.

a.     En la PC, acceda a **Command Prompt** (Línea de comandos) desde la pestaña **Desktop** (Escritorio).

b.     Cuando se le solicite, ingrese **ping www.cisco.pka**.

#### Pregunta:

¿Obtuvo una respuesta al ping? ¿Qué dirección IP se muestra en la respuesta, en caso de existir alguna?
>No hubo respuesta. No se mostró ninguna dirección IP en el mensaje.


## Parte 3: Hacer ping al servidor web desde las PC configuradas correctamente.

a.     En la PC, acceda a **Command Prompt** (Línea de comandos) desde la pestaña **Desktop** (Escritorio).

b.     Cuando se le solicite, ingrese **ping www.cisco.pka**.

#### Pregunta:

¿El **ping** produjo una respuesta? ¿Qué dirección IP se devolvió, si la hay?
>Si hubo respuesta:
```powershell
Pinging 192.15.2.10 with 32 bytes of data:
  
Reply from 192.15.2.10: bytes=32 time<1ms TTL=127
Reply from 192.15.2.10: bytes=32 time<1ms TTL=127
Reply from 192.15.2.10: bytes=32 time=7ms TTL=127
Reply from 192.15.2.10: bytes=32 time=1ms TTL=127
  
Ping statistics for 192.15.2.10:
	Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
	Minimum = 0ms, Maximum = 7ms, Average = 2ms
``` 

## Parte 4: Hacer ping a la dirección IP del servidor web desde la PC con problemas de conectividad.

a.     En la PC, acceda a **Command Prompt** (Línea de comandos) desde la pestaña **Desktop** (Escritorio).

b.     Intente llegar a la dirección IP del servidor web con el comando **ping**.

¿El **ping** produjo una respuesta? De ser así, entonces la PC puede comunicarse con el servidor Web a través de la dirección IP, pero no a través del nombre de dominio. Esto puede indicar un problema en la configuración del servidor DNS en la PC.

## Parte 5: Comparar la información del servidor DNS en las PC.

a.     Acceda al **Command Prompt** (Línea de comandos) de las PC sin ningún problema.

b.     Con el comando **ipconfig /all**, examine la configuración del servidor DNS en las PC sin ningún problema.

c.     Acceda al **Command Prompt** (Línea de comandos) de las PC con problemas de conectividad.

d.     Con el comando **ipconfig /all**, examine la configuración del servidor DNS en las PC con problemas de conectividad. ¿Coinciden las dos configuraciones?

## Parte 6: Realizar los cambios de configuración necesarios en las PC.

a.     Navegue a la pestaña **Desktop** (Escritorio) de las PC con problemas y haga los cambios de configuración necesarios en **IP Configuration** (Configuración IP).

b.     Mediante el **Web Browser** (Navegador web) dentro de la ficha **Desktop** (Escritorio), conéctese con **www.cisco.pka** para verificar que los cambios de configuración hayan resuelto el problema.
