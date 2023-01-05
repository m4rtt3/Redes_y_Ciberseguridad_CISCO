# Packet Tracer - Configurar DHCP en un router inalámbrico

## Objetivos
- Conectar 3 PCs a un router inalámbrico

- Cambiar la configuración DHCP a un rango de red específico

- Configurar los clientes para obtener su dirección vía DHCP

## Antecedentes / Escenario
Un usuario doméstico desea utilizar un router inalámbrico para conectar 3 PCs. Los 3 PCs deben obtener su dirección automáticamente del router inalámbrico.

## Instrucciones
### Parte 1: Configurar la topología de red

a.     Añade tres PC genéricos.

b.     Conecte cada PC a un puerto Ethernet del router inalámbrico mediante cables rectos.

### Parte 2: Observar la configuración DHCP por defecto

a.     Después de que las luces ámbar se hayan vuelto verdes, haga clic en PC0. Haga clic en la pestaña Escritorio. Seleccione Configuración IP. Seleccione DHCP para recibir una dirección IP del router habilitado para DHCP.

Pregunta:
Registre la dirección IP de la puerta de enlace predeterminada:

b.     Cierre la ventana Configuración IP.

c.     Abra un navegador Web.

d.     Introduzca la dirección IP de la puerta de enlace predeterminada registrada anteriormente en el campo URL. Cuando se le solicite, introduzca el nombre de usuario admin y la contraseña admin.

e.     Desplácese por la página Configuración básica para ver la configuración predeterminada, incluida la dirección IP predeterminada del router inalámbrico.

f.      Observe que DHCP está activado, la dirección de inicio del rango DHCP y el rango de direcciones disponibles para los clientes.

### Parte 3: Cambiar la dirección IP predeterminada del router inalámbrico

a.     Dentro de la sección Router IP Settings, cambie la dirección IP a: 192.168.5.1.

b.     Desplácese hasta la parte inferior de la página y haga clic en Guardar configuración.

c.     Si se ha hecho correctamente, la página web mostrará un mensaje de error. Cierre el navegador web.

d.     Haga clic en Configuración IP para renovar la dirección IP asignada. Haga clic en Estática. Haga clic en DHCP para recibir nueva información de dirección IP del router inalámbrico.

e.     Abra el navegador web, introduzca la dirección IP 192.168.5.1 en el campo URL. Cuando se le solicite, introduzca el nombre de usuario admin y la contraseña admin.

### Parte 4: Cambie el rango de direcciones DHCP por defecto

a.     Observe que la dirección IP de inicio del servidor DHCP se actualiza a la misma red que la IP del router.

b.     Cambie la Dirección IP de Inicio de 192.168.5.100 a 192.168.5.126.

c.     Cambie el Número Máximo de Usuarios a 75.

d.     Desplácese hasta el final de la página y haga clic en Guardar configuración. Cierre el navegador web.

e.     Haga clic en Configuración IP para renovar la dirección IP asignada. Haga clic en Estática. Haga clic en DHCP para recibir nueva información de dirección IP del router inalámbrico.

f.      Seleccione Símbolo del sistema. Introduzca ipconfig.

Pregunta:
Registre la dirección IP del PC0:

### Parte 5: Habilitar DHCP en los otros PCs
a.     Haga clic en PC1.

b.     Seleccione la pestaña Escritorio.

c.     Seleccione Configuración IP.

d.     Haga clic en DHCP.

Pregunta:
Anote la dirección IP del PC1:

e.     Cierre la ventana de configuración.

f.      Habilite DHCP en PC2 siguiendo los pasos para PC1.

Parte 6: Verificar la conectividad
a.     Haga clic en PC2 y seleccione la pestaña Escritorio.

b.     Seleccione Símbolo del sistema.

c.     Introduzca ipconfig en el símbolo del sistema para ver la configuración IP.

d.     Cuando se le solicite, ingrese ping 192.168.5.1 para hacer ping al enrutador inalámbrico.

e.     Ingrese ping 192.168.5.126 para hacer ping a PC0.

f.       Cuando se le solicite, ingrese ping 192.168.5.127 para hacer ping a PC1.

g.     Los pings a todos los dispositivos deben producir un resultado correcto.