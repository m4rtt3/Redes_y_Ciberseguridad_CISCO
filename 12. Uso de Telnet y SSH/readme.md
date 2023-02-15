# Packet Tracer: Uso de Telnet y SSH

# Tabla de direccionamiento

| Dispositivo       | Interfaz | Dirección IP | Máscara de subred |
| ----------------- | -------- | ------------ | ----------------- |
| SEDE CENTRAL (HQ) | 60/0/1   | 64.100.1.1   | 255.255.255.0     |
| PC0               | NIC      | DHCP         | DHCP              |
| PC@               | NIC      | DHCP         | DHCP              |

# Objetivos

En esta actividad, establecerá una conexión remota a un enrutador utilizando Telnet y SSH.

- Verifique la conectividad
- Acceder a un dispositivo remoto

# Instrucciones

## Parte 1: Verificar la conectividad

En esta parte, verificará que la PC tenga direccionamiento IP y pueda hacer ping al router remoto.

### Paso 1: Verificar la dirección IP en una PC.

a.     Desde una PC, haga clic en **Desktop** (Escritorio). Haga clic en **Command Prompt** (Símbolo del sistema).

b.     En el indicador, verifique que la PC tenga una dirección IP de DHCP.

#### Pregunta:

¿Qué comando utilizó para verificar la dirección IP de DHCP?
>`ipconfig`

### Paso 2: Verifique la conectividad a la sede central (HQ).

Verifique que pueda hacer ping al enrutador en **HQ** con la dirección IP que figura en la tabla de direccionamiento.

## Parte 2: Acceder a un dispositivo remoto

En esta parte, intentará establecer una conexión remota mediante Telnet y SSH.

### Paso 1: Telnet a la sede central (HQ).

En el indicador, ingrese el comando **telnet 64.100.1.1**.

#### Pregunta:

¿Tuvo éxito? ¿Cuál fue la salida?

```powershell
Trying 64.100.1.1 ...Open
[Connection to 64.100.1.1 closed by foreign host]
```

### Paso 2: SSH a HQ.

El enrutador está configurado correctamente para no permitir el acceso inseguro a Telnet. Debe usar SSH.

En el indicador, ingrese el comando **ssh -l admin 64.100.1.1**. Introduzca la contraseña **class** cuando corresponda.

```
C:\> **ssh -l admin 64.100.1.1**

Password:
```

#### Pregunta:

¿Qué aparece después de acceder al enrutador con éxito a través de SSH?
`HQ#`
