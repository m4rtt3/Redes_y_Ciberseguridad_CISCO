**Packet Tracer: Examinar NAT en un enrutador inalámbrico**

# Objetivos

=    Examinar la configuración NAT en un router inalámbrico

=    Configurar 4 PC para que se conecten a un router inalámbrico mediante DHCP

=    Examinar el tráfico que atraviesa la red mediante NAT

# Instrucciones

## Parte 1: Examine la configuración para acceder a la red externa.

a.     Agregue 1 PC y conéctela al router inalámbrico con un cables directo. Espere a que todas las luces de enlace se vuelvan verdes antes de continuar con el siguiente paso o haga clic en **Fast Forward** (Adelantar).

b.     En la PC, haga clic en **Desktop** (Escritorio). Seleccione **IP Configuration**. Haga clic en **DHCP** a fin de habilitar cada dispositivo para que reciba una dirección IP mediante DHCP en el router inalámbrico.

c.     Anote la dirección IP de la puerta de enlace predeterminada. Cierre **IP Configuration** (Configuración IP) cuando termine.

d.     Desplácese al navegador web e introduzca la dirección IP de la puerta de enlace predeterminada en el campo URL. Cuando se le solicite , ingrese **admin** como el nombre de usuario y **admin** como la contraseña.

e.     Haga clic en la opción de menú **Status** (Estado) en la esquina superior derecha. Cuando se selecciona, muestra la página de submenús del router.

f.       Desplácese hacia abajo por la página del router hasta la opción de conexión a Internet. La dirección IP asignada aquí es la dirección asignada por el ISP. Si no hay una dirección IP (aparece 0.0.0.0), cierre la ventana, espere unos segundos e inténtelo nuevamente. El enrutador inalámbrico se encuentra en el proceso de obtener una dirección IP del servidor DHCP del ISP.

La dirección que se ve aquí es la dirección asignada al puerto de Internet en el enrutador inalámbrico.

#### Pregunta:

¿Es una dirección privada o una pública?

## Parte 2: Examine la configuración para acceder a la red interna.

a.     Haga clic en **Local Network** (Red local) dentro de la barra de submenús Status (Estado).

b.     Desplácese hacia abajo para analizar la información de la red local. Esta es la dirección asignada a la red interna.

c.     Desplácese aún más abajo para examinar la información del servidor DHCP y el rango de direcciones IP que se pueden asignar a los hosts conectados.

#### Pregunta:

¿Son direcciones privadas o públicas?

d.     Cierre la ventana de configuración del router inalámbrico.

## Parte 3: Conecte 3 PCs al router inalámbrico.

a.     Agregue 3 PCs mas y conéctelas al router inalámbrico con cables directos. Espere a que todas las luces de enlace se vuelvan verdes antes de continuar con el siguiente paso o haga clic en **Fast Forward** (Adelantar).

b.     En cada PC, haga clic en **Desktop** (Escritorio). Seleccione **IP Configuration**. Haga clic en **DHCP** a fin de habilitar cada dispositivo para que reciba una dirección IP mediante DHCP en el router inalámbrico. Cierre **IP Configuration** (Configuración IP) cuando termine.

c.     Haga clic en **Command Prompt** (Línea de comandos) para verificar la configuración IP de cada dispositivo con el comando **ipconfig /all**.

**Nota**: Estos dispositivos recibirán una dirección privada. Las direcciones privadas no pueden atravesar Internet; por lo tanto se debe realizar una traducción de NAT.

## Parte 4: Vea la traducción NAT a través del router inalámbrico.

a.     Haga clic en la ficha Simulación de la esquina inferior derecha para acceder al modo Simulación. La pestaña de Simulation (Simulación) se encuentra detrás de la ficha Realtime (Tiempo real) y tiene el símbolo de un cronómetro.

b.     Cree una PDU compleja en el modo Simulación para ver el tráfico:

1)     En el panel de simulación, haga clic en **Show All/None** (Mostrar todos/ninguno) para no ver ningún evento. Ahora haga clic en **Edit Filters** (Editar filtros) y en la ficha **Misc**, marque las casillas de **TCP** y **HTTP**. Cierre la ventana cuando haya terminado.

2)     Agregue una PDU Compleja haciendo clic en el sobre abierto ubicado en el menú superior.

3)     Haga clic en una de las PC para especificarla como origen.

c.     Especifique la configuración de la PDU compleja cambiando lo siguiente en la ventana de la PDU compleja:

1)     En **PDU Settings** (Configuración de PDU), Select Application (Seleccionar aplicación) debeser **HTTP**.

2)     Haga clic en el servidor **ciscolearn.nat.com** para especificarlo como dispositivo de destino.

3)     En Source Port (Puerto de origen), introduzca **1000**.

4)     En Simulation Settings (Configuración de simulación), seleccione **Periodic** (Periódica). Introduzca **120** segundos en Interval (Intervalo).

5)     Haga clic en **Create PDU** (Crear PDU) en la ventana Create Complex PDU (Crear PDU compleja).

d.     Haga doble clic en el panel de simulación para desbloquearlo de la ventana de PT. Esto le permite mover el panel de simulación para ver toda la topología de red.

e.     Observe el flujo de tráfico haciendo clic en **Play** (Reproducir) en el panel de simulación. Acelere la animación deslizando el control hacia la derecha.

**Nota**: Haga clic **en View Previous Event** (Ver evento anterior) cuando aparezca el mensaje Buffer Full (Búfer lleno).

## Parte 5: Vea la información del encabezado de los paquetes que atravesaron la red.

a.     Examine los encabezados de los paquetes enviados entre una PC y el servidor web.

1)     En el panel de simulación, haga doble clic en la tercera línea hacia abajo en la lista de eventos. Aparecerá un sobre en el área de trabajo que representa a esa línea.

2)     Haga clic en el sobre en la ventana del área de trabajo para ver la información del encabezado y el paquete.

b.     Haga clic en la ficha de detalles Inbound PDU (PDU entrante). Examine la información del paquete en busca de la dirección IP de origen (SRC) y la dirección IP de destino.

c.     Haga clic en la ficha de detalles Outbound PDU (PDU saliente). Examine la información del paquete en busca de la dirección IP de origen (SRC) y la dirección IP de destino.

Observe el cambio en la dirección IP SRC.

d.     Haga clic en otras líneas de eventos para ver los encabezados correspondientes a lo largo del proceso.

e.     Al finalizar, haga clic en Check Results (Verificar resultados) para verificar el trabajo.
