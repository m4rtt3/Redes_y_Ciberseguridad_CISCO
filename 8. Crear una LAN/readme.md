**Packet Tracer: Crear una LAN**

# Tabla de direccionamiento
| Dispositivo         | Interfaz | Dirección IPv4  | Máscara de subred |
| ------------------- | -------- | --------------- | ----------------- |
| PC Admin            | NIC      | DHCP            | N/D               |
| PC de Administrador | NIC      | DHCP            | N/D               |
| Impresora           | NIC      | 192.168.1.100   | 255.255.255.0     |
| www. Cisco.pt       | NIC      | 209.165.200.225 | No disponible     |

# Objetivos

=    Conectar dispositivos de red y hosts

=    Configurar dispositivos con direccionamiento IPv4

=    Verificar la configuración y la conectividad del dispositivo final

=    Utilizar los comandos de red para ver la información del host

# Aspectos básicos/Situación

Se está abriendo una nueva sucursal y se le ha pedido que configure la LAN. Los dispositivos de red ya están configurados, pero debe conectarlos junto con los hosts. También debe configurar el direccionamiento IPv4 en los dispositivos finales y verificar que puedan alcanzar los recursos locales y remotos.

# Instrucciones

## Parte 1: Conectar dispositivos de red y hosts

### Paso 1: Encienda los dispositivos finales y el router de oficina.

a.     Haga clic en cada dispositivo y abra su pestaña Physical (Física). **Nota**: No hay ningún interruptor de alimentación en el modelo de switch utilizado en esta actividad.

b.     Localice el interruptor de alimentación para cada dispositivo en la ventana Vista de dispositivo físico.

c.     Haga clic en el interruptor de alimentación para encender el dispositivo. Debería ver una luz verde cerca del interruptor de alimentación para indicar que el dispositivo está encendido.

### Paso 2: Conectar los dispositivos finales.

Utilice la tabla y las instrucciones para conectar los dispositivos de red y los hosts para crear la red física.

Tabla de conexiones
| Dispositivo                          | Interfaz / Puerto | Conectado al dispositivo | Interfaz de conexión / Puerto |
| ------------------------------------ | ----------------- | ------------------------ | ----------------------------- |
| Office Router (Enrutador de oficina) | G0/0              | ISP1                     | G0/0                          |
| Office Router (Enrutador de oficina) | G0/1              | Switch                   | G0/1                          |
| PC Admin                             | NIC (F / 0)       | Switch                   | F0/1                          |
| PC de Administrador                  | NIC (F / 0)       | Switch                   | F0/2                          |
| Impresora                            | NIC (F / 0)       | Switch                   | F0/24                              |

**Nota:** En la tabla anterior, las interfaces designadas con **G** son interfaces GigabitEthernet. Las interfaces que se designan con **F** son interfaces FastEthernet.

a.     Conecte los dispositivos de red según la información de la tabla de conexiones mediante cables directos de cobre Ethernet. Para la conexión de Internet a Office Router, seleccione el dispositivo y el puerto de los menús desplegables que aparecen cuando hace clic en la nube con la herramienta de conexiones seleccionada.

b.     Conecte las dos PC y la impresora al switch de oficina según la información de la tabla de conexiones. Utilice cables directos de cobre.

c.     Debería ver luces de enlace verdes en todas las conexiones después de un breve retraso.

## Parte 2: Configurar dispositivos con direccionamiento IPv4

### Paso 1: Configure los hosts con información de direccionamiento.

a.     Las PC de Admin y Manager deben recibir la información de direccionamiento IP de DHCP. Office Router se ha configurado para proporcionar direcciones IP a los hosts en la LAN de la sucursal. Haga clic en las PC y vaya a las fichas de escritorio en cada PC. Abra la aplicación de configuración de IP y configure las PC para recibir sus direcciones IP dinámicamente.

b.     Las impresoras y los servidores a menudo se configuran manualmente con direccionamiento porque otros dispositivos en la red están configurados para acceder a ellos mediante direcciones IP. La configuración manual con una dirección estática garantizará que las direcciones IP de estos dispositivos no cambien.

1)     Haga clic en la impresora y abra la pestaña Configuración.

2)     Haga clic en la interfaz FastEthernet0 en el panel izquierdo.

3)     Ingrese la información de direccionamiento de la tabla de direccionamiento.

c.     Dado que las dos computadoras se encuentran en la misma red, las direcciones IPv4 serán similares, las máscaras de subred y las puertas de enlace predeterminadas serán idénticas también.

#### Preguntas:

¿Por qué cree que las direcciones IPv4 son diferentes, pero las máscaras de subred y los gateways predeterminados son los mismos?
>Porque están en la misma red local conectados a la misma interfaz del router a través del switch.

La impresora no requiere una puerta de enlace predeterminada porque solo los hosts podrán acceder a ella en la red local. Sin embargo, si necesita configurarlo con una puerta de enlace predeterminada, ¿qué valor utilizará la impresora? ¿Cómo puede determinar esto a partir de los otros dispositivos en la red?
>Utilizará el gateway 192.168.1.1

## Parte 3: Verificar la configuración y la conectividad del dispositivo final

### Paso 1: Verificar la conectividad entre las dos PC.

a.     Vaya a los escritorios de las PC y compruebe la configuración de direccionamiento IP. Debería ver que las PC han recibido dinámicamente direcciones IP en la red 192.168.1.0 255.255.255.0. También debería ver que han recibido direcciones para la configuración de la puerta de enlace predeterminada y del servidor DNS.

b.     Desde el símbolo del sistema en Admin PC, haga ping a la dirección IP de la impresora. Repita este proceso para Manager PC. Debería ver pings exitosos para cada uno. Esto verifica que las PC y la impresora estén encendidas, conectadas y direccionadas correctamente.

### Paso 2: Verificar la conectividad hacia internet.

Desde el escritorio de las PC, abra el navegador web. Ingrese la dirección IP del servidor de Internet para mostrar la página web. Repita el proceso pero conéctese con la URL del servidor.

#### Pregunta:

Si puede conectarse por la dirección IP, pero no por la URL, ¿cuál cree que es la causa de este problema?

>Dado que el DNS se utiliza para resolver las URL en direcciones IP, puede adivinar con seguridad que no se puede acceder al servidor DNS. Esto puede deberse a un problema de conectividad de red o a que falta o es incorrecta la dirección del servidor DNS configurada en los hosts.

## Parte 4: Utilizar los comandos de red para ver la información del host

Los comandos de red disponibles desde el símbolo del sistema en las PC son muy similares a los disponibles en Windows. En esta parte de la actividad, utilizará **ipconfig** y **tracert** para obtener más información sobre la LAN.

### Paso 1: Use comando ipconfig.

El comando ipconfig muestra detalles sobre el direccionamiento configurado en un host.

#### Pregunta:

Abra un símbolo del sistema en una de las PC, ingrese el comando **ipconfig** y tome nota de la información que se devuelve. Ahora ingrese el comando **ipconfig /all**. ¿Qué información adicional se muestra?
ipconfig

> Ipconfig /all muestra información sobre la dirección física (MAC) de la NIC. También muestra las direcciones de los servidores DHCP y DNS.

```powershell
FastEthernet0 Connection:(default port)

   Connection-specific DNS Suffix..: 
   Physical Address................: 0060.5C88.4291
   Link-local IPv6 Address.........: FE80::260:5CFF:FE88:4291
   IPv6 Address....................: ::
   IPv4 Address....................: 192.168.1.2
   Subnet Mask.....................: 255.255.255.0
   Default Gateway.................: ::
                                     192.168.1.1
   DHCP Servers....................: 192.168.1.1
   DHCPv6 IAID.....................: 
   DHCPv6 Client DUID..............: 00-01-00-01-DC-6C-63-D7-00-60-5C-88-42-91
   DNS Servers.....................: ::
                                     209.165.200.225
 ```

### Paso 2: Utilizar el comando tracert.

El comando tracert utiliza ICMP para devolver información sobre los routers que se pasan a medida que los paquetes pasan de la PC de origen al destino.

Rastree hasta un destino remoto yendo a una de las PC e ingresando **tracert** seguido de la URL del servidor web.

#### Preguntas:

```powershell
Tracing route to 209.165.200.225 over a maximum of 30 hops: 

  1   0 ms      0 ms      0 ms      192.168.1.1
  2   0 ms      0 ms      0 ms      209.165.200.233
  3   0 ms      0 ms      0 ms      209.165.200.225

Trace complete.
```

¿Cuántos enrutadores se pasan en el camino hacia el destino? ¿Cómo se identifican esos routers?
>Dos. Se identifican con direcciones de IP públicas d las interfaces entrantnes.

¿Dónde se encuentra el segundo router?
>En el ISP o Internet

Considere una oficina pequeña que tenga una LAN similar a la que ha creado aquí. ¿Cuál es el mayor desafío de las instalaciones para configurar la red en una nueva ubicación?
>La infraestructura de cableado físico. La oficina debe estar cableada y tener salidas de comunicación para todos los dispositivos. Además, las salidas deben estar en ubicaciones convenientes. Además, las salidas deben conectarse a una ubicación central donde se encuentren el switch y el router. El cableado físico puede presentar muchos problemas al crear una nueva ubicación de oficina. 
