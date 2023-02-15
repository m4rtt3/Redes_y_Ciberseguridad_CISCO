**Packet Tracer: observe el flujo de tráfico en una red enrutada**

# Objetivos

Parte 1: Observar el flujo de tráfico en una LAN no enrutada

Parte 2: Reconfigurar la red para enrutar entre las LAN

Parte 3: Observar el flujo de tráfico en la red enrutada

# Aspectos básicos/Situación

Se le ha pedido a la empresa para la que trabaja que proponga un nuevo diseño de red para XYZ LLC. XYZ es una empresa nueva que recientemente ha tenido éxito con sus ofertas de productos. Se expandirán y su red deberá crecer con ellos. Actualmente, la red está configurada con una única red IP para hosts en todos los departamentos. Este diseño se ha vuelto ineficiente y las demoras en la red son cada vez más notorias. Se le ha pedido que ayude a preparar la propuesta con el equipo de ventas. El equipo de ventas propondrá una solución en la que se mejorará la eficiencia de la red mediante la implementación de enrutamiento entre redes de departamentos separadas. Está trabajando en una demostración de cómo tener varias redes enrutadas en una empresa puede mejorar la eficiencia de la red. Siga las instrucciones para realizar la demostración y proponer una nueva red a XYZ LLC.

# Instrucciones

## Parte 1: Observar el flujo de tráfico en una LAN no enrutada

La red XYZ consta de aproximadamente 150 dispositivos que están conectados a una LAN. La LAN está configurada en una sola red IPv4. Los hosts en diferentes departamentos se conectan a switches que luego se conectan al router **Edge**. El router solo enruta el tráfico entre la LAN e Internet, representado por la nube del **ISP**. Dado que solo se utiliza una red IP en la LAN, todos los departamentos están en la misma red.

La topología de Packet Tracer está simplificada. Solo muestra algunos de los departamentos y hosts. Suponga que el comportamiento que demostrará sucede a una escala mucho mayor que la que se muestra en la red de PT.

En esta parte, utilizará el modo de simulación de Packet Tracer para observar cómo fluye el tráfico a través de una LAN no enrutada.

### Paso 1: Borre la caché de ARP en el host de Sales 1.

Pase el mouse sobre el host de **Sales 1** para ver su dirección IP. Anótelo.

a.     Haga clic en **Sales 1**> pestaña **Desktop** (Escritorio)> **Símbolo del sistema** y escriba el comando **arp -a**. No debe haber direcciones MAC en la caché de ARP. Si hay entradas en la caché de ARP, utilice el comando **arp -d** para eliminarlas.

### Paso 2: Observe el flujo de tráfico en la red.

a.     Haga clic en el botón **Modo de simulación** en la esquina inferior derecha de la ventana del PT para pasar del modo **tiempo real** al de **simulación**.

b.     Abra el **símbolo del sistema** para **Sales 2** e introduzca el comando **ping** seguido de la dirección IP de **Sales 1**.

c.     Utilice el botón **Capture then Forward** (Capturar y Avanzar) (el triángulo que apunta hacia la derecha con una barra vertical adjunta) en los **controles de reproducción** del **panel de simulación** para comenzar a ejecutar el comando **ping**. Verá un icono de sobre de color junto a Ventas 2. Esto representa una PDU. Haga clic en el botón **Capture then Forward** para mover la PDU al primer dispositivo en su ruta al dispositivo de destino. Haga clic en el sobre de la PDU para inspeccionar el contenido.

#### Preguntas:

¿Cuáles son las direcciones IP y MAC de origen y destino para la trama y el paquete?
IP origen: 0060.70EC.83C3
IP destino: FFFF.FFFF.FFFF
MAC origen: 192.168.1.5
MAC destino: 192.168.1.2

¿Por qué la dirección MAC de destino es la dirección de difusión?
Porque Sales 1 conoce la IP, pero no conoce la dirección MAC, entonces primero realiza un ARP request  a través de una difusión.

d.     Avance las PDU a través de la red hasta que se cree una nueva PDU (color diferente) en **Sales 2**.

#### Preguntas:

¿Qué hosts y otros tipos de dispositivos necesitaban procesar los paquetes de solicitud de ARP?
Todos los hosts en la misma red local, switches y router.

¿Cuál es el impacto de esto en el funcionamiento eficiente de la red como está configurada actualmente?
Hay demasiados clientes en la red que deben procesar una solicitud ARP, congestionando la red al no estar segmentada.

e.     En Sales 2, apareció una nueva PDU con un color diferente. Haga clic en la nueva PDU e inspeccione su contenido. Mire los detalles de la PDU de salida.

#### Pregunta:

¿Qué tipo de PDU es esta?
Respuesta ARP.

f.       Vuelva al modo **Realtime**.

## Parte 2: Reconfigurar la red para enrutar entre las LAN.

En esta parte, demostrará los beneficios del enrutamiento entre redes de departamentos. Primero, cableará cada switch de red para conectarse directamente a una interfaz de router. Luego, reconfigurará los hosts para recibir direcciones en dos redes IPv4 nuevas creadas por el router.

### Paso 1: Cambie las conexiones de los dispositivos.

Los tres switches están conectados entre sí con cables directos de cobre.

a.     Para el cable que conecta el switch de **contabilidad** con el switch de **finanzas**, haga clic en el triángulo verde en el lado del enlace del switch de **contabilidad**.

b.     Arrastre el extremo del cable al router **Edge** y conéctelo al puerto **GigabitEthernet 1/0**.

c.     Repita este paso para el enlace entre **finanzas** y **ventas**. Conéctese al puerto GigabitEthernet disponible.

### Paso 2: Configure los hosts con direcciones en las nuevas LAN.

Cada interfaz del router **Edge** se configuró previamente para poner a cada departamento en su propia red IPv4. Los hosts recibirán sus nuevas direcciones IP del router. Sin embargo, llevará tiempo para que los hosts en las redes de **finanzas** y **ventas** reciban sus nuevas direcciones IP. (Los hosts en la red de contabilidad permanecerán en 192.168.1.0/24).

a.     Para acelerar el proceso de obtención de nuevas direcciones IP, abra un **símbolo del sistema** en cada uno de los cuatro dispositivos en las redes de **finanzas** y **ventas**.

b.     Ingrese el comando **ipconfig /renew** . Esto obligará al host a solicitar una nueva dirección IP del servidor DHCP que corre en el router **Edge** . Debería ver la confirmación del nuevo direccionamiento IP.

¿Qué red IPv4 se asigna a la red de **finanzas** y en **ventas**?
Ambos departamentos siguen en la red 192.168.1.0/24

## Parte 3: Observar el flujo de tráfico en la red enrutada.

En esta parte, observará cómo el tráfico ahora fluye a través de una red enrutada.

### Paso 1: Haga ping a Sales 1 de Sales 2.

a.     Vuelva al **símbolo del sistema** de **Sales 2** y verifique que su caché ARP esté vacía. Si no es así, elimine las entradas.

b.     Cambie a modo de **simulación**.

c.     Haga ping a **Sales 1** de **Sales 2**.

d.     Utilice el botón **Capture then Forward** para pasar las PDU por la red. Observe cómo el mensaje de solicitud ARP fluye a través de la red esta vez.

#### Pregunta:

¿Qué dispositivos reciben las transmisiones ARP esta vez?
Solamente los clientes en la red del departamento de ventas.

### Paso 2: Haga ping a otros hosts.

Repita esta demostración haciendo ping a otros hosts y al servidor de Internet. Observe el flujo de las PDU de solicitud de ARP.

**Nota**: La topología de red que se usa en la actividad es solo para fines de demostración. Si bien es posible que una red empresarial real pueda utilizar un router de esta manera, existen topologías más óptimas que logran estos resultados. Aprenderá sobre otros enfoques de diseño en cursos de redes posteriores.
