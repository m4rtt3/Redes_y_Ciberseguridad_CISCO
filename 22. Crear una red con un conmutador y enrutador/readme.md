# Packet Tracer - Crear una red con un conmutador y un enrutador

## Objetivos

-   Configurar las computadoras.
-   Configure a router.
-   Verifique la conectividad de extremo a extremo
-   Configure a switch.
-   Secure remote access to the router.

## Trasfondo/Situación

Su tía es propietaria de una pequeña agencia de seguros. Recientemente adquirió un router y switch de Cisco. Tiene dos PC cableadas que deben conectarse a la red. Está orgullosa de su progreso en su curso de redes y le preguntó si le gustaría demostrar sus habilidades. Su trabajo es conectar los dispositivos, implementar una configuración básica y verificar la conectividad. After network connectivity has been verified, you will use IOS commands to retrieve information from the devices to answer questions about your network equipment. También configurará el router para un acceso remoto seguro.

## Tabla de direccionamiento

| Dispositivo | Interfaz | Dirección IP | Máscara de subred | Puerta de enlace predeterminada |
| ----------- | -------- | ------------ | ----------------- | ------------------------------- |
| R1          | G0/0/0   | 192.168.0.1  | 255.255.255.0     | No corresponde                  |
| R1          | G0/0/1   | 192.168.1.1  | 255.255.255.0     | No corresponde                  |
| S1          | VLAN1    | 192.168.1.2  | 255.255.255.0     | 192.168.1.1                     |
| PCA         | NIC      | 192.168.1.3  | 255.255.255.0     | 192.168.1.1                     |
| PCB         | NIC      | 192.168.0.3  | 255.255.255.0     | 192.168.0.1                     |

## Paso 1. conectar los dispositivos mediante cables directos de cobre

R1 G0/0/1 - S1
PCA - S1
PCB - R1 G0/0/0

## Paso 2. Asignar direcciones de IPv4 estáticas

In this step, you will assign static IPv4 addressing information to the PC interfaces. Utilice la información de la tabla de direccionamiento para completar la tarea.

- Asignar IPv4 y Puerta de enlace predeterminada a partir de la tabla de direccionamiento a PCA y PCB

## Paso 3. Probar la conectividad entre PCA y PCB

Utilicé el comando ping para esta prueba. El ping falló debido a que no se ha configurado la dirección IP de las interfaces del router.

## Paso 4. Configuración básica del router

- Asignar R1 como hostname del router: 
  `Router(config)#hostname R1`
- Asignar como contraseña de EXEC con privilegios
  `R1(config)# enable secret class`
- Asignar contraseña de consola
  `S1(config)# line console 0`
  `S1(config-line)# password cisco`
  `S1(config-line)# login`
- Activar el encriptado de contraseñas
  `R1(config)# service password-encryption`
- Configurar el Aviso de Bienvenida
  `R1(config)# banner motd $Authorized Access Only!$`
- Configurar la IPv4 en la interfaz G0/0/0
  `R1(config)# interface g0/0/0`
  `R1(config-if)# ip address 192.168.0.1 255.255.255.0`
  `R1(config-if)# no shutdown`
- Configurar la IPv4 en la interfaz G0/0/1
  `R1(config)# interface g0/0/1`
  `R1(config-if)# ip address 192.168.1.1 255.255.255.0`
  `R1(config-if)# no shutdown`
- Guardar el archivo de configuración
  `R1# copy runing-config startup-config`

## Paso 5. Probar conectividad entre PCA y PCB

Usé el comando ping. Esta vez fue exitoso porque se configuró exitosamente las direcciones IP de las interfaces del router.

## Paso 6. Configuración básica del conmutador

ou will use the CLI tab for S1 to configure basic settings. Puede conectar un cable de consola y acceder a la CLI desde o si lo desea.PCAPCB However, in this activity, you can also just click S1 to open it.
- Asignanr el hostname S1
- Asginar contraseña de EXEC con privilegios
- Asignar contraseña de EXEC de usuario
- Habilitar el servicio de encriptado de contraseñas
- Crear un banner de bienvenida
- Configurar la dirección IP de la VLAN1
- Configurar la puerta de enlace predeterminada del conmutador
- Guardar el archivo de configuración

```cisco
Switch>enable
Switch#conf terminal 
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#hostname S1
S1(config)#enable secret class
S1(config)#line console 0
S1(config-line)#password cisco
S1(config-line)#login
S1(config-line)#exit
S1(config)#service password-encryption 
S1(config)#banner motd $Authorized access only!$
S1(config)#interface vlan 1
S1(config-if)#ip address 192.168.1.2 255.255.255.0
S1(config-if)#no shutdown 

S1(config-if)#
%LINK-5-CHANGED: Interface Vlan1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface Vlan1, changed state to up

S1(config-if)#exit
S1(config)#ip default-gateway 192.168.1.1
S1(config)#exit
S1#
%SYS-5-CONFIG_I: Configured from console by console

S1#copy running-config startup-config 
Destination filename [startup-config]? 
Building configuration...
[OK]
S1#
```

## Paso 7. Configurar el acceso remoto a R1

- Configurar el dominio como R1academy.net
- Generar las claves RSA de 1024 bits
- Crear usuario `SSHuser` con contraseña `cisco`
- Configurar las VTY para usar únicamente la base de datos de usuarios locales
- Configurar el acceso exclusivamente desde SSH

```cisco
R1>enable
Password: 
R1#conf terminal
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#ip domain-name academy.net
R1(config)#crypto key generate rsa
The name for the keys will be: R1.academy.net
Choose the size of the key modulus in the range of 360 to 2048 for your
  General Purpose Keys. Choosing a key modulus greater than 512 may take
  a few minutes.

How many bits in the modulus [512]: 1024
% Generating 1024 bit RSA keys, keys will be non-exportable...[OK]

R1(config)#username SSHuser secret cisco
*Mar 1 1:58:41.57: %SSH-5-ENABLED: SSH 1.99 has been enabled
R1(config)#line vty 0 15
R1(config-line)#transport input ssh
R1(config-line)#login local
R1(config-line)#exit
```

## Paso 8. Verificación del acceso remoto a través de SSH

Prueba desde PCA:

```powershell
C:\>ssh
Cisco Packet Tracer PC SSH

Usage: SSH -l username target

C:\>ssh -l SSHuser 192.168.1.1

Password: 

Authorized Access Only!

R1>
```
