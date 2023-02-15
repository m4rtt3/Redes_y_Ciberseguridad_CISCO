Esta actividad tutorizada de Packet Tracer (PTTA) tiene características que proporcionan sugerencias durante toda la actividad, en el nivel que especifique. Puede practicar sus habilidades de solución de problemas con la mínima o tanta orientación como necesite.

En esta actividad de Packet Tracer, cumplirá los siguientes objetivos:

Parte 1: Investigar la Barra de Herramientas Inferior
Parte 2: Investigar Dispositivos en un Armario de Cableado
Parte 3: Conectar Dispositivos Finales a Dispositivos de Red
Parte 4: Instalar un Router de Respaldo
Parte 5: Configurar un Nombre de Host
Parte 6: Explora el resto de la Red

---

# Objetivos
- Investigar Dispositivos en un Armario de Cableado
- Conectar Dispositivos Finales a Dispositivos de Red
- Instalar un Router de Respaldo
- Configuración de un Nombre de Host

# Trasfondo/Situación
El modelo de red de esta Actividad supervisada de Packet Tracer (PTTA) incorpora muchas de las tecnologías que puede dominar en los cursos de Cisco Networking Academy. Y representa una versión simplificada de la forma en que podría verse una red de pequeña o mediana empresa.

La mayoría de los dispositivos de la sucursal del Seward Branch Office (arriba a la izquierda) y Warrenton (abajo a la derecha) Centro de Datos ya están implementados y configurados. Acaban de ser contratados para revisar los dispositivos y redes implementados. No es importante que comprenda todo lo que vea y haga en esta actividad. Siéntase libre de explorar la red por usted mismo. Las sugerencias también aparecerán después de cierto tiempo. Puede seleccionar un nivel de sugerencia con la barra deslizante situada en la esquina inferior izquierda.

Nota: Hay dos formas de ver una red en Packet Tracer. El modológico muestra cómo se conectan los dispositivos en la red. El modo físico le muestra dónde se encuentran los dispositivos en la red. Esta actividad se abre y se centra en el modo Físico. Muchas de las actividades de Packet Tracer que encuentre en los cursos de Cisco Networking Academy utilizarán el modo Lógico . Puede cambiar entre estos modos en cualquier momento para comparar las diferencias haciendo clic en los botones Logical (Shift+L) y Physical (Shift+P). Sin embargo, en otras actividades de este curso puede estar bloqueado de un modo u otro

---

Haga clic en las ubicaciones para explorar la red. Familiarícese con las representaciones de red en los modos Lógico y Físico . En el modo Físico, vaya a otras áreas, como el Warrenton Data Center Centro Teleworker Homede Datos deWellington y el hogar de Teleworker. Las tecnologías utilizadas en estos lugares se analizan con mayor detalle en los cursos de Cisco Networking Academy.
La mayoría de los
dispositivos de la sucursal Seward de Seward y del Warrenton Centro de Datos de Warrenton ya están implementados y configurados. Puede explorar los dispositivos y las redes. No es importante que comprenda todo lo que vea y haga en esta actividad. Siéntase libre de explorar la red por usted mismo. Las sugerencias también aparecerán después de cierto tiempo. Puede seleccionar un nivel de sugerencia con la barra deslizante situada en la esquina inferior izquierda. Responda las preguntas lo mejor que pueda.

Puede cambiar entre estos modos en cualquier momento para comparar las diferencias haciendo clic en los botones Logical (Shift+L) y Physical (Shift+P).

Por ahora, vea lo que puede descubrir por su cuenta. No se preocupe por romper nada. Siempre puede cerrar Packet Tracer y abrir una copia nueva para empezar a explorar de nuevo.

---

Se ha conectado Laptop_1 a Backup_Router través de un cable de consola USB. Con la consola USB conectada, accederá a la interfaz de línea de comandos (CLI) de Backup_Router mediante el software de terminal y configurará un nombre de host.

Todas las computadoras requieren un sistema operativo para funcionar, incluso los dispositivos de red basados en PC, como switches, routers, puntos de acceso y firewalls. Un sistema operativo de red habilita el hardware del dispositivo que funcione y proporciona una interfaz para que los usuarios interactúen.

El Cisco Internetwork Operating System (IOS) es un sistema operativo que se utiliza en los dispositivos de red de Cisco. Permite la creación de configuraciones que personalizan el funcionamiento de los dispositivos de red en diferentes entornos de red. Se puede acceder a la CLI a través del puerto de la consola del dispositivo mediante el software de terminal o de forma remota mediante Secure Shell (SSH) Los administradores de red utilizan una computadora para acceder a la consola del dispositivo con el fin de crear o modificar la configuración del dispositivo.

Los administradores de red suelen asignar un nombre a los dispositivos de red. El nombre de host se usa para identificar un dispositivo cuando se accede a su sistema operativo para la configuración. Para hacer esto, utilizará la conexión de consola al Backup_Router. Una vez configurado el nombre de host, el nombre de host aparece como parte del símbolo del sistema IOS.

En este paso, configurará el nombre de host en Backup_Router.

1. En Laptop_1, acceda a la pestaña Desktop (Escritorio) y haga clic en Terminal. La configuración del Terminal ya está definida con la configuración de puerto necesaria y debe usarse con su configuración predeterminada. Haga clic en OK para iniciar la conexión de terminales.

2. Ahora está en la línea de comandos para Backup_Router y debería ver la siguiente salida del enrutador.

```cisco
[output omitted]
cisco ISR4331/K9 (1RU) processor with 1795999K/6147K bytes of memory.
Processor board ID FLM232010G0
3 Gigabit Ethernet interfaces
2 Serial interfaces
32768K bytes of non-volatile configuration memory.
4194304K bytes of physical memory.
3207167K bytes of flash memory at bootflash:.
0K bytes of WebUI ODM Files at webui:.
```

Responda no a la pregunta y luego presione ENTER para obtener el Router> command prompt.

```cisco
         --- System Configuration Dialog ---
Would you like to enter the initial configuration dialog? [yes/no]: no
```
                
3. Siguientes comandos para nombrar al router Edge_Router_Backup. Tenga en cuenta que el nombre de host debe coincidir exactamente con este valor.

```cisco
Router> enable
Router# configure terminal
Router(config)# hostname Edge_Router_Backup
Edge_Router_Backup(config)# end
```

