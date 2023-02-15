**Packet Tracer: La interacción con los clientes**

# Objetivos

Observar la interacción de los clientes entre el servidor y la PC.

# Aspectos básicos/situación

Los clientes, como las PC de escritorio, solicitan servicios a los servidores. El entorno de laboratorio, que usa PC y servidores físicos, admite una gama completa de servicios. En un ambiente simulado, la cantidad de servicios es limitada. Packet Tracer permite agregar servidores de red simulados que soportan DHCP, DNS, HTTP y TFTP. Packet Tracer también soporta la adición de PC simuladas que pueden solicitar dichos servicios. Esta actividad usa una red simple que consiste en una PC conectada directamente a un servidor configurado para prestar servicios de DNS, además de alojar una página web mediante un servidor HTTP. Esta actividad rastreará el flujo de tráfico que se produce cuando se solicita una página web, cómo se resuelve la dirección IP de la página web y cómo se entrega esta.

# Instrucciones

## Parte 1: Ingrese al modo de simulación.

Cuando se inicia el Packet Tracer, éste presenta una vista lógica de la red en el modo de tiempo real.

Haga clic en **Simulation Mode** para ingresar al modo de simulación. El icono del modo de simulación se encuentra en la parte inferior derecha del área de trabajo lógico.

## Parte 2: Establezca filtros para la lista de eventos.

En el modo de simulación, la opción predeterminada es capturar todos los eventos. Usará filtros para capturar solamente eventos DNS y HTTP.

a.     En la sección **Event List Filters** (Filtros de la lista de eventos), haga clic en **Show All/None** (Mostrar todos/ninguno) para borrar todas las marcas.

b.     Haga clic en **Edit Filters** (Editar filtros). En la ficha IPv4, seleccione **DNS**. En la ficha Misc, seleccione **HTTP**. Cierre la ventana cuando haya terminado. **Event List Filters** muestra DNS y HTTP como los únicos eventos visibles.

## Parte 3: Solicite una página web desde la PC.

Abrirá un navegador web simulado en la PC y solicitará una página web al servidor.

a.     Haga clic en **PC**. Haga clic en la ficha **Desktop** (Escritorio) y en **Web Browser** (Navegador web).

b.     Se abrirá un navegador web simulado. Escriba **www.ejemplo.com** en el cuadro de la URL y haga clic en el botón **Go** (Ir) a la derecha. Minimice la ventana de la PC.

## Parte 4: Ejecute la simulación.

a.     En la sección **Play Controls** (Controles de reproducción) del **Simulation Panel** (Panel de simulación), haga clicen **Play** (Reproducir). Se anima el intercambio entre la PC y el servidor, y se agregan eventos a **Event List** (Lista de eventos).

Estos eventos representan la solicitud de la PC de resolver la URL en una dirección IP, el suministro del servidor de la dirección IP, la solicitud de la página web por parte de la PC, el envío de la página web por parte del servidor en dos segmentos y la confirmación de la PC de que recibió la página web.

b.     Haga clic en **View Previous Event** (Ver evento anterior) para continuar cuando el búfer esté lleno.

## Parte 5: Acceda a una PDU específica.

a.     Restaure la ventana de la PC simulada. Observe que se muestra una página web en el navegador web. Minimice la ventana de navegador simulado.

b.     En la sección **Simulation Panel Event List** (Lista de eventos del panel de simulación), la última columna contiene un cuadro coloreado que brinda acceso a información detallada sobre un evento. Haga clic en el cuadro coloreado en la primera fila del primer evento. Se abre la ventana **PDU Information** (Información de la PDU).

## Parte 6: Examine el contenido de la ventana PDU Information (Información de la PDU).

La primera ficha en la ventana PDU Information (Información de PDU) contiene información sobre la PDU entrante y/o saliente en relación con el modelo OSI. Haga clic en **Next Layer >>** (Próxima capa) varias veces para recorrer las capas entrantes y salientes, y lea la descripción del cuadro debajo de las capas para obtener una descripción general de cómo funciona el intercambio.

Examine la información de PDU de los otros eventos para obtener una descripción general de todo el proceso de intercambio.
