Packet Tracer: Utilizar Servicios FTP

# Tabla de direccionamiento

Dispositivo

Interfaz

Dirección IP

Máscara de subred

Servidor FTP (ftp.pka)

NIC

209.165.200.226

255.255.255.224

# Objetivos

=    Cargar un archivo al servidor FTP

=    Descargar un archivo desde el servidor FTP

# Aspectos básicos/Situación

El Protocolo de transferencia de archivos (FTP) es una aplicación comúnmente utilizada para transferir archivos entre clientes y servidores en la red. El servidor está configurado para ejecutar el servicio donde los clientes se conectan, inician sesión y transfieren archivos. FTP utiliza el puerto 21 como puerto de comando del servidor para crear la conexión. A continuación, FTP utiliza el puerto 20 para la transferencia de datos.

En esta actividad, cargará un archivo a un servidor FTP. También descargará un archivo desde un servidor FTP.

# Instrucciones

## Parte 1: Cargar un archivo al servidor FTP

En esta parte, encontrará el archivo **sampleFile.txt** y lo cargará en un servidor FTP.

### Paso 1: Ubique el archivo.

a.     Haga click en **PC-A**.

b.     Haga click en **Desktop** (Escritorio).

c.     Haga clic en **Command Prompt** (Símbolo del sistema).

d.     En el indicador, haga clic en **?** para listar los comandos disponibles.

e.     Ingrese **dir** para ver los archivos en la PC. Observe que hay un archivo **sampleFile.txt** en el directorio C:\

```powershell
C:\> **dir**
Volume in drive C has no label.
Volume Serial Number is 5E12-4AF3
Directory of C:\
12/31/1969 17:0 PM 26 sampleFile.txt
26 bytes 1 File (s)
```

### Paso 2: Conectarse al servidor FTP.

a.     FTP al servidor FTP en **209.165.200.226** o **ftp.pka**.

```powershell
C:\> **ftp 209.165.200.226**
Trying to connect...209.165.200.226
Connected to 209.165.200.226
```

b.     Ingrese el nombre de usuario **student** y la contraseña **class** para obtener acceso.

```powershell
220- Welcome to PT Ftp Server
Username:**student**
331- Username ok, need password
Password:
230- Logged in
(passive mode On)
```
### Paso 3: Cargar un archivo al servidor FTP

a.     Ingresar **?** para ver los comandos disponibles en el cliente ftp.

```
ftp> **?**
?
cd
delete
dir
get
help
passive
put
pwd
quit
rename
ftp>
```

b.     Introduzca **dir** para ver los archivos disponibles en el servidor.

```powershell
ftp> **dir**
Listing /ftp directory from 192.168.1.3:
0 : asa842-k8.bin 5571584
1 : asa923-k8.bin 30468096
2 : c1841-advipservicesk9-mz.124-15.T1.bin 33591768
3 : c1841-ipbase-mz.123-14.T7.bin 13832032
<output omitted>
```

c.     Introduzca **put sampleFile.txt** para enviar el archivo al servidor.

```powershell
ftp> **put sampleFile.txt**
Writing file sampleFile.txt to 209.165.200.226:
File transfer in progress...
[Transfer complete - 26 bytes]
26 bytes copied in 0.08 secs (325 bytes/sec)
ftp>
```

d.     Utilice el comando **dir** nuevamente para listar el contenido del servidor FTP y verificar que el archivo se haya cargado en el servidor FTP.

## Parte 2: Descargar un archivo desde el servidor FTP

También puede descargar un archivo desde un servidor FTP. En esta parte, cambiará el nombre del archivo **sampleFile.txt** y lo descargará del servidor FTP.

### Paso 1: Cambie el nombre del archivo a un servidor FTP.

a.     En el indicador **ftp>**, cambie el nombre del archivo **sampleFile.txt** a **sampleFile_FTP.txt**.

```powershell
ftp> **rename sampleFile.txt sampleFile_FTP.txt**
Renaming sampleFile.txt
ftp>
[OK Renamed file successfully from sampleFile.txt to sampleFile_FTP.txt]
ftp>
```

b.     En el indicador **ftp>**, ingrese **dir** para verificar que se haya cambiado el nombre del archivo.

### Paso 2: Descargar el archivo desde el servidor FTP.

a.     Ingrese el comando **get sampleFile_FTP.txt** para recuperar el archivo del servidor.

```powershell
ftp> **get sampleFile_FTP.txt**
Reading file sample File_FTP.txt from 209.165.200.226:
File transfer in progress...
[Transfer complete - 26 bytes]
26 bytes copied in 0.013 secs (2000 bytes/sec)
ftp>
```

b.     Ingrese **quit** para salir del cliente FTP cuando haya terminado.

c.     Mostrar de nuevo el contenido del directorio en el PC para ver el archivo de imagen desde el servidor FTP.

### Paso 3: Eliminar el archivo del servidor FTP.

a.     Inicie sesión en el servidor FTP nuevamente para eliminar el archivo **sampleFile_FTP.txt**.

b.     Ingrese el comando para eliminar el archivo **sampleFile _FTP.txt** del servidor.

#### Pregunta:

¿Qué comando utilizó para eliminar el archivo del servidor FTP?
> `ftp> delete sampleFile_FTP.txt`

c.     Ingrese **quit** para salir del cliente FTP cuando haya terminado.
