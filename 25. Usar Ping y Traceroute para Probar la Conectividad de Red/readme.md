# **Packet Tracer - Use Ping y Traceroute para probar la conectividad de red**

## Objetivos

- Parte 1: Probar y restaurar la conectividad IPv4
- Parte 2: Probar y restaurar la conectividad IPv6

## Escenario

En esta actividad, hay problemas de conectividad. Además de reunir y registrar información acerca de la red, localizará los problemas e implementará soluciones razonables para restaurar la conectividad.

**Nota:** La contraseña de EXEC del usuario es **cisco**. La contraseña de EXEC privilegiado es **class**.

## Instrucciones

### Parte 1: Pruebe y restaure la conectividad IPv4

#### Paso 1: Utilice los comandos ipconfig y ping para verificar la conectividad

a.     Haga clic en **PC1** y abra el **Command Prompt** (símbolo del sistema).

b.     Introduzca el comando **ipconfig /all** para obtener la información de IPv4. Complete la **tabla de direccionamiento** con la dirección IPv4, la máscara de subred y el gateway predeterminado.

c.     Haga clic en **PC3** y abra el **Command Prompt** (símbolo del sistema).

d.     Introduzca el comando **ipconfig /all** para obtener la información de IPv4. Complete la **tabla de direccionamiento** con la dirección IPv4, la máscara de subred y el gateway predeterminado.

e.     Utilice el comando **ping** para probar la conectividad entre **PC1** y **PC3**. El ping debe fallar.

#### Paso 2: Localice el origen de la falla de conectividad

a.     En la **PC1**, introduzca el comando necesario para rastrear la ruta a la **PC3**.

##### Pregunta:
¿Cuál es la última dirección IPv4 a la que se llegó correctamente?
>10.10.1.97

b.     El rastreo finaliza después de 30 intentos. Presione **Ctrl**+**C** para detener el rastreo antes de los 30 intentos.

c.     En la **PC3**, introduzca el comando necesario para rastrear la ruta a la **PC1**.

##### Pregunta:
¿Cuál es la última dirección IPv4 a la que se llegó correctamente?
>10.10.1.17

d.     Presione **Ctrl**+**C** para detener el rastreo.

Abra la ventana de configuración

e.     Haga clic en **R1**. Presione **ENTER** e inicie sesión en el router.

f.      Introduzca el comando **show ip interface brief** para obtener una lista de las interfaces y su estado. Hay dos direcciones IPv4 en el router. Una se debe haber registrado en el paso 2a.

##### Pregunta:
¿Cuál es la otra?
>10.10.1.6

g.     Introduzca el comando **show ip route** para obtener una lista de las redes a las que está conectado el router. Observe que hay dos redes conectadas a la interfaz **Serial0/0/1**.

##### Pregunta:
¿Cuáles son?
>10.10.1.6/32, 10.10.1.4/30

h.     Repita los pasos 2e a 2g con el **R3** y registre tus respuestas.
>10.1.1.10
>10.10.1.8/30, 10.10.1.10/32

i.      Haga clic en **R2**. Presione **ENTER** e inicie sesión en el router.

j.      Ingrese el comando **show ip interface brief** y registre sus direcciones.
>Serial0/0/0 10.10.1.2
>Serial0/0/1 10.10.1.9

k.     Ejecute más pruebas si eso permite visualizar el problema. Está disponible el modo de simulación.

Cierre la ventana de configuración

#### Paso 3: Proponga una solución para resolver el problema

Compare sus respuestas del paso 2 con la documentación que tiene disponible para la red.

##### Pregunta:
¿Cuál es el error?
>La interfaz serial 0/0/0 del R2 está configurada con una dirección IP incorrecta.

¿Qué solución propondría para corregir el problema?
>Configure la dirección IP correcta en la interfaz serial 0/0/0 del R2 (10.10.1.5).

#### Paso 4: Implemente el plan

Implemente la solución que propuso en el paso 3b.

#### Paso 5: Verifique que la conectividad esté restaurada

a.     En la **PC1**, pruebe la conectividad a la **PC3**.

b.     En la **PC3**, pruebe la conectividad a la **PC1**.

##### Pregunta:
¿Se solucionó el problema?
>Sí

#### Paso 6: Registre la solución
```cisco
R2>enable
Password: 
R2#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
R2(config)#interface serial 0/0/0
R2(config-if)#ip address 10.10.1.5 255.255.255.252
R2(config-if)#
%DUAL-5-NBRCHANGE: IP-EIGRP 1: Neighbor 10.10.1.6 (Serial0/0/0) is up: new adjacency

R2(config-if)#no shutdown
R2(config-if)#exit
R2(config)#end
R2#
%SYS-5-CONFIG_I: Configured from console by console
R2#show ip int b
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     unassigned      YES unset  administratively down down 
GigabitEthernet0/1     unassigned      YES unset  administratively down down 
Serial0/0/0            10.10.1.5       YES manual up                    up 
Serial0/0/1            10.10.1.9       YES manual up                    up 
Vlan1                  unassigned      YES unset  administratively down down
R2#ping 10.10.1.18

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.1.18, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 21/23/28 ms

R2#ping 10.10.1.98

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 10.10.1.98, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 16/22/35 ms

R2#exit
```

### Parte 2: Pruebe y restaure la conectividad IPv6

#### Paso 1: Utilice los comandos ipv6config y ping para verificar la conectividad

a.     Haga clic en **PC2** y abra el **Command Prompt** (símbolo del sistema).

b.     Introduzca el comando **ipv6config /all** para obtener la información de IPv6. Complete la **tabla de direccionamiento** con la dirección IPv6, el prefijo de subred y el gateway predeterminado.

c.     Haga clic en **PC4** y abra el **Command Prompt** (símbolo del sistema).

d.     Introduzca el comando **ipv6config /all** para obtener la información de IPv6. Complete la **tabla de direccionamiento** con la dirección IPv6, el prefijo de subred y el gateway predeterminado.

e.     Pruebe la conectividad entre la **PC2** y la **PC4**. El ping debe fallar.

#### Paso 2: Localice el origen de la falla de conectividad

a.     En la **PC2**, introduzca el comando necesario para rastrear la ruta a la **PC4**.

#### Pregunta:
¿Cuál es la última dirección IPv6 a la que se llegó correctamente?
>2001:db 8:1:3: :2

b.     El rastreo finaliza después de 30 intentos. Presione **Ctrl**+**C** para detener el rastreo antes de los 30 intentos.

c.     En la **PC4**, introduzca el comando necesario para rastrear la ruta a la **PC2**.

#### Pregunta:
¿Cuál es la última dirección IPv6 a la que se llegó correctamente?
>No se alcanzó la dirección IPv6.

d.     Presione **Ctrl**+**C** para detener el rastreo.

e.     Haga clic en **R3**. Presione **ENTER** (Introducir) e inicie sesión en el router.

f.      Introduzca el comando **show ipv6 interface brief** para obtener una lista de las interfaces y su estado. Hay dos direcciones IPv6 en el router. Una debe coincidir con la dirección de gateway registrada en el paso 1d.

##### Pregunta:
¿Hay alguna discrepancia?
>Sí.

g.     Ejecute más pruebas si eso permite visualizar el problema. Está disponible el modo de simulación.

Cierre símbolo del sistema

#### Paso 3: Proponga una solución para resolver el problema

Compare sus respuestas del paso 2 con la documentación que tiene disponible para la red.

##### Pregunta:
¿Cuál es el error?
>La PC4 está utilizando una configuración del gateway predeterminado errónea.

¿Qué solución propondría para corregir el problema?
>Configure la PC4 con la dirección del gateway predeterminado correcta: FE80::3.

#### Paso 4: Implemente el plan

Implemente la solución que propuso en el paso 3b.

#### Paso 5: Verifique que la conectividad esté restaurada

a.     En la **PC2**, pruebe la conectividad a la **PC4**.

b.     En la **PC4**, pruebe la conectividad a la **PC2**.

##### Pregunta:
¿Se solucionó el problema?
>Sí
