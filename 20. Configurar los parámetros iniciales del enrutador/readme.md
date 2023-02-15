**Packet Tracer: Configuración inicial del enrutador**

# Objetivos

Parte 1: Verificar la configuración predeterminada del enrutador

Parte 2: Configurar y verificar la configuración inicial del enrutador

Parte 3: Guardar el archivo de configuración en ejecución

# Aspectos básicos

En esta actividad, realizará tareas básicas de configuración del enrutador. Asegurará el acceso a la CLI y al puerto de la consola utilizando contraseñas encriptadas y de texto sin formato. También configurará mensajes para los usuarios que inician sesión en el enrutador. Estos avisos advierten a los usuarios no autorizados que el acceso está prohibido. Por último, verificará y guardará la configuración en ejecución.

# Instrucciones

## Parte 1: Verifique la configuración predeterminada del enrutador

### Paso 1: Establezca una conexión de consola al R1.

a.     Elija un cable de **Console** (consola) de las conexiones disponibles.

b.     Haga clic en **PCA** y seleccione **RS 232**.

c.     Haga clic en **R1** y seleccione **Console**.

d.     Haga clic en **PCA** > ficha **Desktop** > **Terminal**.

e.     Haga clic en **OK** y presione **ENTER**. Ahora puede configurar **R1**.

### Paso 2: Ingrese al modo con privilegios y examinar la configuración actual.

Puede acceder a todos los comandos del enrutador en el modo EXEC privilegiado. Sin embargo, debido a que muchos de los comandos privilegiados configuran parámetros operativos, el acceso privilegiado se debe proteger con contraseña para evitar el uso no autorizado.

a.     Ingrese al modo EXEC privilegiado introduciendo el comando **enable**.

Abra una ventana de configuración

Router> **enable**

Router#

Observe que la petición de entrada cambia en la configuración para reflejar el modo EXEC con privilegios.

b.     Ingrese el comando **show running-config**.

Router# **show running-config**

#### Preguntas:
¿Cuál es el nombre de host del enrutador?
>Router

¿Cuántas interfaces Fast Ethernet tiene el enrutador?
>Ninguna

¿Cuántas interfaces Gigabit Ethernet tiene el enrutador?
>2

¿Cuántas interfaces seriales tiene el enrutador?
>2

¿Cuál es el rango de valores que se muestra para las líneas vty?
>0-4

c.     Muestre el contenido actual de la NVRAM.

```red
Router# **show startup-config**
startup-config is not present
```

#### Pregunta:

¿Por qué el enrutador responde con el mensaje **startup-config is not present**?
>Porque el archivo de configuración del switch no se guardó en la NVRAM. Actualmente solo se encuentra en la RAM.

Cierre la ventana de configuración

## Parte 2: Configure y verifique la configuración inicial del enrutador

Para configurar los parámetros de un enrutador, quizá deba pasar por diversos modos de configuración. Observe cómo cambia la solicitud a medida que navega por los modos de configuración de IOS.

### Paso 1: Configure los parámetros iniciales del R1.

**Nota**: Si tiene dificultades para recordar los comandos, consulte el contenido de este tema.

Abra una ventana de configuración

a.     Configure **R1** como el nombre del enrutador (hostname).

b.     Configure el mensaje de texto del día: **Unauthorized access is strictly prohibited.**

c.     Encripte todas las contraseñas de texto no cifrado.

Utilice las siguientes contraseñas:

1)    EXEC privilegiado, encriptado: **itsasecret**

2)    Consola: **letmein**

### Paso 2: Verifique los parámetros iniciales del R1.

a.     Para verificar los parámetros iniciales, observe la configuración del R1.

#### Pregunta:

¿Qué comando utiliza?
>`show running-config`

b.     Salga de la sesión de consola actual hasta que vea el siguiente mensaje:

`R1 con0 is now available`
`Press RETURN to get started.`

c.     Presione **ENTER**; debería ver el siguiente mensaje:

```cisco
Unauthorized access is strictly prohibited.
User Access Verification
Password:
```

#### Preguntas:

¿Por qué todos los enrutadors deben tener un mensaje del día (MOTD)?
>Cada enrutador debe tener un mendaje para advertir a los usuarios no autorizados que el acceso está prohibido. Los mensajes MOTD también se pueden utilizar para enviar mensajes al personal de la red (como por ejemplo apagados inminentes del sistema o a quién contactar para acceder).

Si no se le solicita una contraseña antes de llegar al indicador EXEC del usuario, ¿qué comando de línea de consola olvidó configurar?
>R1(config-line)# login

d.     Introduzca las contraseñas necesarias para regresar al modo EXEC con privilegios.

#### Preguntas:

Si configura más contraseñas en el enrutador, ¿se muestran como texto no cifrado o en forma cifrada en el archivo de configuración? Explique.
>El comando service password-encryption encriptará todas las contraseñas actuales y futuras.

Cierre la ventana de configuración

## Parte 3: Guarde el archivo de configuración en ejecución

### Paso 1: Guarde el archivo de configuración en la NVRAM.

Abra una ventana de configuración

a.     Ha configurado la configuración inicial para **R1**. Ahora haga una copia de respaldo del archivo de configuración en ejecución en la NVRAM para garantizar que no se pierdan los cambios realizados si el sistema se reinicia o se apaga.

#### Preguntas:

¿Qué comando introdujo para guardar la configuración en la NVRAM?
>`copy running-config startup-config`

¿Cuál es la versión más corta e inequívoca de este comando?
>`cop r st`

¿Qué comando muestra el contenido de la NVRAM?
>`show startup-configuration` o `show start`

b.     Verifique que todos los parámetros configurados estén registrados. De lo contrario, analice el resultado y determine qué comandos no se ejecutaron o se ingresaron incorrectamente. También puede hacer clic en **Check Results** en la ventana de instrucción.

### Paso 2: Opcional: Guarde el archivo de configuración de inicio en flash.

Si bien aprenderá más sobre cómo administrar el almacenamiento flash en un enrutador en capítulos posteriores, es posible que le interese saber que, como procedimiento de respaldo adicional, puede guardar su archivo de configuración de inicio en flash. De manera predeterminada, el enrutador seguirá cargando la configuración de inicio desde la NVRAM, pero si esta se daña, puede restablecer la configuración de inicio copiándola de la memoria flash.

Complete los siguientes pasos para guardar la configuración de inicio en la memoria flash.

a.     Examine el contenido de la memoria flash mediante el comando **show flash**:

R1# **show flash**

#### Preguntas:

¿Cuántos archivos hay almacenados actualmente en la memoria flash?
>3

¿Cuál de estos archivos cree que es la imagen de IOS?
>ISR4300-universalK9.03.16.05.S.155-3.s5-ext.spa.bin

¿Por qué cree que este archivo es la imagen de IOS?
>la longitud del archivo en comparación con otros y la extensión .bin al final del nombre de archivo.

b.     Utilice los siguientes comandos para guardar el archivo de configuración de inicio en la memoria flash:

```cisco
R1# **copy startup-config flash**
Destination filename [startup-config]
```

El enrutador le solicita almacenar el archivo en flash utilizando el nombre entre paréntesis. Si la respuesta es afirmativa, presione **ENTER**; de lo contrario, escriba un nombre adecuado y presione la tecla **ENTER**.

c.     Utilice el comando **show flash** para verificar que el archivo de configuración de inicio esté guardado en la memoria flash.
