Packet Tracer: Observar las solicitudes web

# Objetivos

Ver el tráfico cliente y servidor enviado desde una PC a un servidor Web al solicitar servicios Web

# Instrucciones

## Parte 1: Verificar la conectividad al servidor Web.

a.     Haga clic en External Client (Cliente externo) y acceda a **Command Prompt** (Línea de comandos) desde la ficha  **Desktop**  (Escritorio).

b.     Use el comando **ping** para comunicarse con la URL **ciscolearn.web.com**.

PC> **ping ciscolearn.web.com**

Observe la dirección IP que aparece en el resultado del ping. Esta dirección se obtiene del servidor DNS y se resuelve como el nombre de dominio ciscolearn.web.com. Todo el tráfico reenviado a través de una red usar información de dirección IP de origen y destino.

c.     Cierre la ventana de la línea de comandos pero deje la ventana del escritorio del cliente externo abierta.

## Parte 2: Conéctese con el servidor web.

a.     En la ventana del escritorio acceda al **Web Browser** (Explorador Web).

b.     En el cuadro de la URL escriba **ciscolearn.web.com**.

Asegúrese de leer la página Web que se muestra. Deje esta página abierta.

c.     Minimice la ventana del cliente externo, pero no la cierre.

## Parte 3: Vea el código HTML.

a.     Desde la topología lógica, haga clic en el servidor **ciscolearn.web.com**.

b.     Haga clic en la ficha **Services** (Servicios) > **HTTP**. Luego, junto al archivo **index.html**, haga clic en **(edit)** (editar).

c.     Compare el código de marcado HTML en el servidor que crea la página de visualización del navegador web en el cliente externo. Puede ser necesario volver a maximizar la ventana del cliente si se minimizó al abrir la ventana del servidor.

d.     Cierre la ventana del cliente externo y la del servidor Web.

## Parte 4: Observe el tráfico entre el cliente y el servidor Web.

a.     Haga clic en la ficha Simulación de la esquina inferior derecha para acceder al modo **Simulation** (Simulación).

b.     Haga doble clic en el Panel de simulación para desacoplarlo de la ventana de PT. Esto le permite mover el Panel de simulación para ver toda la topología de la red.

c.     Cree una PDU compleja en el modo Simulación para ver el tráfico.

1)     En el **Simulation Panel** (Panel de simulación), seleccione **Edit Filters** (Editar filtros).

2)     Haga clic en la ficha Misc para verificar que solo estén marcadas las casillas TCP y HTTP.

3)     Haga clic en el sobre abierto que está sobre el ícono del modo de simulación para agregar una PDU compleja.

4)     Haga clic en **External Client** (Cliente externo) para especificarlo como origen. Se abre la ventana **Create Complex PDU** (Crear PDU compleja).

d.     Especifique la configuración de **Create Complex PDU** cambiando lo siguiente en la ventana de la PDU compleja:

1)     En PDU Settings (Configuración de PDU), Select Application (Seleccionar aplicación) debe ser **HTTP**.

2)     Haga clic en el servidor **ciscolearn.web.com** para configurarlo como dispositivo de destino. Observe que aparecerá la dirección IP del servidor web en el cuadro de destino dentro de la ventana de la PDU compleja.

3)     En Starting Source Port (Puerto de origen inicial), introduzca **1000**.

4)     En Simulation Settings (Configuración de la simulación), seleccione Periodic Interval (Intervalo periódico) y escriba **120**.

e.     Cree la PDU, haga clic en la casilla **Create PDU** de la ventana **Create Complex PDU**.

1)     Observe el flujo de tráfico haciendo clic en **Play** (Reproducir) en el panel de simulación. Para acelerar la animación utilice el control deslizante de reproducción.

Cuando aparezca la ventana Buffer Full (Búfer lleno), haga clic en el botón **View Previous Events** (Ver eventos anteriores).

2)     Desplácese por la lista de eventos. Observe la cantidad de paquetes que viajaron desde el origen hacia el destino. HTTP es un protocolo TCP, por lo que requiere que se establezca una conexión y se acuse recibo de los paquetes. Esto aumenta considerablemente la cantidad de tráfico.
