**Packet Tracer: Configurar un enrutador inalámbrico y clientes**

# Objetivos

Parte 1: Conectar los dispositivos

Parte 2: Configurar el enrutador inalámbrico

Parte 3: Configurar el direccionamiento IP y probar la conectividad

# Aspectos básicos/Situación

Su amiga, Natsumi, escuchó que usted está estudiando redes. Le pidió que viniera y la ayudara a conectar su nuevo hogar a la red de televisión por cable. Debe conectar los cables correctos a los dispositivos correctos, conectar los dispositivos a un router inalámbrico doméstico y configurar el router para proporcionar direcciones IP a los clientes de la red. Natsumi también desea que configure una LAN inalámbrica para su red doméstica, por lo que también deberá configurarla. Usted está seguro de que este será un proceso fácil y que la red se configurará en muy poco tiempo.

# Instrucciones

## Parte 1: Conectar los dispositivos.

El área de trabajo muestra el interior de la casa de su amigo. Desplácese por la ventana para tener una idea del diseño de la casa y la ubicación de los dispositivos. En esta parte, conectará todos los dispositivos etiquetados.

### Paso 1: Conectar los cables coaxiales

La empresa de cable de Natsumi ofrece servicios de Internet y video a su hogar a través de un cable coaxial. El cable está conectado a una salida en su casa. Un dispositivo divisor separa el servicio de datos de Internet del servicio de video. Esto permite que los dos servicios se conecten a los dispositivos correspondientes. Conectará el servicio de Internet al cable módem y el servicio de video al televisor.

a.     En Componentes de red, haga clic en **Connections** (Conexiones) (el rayo).

b.     Busque y haga clic en el icono del cable **Coaxial**. Es el icono azul en zigzag.

c.     Haga clic en **Cable Splitter** y seleccione el puerto **Coaxial1**.

d.     Haga clic en **Cable Modem** y seleccione **Port 0**.

e.     Repita los pasos anteriores para conectar el cable **Coaxial2** en el **Cable Splitter** al **Port 0** (puerto 0) del **TV**.

f.      Haga clic en **TV** y luego en **ON** para **Status** (Estado). Si las conexiones son correctas, verá una imagen que representa un programa de TV.

### Paso 2: Conectar los cables de red.

Hay dos PC en la casa de Natsumi. No tienen adaptadores LAN inalámbricos, por lo que se conectarán con cables Ethernet. El router inalámbrico doméstico es el centro de la red. Permite que los dispositivos configurados en la red doméstica se comuniquen entre sí y con Internet. El router incluye un switch de red que acepta conexiones cableadas para hasta cuatro hosts. Conectará las PC a estos puertos.

Para que el **Home Wireless Router** (router inalámbrico doméstico) acceda a Internet a través de la red del proveedor de televisión por cable, el cable módem debe estar conectado al puerto de Internet del router inalámbrico doméstico. Esto se hace con un cable directo de cobre.

a.     Haga clic en **Connections** (Conexiones) y después en el **Copper Straight-Through** (Cable de cobre directo). Parece una línea negra sólida.

b.     Conecte el **Port 1** (puerto 1) del **Cable Modem** (módem por cable) al puerto de **Internet** del **Home Wireless Router** (router inalámbrico doméstico).

c.     Haga clic en la **Office PC** (PC de oficina) y conecte el cable al puerto **FastEthernet0**. Busque el **Home Wireless Router** (router inalámbrico doméstico) y haga clic en él. Conecte el otro extremo del cable al puerto **GigabitEthernet 1** para completar la conexión.

d.     Repita los pasos anteriores para conectar la **Bedroom PC** (PC de dormitorio) al puerto **GigabitEthernet** **2** del **Home Wireless Router** (router inalámbrico doméstico).

La red doméstica cableada ahora está completamente conectada a Internet a través de la red del proveedor de televisión por cable.

## Parte 2: Configurar el router inalámbrico

La mayoría de los routers inalámbricos domésticos se configuran mediante una interfaz gráfica de usuario (GUI) a la que se accede a través del navegador web de la computadora. En esta parte, accederá al router inalámbrico doméstico a través del navegador en la **Office PC** (PC de oficina) y configurará la red doméstica de Natsumi.

### Paso 1: Acceder a la GUI del router inalámbrico doméstico.

a.     Haga clic en **Office PC** (PC de la oficina) > pestaña **Desktop** (Escritorio) y luego en **IP Configuration** (Configuración de IP).

b.     Haga click en **DHCP**. DHCP configurará automáticamente la **Office PC** (PC de oficina) para que esté en la misma red IP que el **Home Wireless Router** (router inalámbrico doméstico).

c.     Después de un breve retraso, los valores para la **IP Configuration** (configuración de IP) deben actualizarse automáticamente. La dirección IPv4 debe comenzar con el número 192. Si no es así, haga clic en **Fast Forward Time** (Tiempo de avance rápido), que se encuentra justo debajo de la topología de red en la esquina inferior izquierda. Esto acelerará la simulación de DHCP.

d.     Tome nota de la dirección de la puerta de enlace predeterminada. La puerta de enlace predeterminada es el dispositivo que proporciona a los dispositivos de la red doméstica acceso a redes externas, como Internet. En este caso, la dirección de la puerta de enlace predeterminada es la dirección del **Home Wireless Router** (enrutador inalámbrico doméstico).

e.     Manteniendo la ventana de la **Office PC** (PC de oficina) abierta, cierre la ventana de **IP Configuration** (configuración de IP) y luego haga clic en el **Web Browser** (navegador web). Ingrese la dirección IP del **Home Wireless Router** (router inalámbrico doméstico) (la dirección de la puerta de enlace predeterminada) en el cuadro **URL** y haga clic en **Go** (Ir).

f.      Los routers domésticos recién instalados se configuran con credenciales predeterminadas. Use **admin** tanto para el **User Name** (nombre de usuario) y la **Password** (contraseña). Ahora debería ver aparecer la GUI del **Home Wireless Router** (router inalámbrico doméstico) y estar listo para configurar la red de Natsumi. Ajuste el tamaño de la ventana, según sea necesario, para ver más de la interfaz.

**Nota**: Las contraseñas predeterminadas en dispositivos reales deben cambiarse inmediatamente porque es ampliamente conocido, incluyento a los agentes de amenaza.

### Paso 2: Configurar ajustes básicos.

En este paso, configurará un nuevo nombre de usuario y contraseña para el router inalámbrico y limitará la cantidad de direcciones IP que DHCP emitirá a hosts que estén conectadas a la red.

Natsumi solo tiene unos pocos dispositivos para conectar la red, y no tendrá muchos amigos. Ella piensa que no más de 10 dispositivos se conectarían a su red al mismo tiempo. Decide reducir el número de usuarios a 10. Su amiga vive en una parte densamente poblada de la ciudad, por lo que es posible que muchas personas puedan ver su red inalámbrica.

a.     Actualmente está viendo las opciones de configuración en la pestaña **Setup** (Configuración). Localice el área de **Network Setup** (Configuración de red). Aquí es donde puede configurar el servidor DHCP del router. Busque el campo **Maximum Number of Users** (Número máximo de usuarios) e introduzca **10**. Desplácese hasta la parte de abajo de la página y haga clic en **Save Settings** (Guardar configuración). Debe guardar la configuración en cada página de la GUI en la que realice cambios.

**Nota**: Es posible que pierda la conexión con el router. Haga clic en **Go** (Ir) en el navegador web para volver a cargar la página de la GUI. Es posible que deba cerrar el **Web Browser _(_**navegador web), hacer clic en **IP Configuration** (Configuración de IP) y alternar entre **DHCP** y **Static** (Estático) para actualizar el direccionamiento IP para **Office PC** (PC de oficina). Luego verifique que la **Office PC** (PC de oficina) tenga una configuración de dirección IP que comience con 192, abra el **Web Browser** (navegador web) nuevamente, ingrese la dirección IP del router y vuelva a autenticarse con **admin** como credenciales predeterminadas**.**

b.     Haga clic en la pestaña **Administration**. Aquí, puede cambiar la contraseña **admin** predeterminada. Ingrese y confirme **MyPassword1!** como la nueva contraseña. Desplácese hasta la parte inferior de la página y haga clic en **Save Settings** (Guardar configuración).

Se le pedirá que inicie sesión nuevamente. Ingrese **admin** como nombre de usuario y **MyPassword1!** como nueva contraseña y haga clic en **Continuar**.

### Paso 3: Configurar la LAN inalámbrica.

En este punto, está listo para configurar la red inalámbrica de Natsumi para que pueda conectar sus dispositivos inalámbricos a Internet a través de Wi-Fi.

a.     Desplácese hacia la parte superior de la ventana y haga clic en la pestaña **Wireless** (Inalámbrico).

b.     Para la red de **2,4 GHz**, haga clic en **Enable** (Habilitar) para activar la radio de red.

c.     Cambie el **Network Name** (nombre de la red**) (SSID)** de **Default** a **MyHome**. Cuando las personas buscan redes Wi-Fi para conectarse, verán este nombre de red. El nombre de la red puede estar oculto, pero esto puede dificultar un poco la conexión de los invitados a la red. Desplácese hasta la parte inferior de la página y haga clic en **Save Settings** (Guardar configuración).

d.     Ahora configurará la seguridad en la red **MyHome**. Esto evitará que personas no autorizadas se conecten a la red inalámbrica. Desplácese hasta la parte superior de la ventana y luego haga clic en **Wireless Security** (Seguridad inalámbrica) en la pestaña **Wireless** (Inalámbrico).

e.     Tenga en cuenta que la seguridad está actualmente deshabilitada en las tres redes inalámbricas. Solo utiliza la red de **2,4 GHz**. Haga clic en el menú desplegable de la red de **2,4 GHz** y seleccione **WPA2 Personal**. Esta es la seguridad más sólida que ofrece este router para redes inalámbricas.

f.      Se revelan más configuraciones. WPA2 Personal requiere una frase de contraseña que debe introducir cualquier persona que desee conectarse a la red inalámbrica. Ingrese **MyPassPhrase1!** como la **Passphrase** (frase de contraseña). Tenga en cuenta que las mayúsculas son importantes.

g.     Desplácese hasta la parte inferior de la página, haga clic en **Save Settings** (Guardar configuración) y cierre **Web Browser** (el navegador web) de la Office PC (PC de oficina).

## Parte 3: Configurar el direccionamiento IP y probar la conectividad

Ahora que el router está configurado, en esta parte configurará el direccionamiento IP para las PC y las computadoras portátiles y verificará que se puedan conectar a Internet.

### Paso 1: Conecte la computadora portátil a la red inalámbrica.

a.     Haga clic en la **Laptop** (computadora portátil) en la sala de estar y luego en la pestaña **Desktop** (Escritorio) > **PC Wireless** (PC inalámbrica).

b.     Haga clic en la pestaña **Connect** (Conectar). Después de un breve retraso, la red inalámbrica que configuró anteriormente aparecerá en la lista de nombres de redes inalámbricas.

c.     Haga clic en el nombre de la red que creó y luego en el botón **Connect** (Conectar).

d.     Ingrese la frase de contraseña que configuró antes para la red inalámbrica en el campo **Pre-shared Key** (Clave precompartida) y haga clic en **Connect** (Conectar).

e.     Haga clic en la pestaña de **Link Information** (Información de enlace). Debería ver el mensaje **You have successfully connected to the access point** (Se ha conectado correctamente al punto de acceso).

f.      Haga clic en el botón **More Information** (Más Información) para ver detalles sobre la conexión. Si la dirección IP no comienza con **192**, haga clic en **Fast Forward Time** varias veces para acelerar la simulación.

g.     Cierre la aplicación **PC Wireless** y abra el **Web Browser** (navegador web). Verifique que la **Laptop (**computadora portátil) ahora pueda conectarse a **skillsforall.srv**, haciendo clic en **Fast Forward Time** (Tiempo de avance rápido) hasta que se cargue la página. Esto verifica que la **Laptop** (computadora portátil) tenga conectividad a Internet.

### Paso 2: Pruebe la conectividad desde la PC de oficina.

Usted sabe que la PC de Office puede conectarse a la red porque la utilizó para configurar el router. Sin embargo, ¿también puede acceder a Internet? Si puede, sabrá que la red cableada está correctamente conectada y configurada.

a.     Haga clic en **Office PC** (PC de oficina) > pestaña **Desktop** (Escritorio) > **Web Browser** (Navegador web).

b.     Ingrese **skillsforall.srv** y haga clic en **Go** (Ir). Después de un breve retraso, verá aparecer la página web. Si es necesario, haga clic en **Fast Forward Time** (Tiempo de avance rápido) varias veces para acelerar la convergencia.

Cargar un sitio web externo verifica que la conectividad a Internet para la **Office PC** (PC de oficina).

### Paso 3: Configurar la PC de dormitorio.

a.     Para la **Bedroom PC** (PC de dormitorio), abra **IP Configuration** (Configuración IP) y configúrela como **DHCP**. Verifique que la PC del dormitorio recibió una dirección IP que comienza con **192**.

b.     Cierre la ventana **IP Configuration** (Configuración IP) y haga clic en **Web Browser** (Navegador web). Verifique que la **Bedroom PC** (PC del dormitorio) ahora pueda conectarse a **skillsforall.srv**, haciendo clic en **Fast Forward Time** (Tiempo de avance rápido) hasta que se cargue la página. Esto verifica que la **Bedroom PC** (PC del dormitorio) tenga conectividad a Internet.

Ha completado la conexión de dispositivos de red, la configuración del router y la LAN inalámbrica, y la configuración de hosts para conectarse a la red. Todos los dispositivos deben poder conectarse a Internet. Su trabajo está hecho y Natsumi se ha ofrecido a prepararle la cena como recompensa por su ayuda.
