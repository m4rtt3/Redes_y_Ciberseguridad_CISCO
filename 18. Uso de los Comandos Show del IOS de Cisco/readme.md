# **Packet Tracer: Utilizar los comandos show de Cisco IOS**

# Objetivos

=   Utilizar los comandos **show** de Cisco IOS

# Aspectos básicos/situación

Los comandos **show** de Cisco IOS se usan muy frecuentemente al trabajar con equipos Cisco. En esta actividad, usaremos los comandos **show** en un router ubicado en un ISP.

# Instrucciones

## Parte 1: Conectarse al router Cisco 4321 del ISP.

En esta parte, utilizará el software de emulación de terminal en la PC del ISP para conectarse al enrutador Cisco 4321.

a.     Haga clic en **ISP PC**.

b.     Haga clic en la ficha **Desktop** (Escritorio). Seleccione **Terminal**. Revise la configuración del terminal y haga clic en **OK** (Aceptar) para continuar.

c.     La línea **ISPRouter >** indica que está en el modo EXEC de usuarios. Presione Enter (Intro) si la línea de comandos no aparece.

## Parte 2: Aprender los comandos show.

Use la información que muestran los comandos **show** para responder las siguientes preguntas.

### Paso 1: Explore los comandos show en el modo EXEC de usuario.

Abrir la ventana de configuración

a.     Escriba **show ?** en la línea de comandos.
>Estos son algunos de los comandos show disponibles: `show cdp, show class-map, show clock`

#### Pregunta:
Mencione algunos comandos **show** más que estén disponibles en el modo EXEC de usuario.

b.     Introduzca **show arp** en el cursor.

#### Pregunta:
Registre la dirección MAC y la dirección IP.
>`0001.96CD.2501: 209.165.201.1, 000A.F3C7.5CD3: 209.165.201.5, y 0002.162C.67A7: 209.165.201.10`

c.     Introduzca **show flash** en el cursor.

#### Pregunta:
Registre la imagen de IOS que se indica:
>`ISR4300-universalK9.03.16.05.S.155-3.s5-ext.spa.bin`

d.     Escriba **show ip route** en la línea de comandos.

#### Pregunta:
¿Cuántas rutas aparecen en la tabla?
>`2`

e.     Escriba **show interfaces** en la línea de comandos.

#### Pregunta:
¿Qué interfaz se encuentra activa y en funcionamiento?

| Interfaz              | Estado                | Protocolo |
| --------------------- | --------------------- | --------- |
| GigabitEthernet 0/0/0 | Activo                | Activo    |
| GigabitEthernet 0/0/1 | Administratively Down | Inactivo  |
| Serial 0/1/0          | Inactivo              | Inactivo  |
| Serial 0/1/1          | Inactivo              | Inactivo  |

f.      Escriba **show ip interfaces** en la línea de comandos.

#### Pregunta:
Según la salida de **show ip interface** , ¿qué interfaz está conectada?
>`GigabitEthernet0/0/0`

g.     Escriba **show version** en la línea de comandos.

#### Pregunta:
¿Qué paquete de tecnología está habilitado en este momento en el router?
>`ipbasek9 y securityk9`

h.     Introduzca **show protocols** en el cursor.

#### Pregunta:
¿Qué protocolos están habilitados actualmente en el enrutador?
>`Internet Protocol routing is enabled. Line protocol is up for GigabitEthernet0/0/0.`

i.      Ingrese **show running-config** en el indicador.

#### Pregunta:
¿Cuál es la salida?
>`% Invalid input detected at '^' marker.`

### Paso 2: Explorar los comandos show en el modo EXEC de usuario.

a.     Introduzca **enable** en la línea de comandos para ingresar al modo EXEC con privilegios.

#### Pregunta:
Mencione algunos otros comandos **show** en este modo.
>`show aaa, show access-list, show file`

b.     Ingrese **show running-config** en el indicador.

#### Pregunta:
¿Cuál es la salida?
>La salida muestra las configuraciones y los ajustes actuales.
