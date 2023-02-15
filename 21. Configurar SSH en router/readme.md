# **Packet Tracer - Configure SSH**

# Tabla de direccionamiento

| Dispositivo | Interfaz | Dirección IP | Máscara de subred |
| ----------- | -------- | ------------ | ----------------- |
| PC1         | NIC      | 10.10.10.10  | 255.255.255.0     |
| S1          | VLAN 1   | 10.10.10.2   | 255.255.255.0     |

# Objetivos

Parte 1: Proteger las contraseñas

Parte 2: Cifrar las comunicaciones

Parte 3: Verificar la implementación de SSH

# Aspectos básicos/Situación

SSH debe reemplazar a Telnet para las conexiones de administración. Telnet usa comunicaciones inseguras de texto no cifrado. SSH proporciona seguridad para las conexiones remotas mediante el cifrado seguro de todos los datos transmitidos entre los dispositivos. En esta actividad, protegerá un conmutador remoto con el cifrado de contraseñas y SSH.

# Instrucciones

## Parte 1: Contraseñas seguras

a.     Desde el símbolo del sistema en la **PC1**, acceda a **S1** mediante Telnet. La contraseña de los modos EXEC de usuario y EXEC con privilegios es **cisco**.

```cisco
PC> **telnet 10.10.10.2**
Trying 10.10.10.2 ...Open

User Access Verification
Password:

S1> **en**
Password:
S1#
```
b.     Guarde la configuración actual, de manera que pueda revertir cualquier error que cometa reiniciando el **S1**.

```cisco
S1# copy running-config startup-config
Destination filename [startup-config]?
Building configuration...
[OK]
```

c.     Muestre la configuración actual y observe que las contraseñas están en texto no cifrado.

d.     En el modo de configuración global, ingrese el comando que cifra las contraseñas de texto sin formato:

`S1(config)# service password-encryption`

e.     Verifique que las contraseñas estén cifradas.

## Parte 2: Cifrar las comunicaciones

### Paso 1: Establecer el nombre de dominio IP y generar claves seguras.

En general no es seguro utilizar Telnet, porque los datos se transfieren como texto no cifrado. Por lo tanto, utilice SSH siempre que esté disponible.

a.     Configure el nombre de dominio **netacad.pka.**

`S1(config)# ip domain-name netacad.pka`

b.     Se necesitan claves seguras para cifrar los datos. Genere las claves RSA con la longitud de clave 1024.

```cisco
S1(config)# crypto key generate rsa
The name for the keys will be: S1.netacad.pka
Choose the size of the key modulus in the range of 360 to 2048 for your
General Purpose Keys. Choosing a key modulus greater than 512 may take
a few minutes.
How many bits in the modulus [512]: **1024**
% Generating 1024 bit RSA keys, keys will be non-exportable...[OK]
```

### Paso 2: Crear un usuario de SSH y reconfigurar las líneas VTY para que solo admitan acceso por SSH.

a.     Cree un usuario **administrator** con **cisco** como contraseña secreta.

`S1(config)# username administrator secret cisco`

b.     Configure las líneas VTY para que revisen la base de datos local de nombres de usuario en busca de las credenciales de inicio de sesión y para que solo permitan el acceso remoto mediante SSH. Elimine la contraseña existente de la línea vty.

```cisco
S1(config)# line vty 0 15
S1(config-line)# login local
S1(config-line)# transport input ssh
S1(config-line)# no password cisco
```

## Parte 3: Verificar la implementación de SSH

a.     Cierre la sesión de Telnet e intente iniciar sesión nuevamente con Telnet. El intento debería fallar.

b.     Intente iniciar sesión mediante SSH. Escriba ssh y presione la tecla Enter, sin incluir ningún parámetro que revele las instrucciones de uso de comandos. Sugerencia: la opción -l representa la letra “L”, no el número 1.

c.     Cuando inicie sesión de forma correcta, ingrese al modo EXEC con privilegios y guarde la configuración. Si no pudo acceder de forma correcta al S1, reinicie y comience de nuevo en la parte 1.
