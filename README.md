# Bash
Bash (acrónimo de Bourne-Again Shell) es un intérprete de comandos y lenguaje de programación integrado que corre bajo el macroprocesador Shell de Unix.
Este programa ejecuta una a una las órdenes que el usuario pone en una ventana de texto o las que se encuentran contenidas en un script o bash script (archivo con todas las instrucciones), para luego devolver los resultados.
Bash fue diseñado por Stephen Bourne en 1977 y tuvo su primera aparición en Unix v7. Doce años más tarde, en 1989 Brian Fox desarrolla Bourn-Agail Shell para usarse en el proyecto GNU como intérprete de comandos estándar, y continúa actualizándolo hasta 1993 con la ayuda de Chet Ramey, quien creó muchos de los arreglos y nuevas características del programa.
En la actualidad, Bash es el intérprete predeterminado en gran parte de los sistemas GNU/Linux y funciona en la mayoría de sistemas de Unix. Sin embargo, no es el único Shell que existe.

## 1. Comandos de Gestión de Archivos

### **ls**: Lista el contenido del directorio.
- **Sintaxis**: `ls [opciones] [directorio]`
- **Parámetros Comunes**:
  - `-l`: Lista en formato largo.
  - `-a`: Muestra todos los archivos, incluidos los ocultos.
  - `-h`: Muestra los tamaños en un formato legible (por ejemplo, KB, MB).
- **Ejemplo**: 
  - `ls -lha /home/user`: Lista todos los archivos en el directorio `/home/user` en formato largo y legible.

### **cd**: Cambia el directorio actual.
- **Sintaxis**: `cd [directorio]`
- **Ejemplo**: 
  - `cd /var/log`: Cambia al directorio `/var/log`.

### **mkdir**: Crea un nuevo directorio.
- **Sintaxis**: `mkdir [opciones] directorio`
- **Parámetros Comunes**:
  - `-p`: Crea directorios intermedios según sea necesario.
- **Ejemplo**: 
  - `mkdir -p /home/user/docs/proyectos`: Crea el directorio `/home/user/docs/proyectos`, creando también cualquier directorio intermedio que no exista.

### **rmdir**: Elimina un directorio vacío.
- **Sintaxis**: `rmdir [directorio]`
- **Ejemplo**: 
  - `rmdir /home/user/docs/proyectos`: Elimina el directorio `/home/user/docs/proyectos` si está vacío.

### **touch**: Crea un archivo vacío o actualiza la marca de tiempo de un archivo existente.
- **Sintaxis**: `touch [archivo]`
- **Ejemplo**: 
  - `touch /home/user/docs/nuevo_archivo.txt`: Crea un archivo vacío llamado `nuevo_archivo.txt` en el directorio especificado.

### **cp**: Copia archivos o directorios.
- **Sintaxis**: `cp [opciones] origen destino`
- **Parámetros Comunes**:
  - `-r`: Copia directorios de manera recursiva.
  - `-u`: Copia solo cuando el archivo origen es más nuevo que el destino o cuando el archivo de destino no existe.
- **Ejemplo**: 
  - `cp -r /home/user/docs /home/user/backup`: Copia el directorio `docs` al directorio `backup`.

### **mv**: Mueve o renombra archivos o directorios.
- **Sintaxis**: `mv [opciones] origen destino`
- **Ejemplo**: 
  - `mv /home/user/docs/proyecto.txt /home/user/docs/proyecto_renombrado.txt`: Renombra `proyecto.txt` a `proyecto_renombrado.txt`.

### **rm**: Elimina archivos o directorios.
- **Sintaxis**: `rm [opciones] archivo`
- **Parámetros Comunes**:
  - `-r`: Elimina directorios de manera recursiva.
  - `-f`: Fuerza la eliminación sin pedir confirmación.
- **Ejemplo**: 
  - `rm -rf /home/user/docs/proyectos`: Elimina el directorio `proyectos` y todo su contenido.

## 2. Comandos de Búsqueda y Filtro

### **grep**: Busca texto usando patrones.
- **Sintaxis**: `grep [opciones] patrón [archivo]`
- **Parámetros Comunes**:
  - `-i`: Ignora la distinción entre mayúsculas y minúsculas.
  - `-r`: Busca recursivamente en todos los archivos dentro de un directorio.
  - `-v`: Inversa la búsqueda, mostrando líneas que no coinciden con el patrón.
- **Ejemplo**: 
  - `grep -r "error" /var/log`: Busca la palabra "error" en todos los archivos del directorio `/var/log`.

### **awk**: Lenguaje de procesamiento y escaneo de patrones.
- **Sintaxis**: `awk [opciones] 'programa' [archivo]`
- **Ejemplo**: 
  - `awk '{print $1}' /etc/passwd`: Imprime la primera columna de cada línea del archivo `/etc/passwd`.

### **sed**: Editor de flujos para filtrar y transformar texto.
- **Sintaxis**: `sed [opciones] 'comando' [archivo]`
- **Ejemplo**: 
  - `sed 's/antiguo/nuevo/g' archivo.txt`: Reemplaza todas las ocurrencias de "antiguo" con "nuevo" en `archivo.txt`.

### **sort**: Ordena líneas de archivos de texto.
- **Sintaxis**: `sort [opciones] [archivo]`
- **Parámetros Comunes**:
  - `-r`: Ordena en orden inverso.
  - `-n`: Ordena numéricamente.
- **Ejemplo**: 
  - `sort -nr archivo.txt`: Ordena `archivo.txt` en orden numérico inverso.

### **uniq**: Informa o elimina líneas repetidas.
- **Sintaxis**: `uniq [opciones] [archivo]`
- **Parámetros Comunes**:
  - `-c`: Cuenta las ocurrencias de líneas únicas.
- **Ejemplo**: 
  - `uniq -c archivo.txt`: Muestra cada línea única en `archivo.txt` precedida por el número de ocurrencias.

### **diff**: Compara archivos línea por línea.
- **Sintaxis**: `diff [opciones] archivo1 archivo2`
- **Parámetros Comunes**:
  - `-u`: Muestra la diferencia en un formato unificado.
- **Ejemplo**: 
  - `diff -u archivo_viejo.txt archivo_nuevo.txt`: Compara dos archivos y muestra las diferencias en formato unificado.

### **wc**: Imprime el recuento de líneas, palabras y bytes de archivos.
- **Sintaxis**: `wc [opciones] [archivo]`
- **Parámetros Comunes**:
  - `-l`: Imprime solo el número de líneas.
  - `-w`: Imprime solo el número de palabras.
- **Ejemplo**: 
  - `wc -l archivo.txt`: Imprime el número de líneas en `archivo.txt`.

## 3. Comandos de Redirección

### **>**: Redirige la salida estándar a un archivo, sobrescribiéndolo.
- **Ejemplo**: 
  - `echo "Hola, mundo" > archivo.txt`: Escribe "Hola, mundo" en `archivo.txt`, sobrescribiendo el contenido anterior.

### **>>**: Añade la salida estándar a un archivo.
- **Ejemplo**: 
  - `echo "Añadir texto" >> archivo.txt`: Añade "Añadir texto" al final de `archivo.txt`.

### **<**: Redirige la entrada estándar desde un archivo.
- **Ejemplo**: 
  - `sort < archivo.txt`: Ordena las líneas en `archivo.txt`.

### **|**: Pasa la salida de un comando a otro.
- **Ejemplo**: 
  - `ls -l | grep ".txt"`: Lista archivos y luego filtra solo aquellos que terminan en `.txt`.

### **tee**: Lee de la entrada estándar y escribe en la salida estándar y en archivos.
- **Ejemplo**: 
  - `ls -l | tee listado.txt`: Lista archivos y escribe la salida en `listado.txt` además de mostrarla en la terminal.

## 4. Comandos de Archivado

### **tar**: Almacena y extrae archivos de un archivo.
- **Sintaxis**: `tar [opciones] [archivo.tar] [archivo]`
- **Parámetros Comunes**:
  - `-c`: Crea un nuevo archivo.
  - `-x`: Extrae los archivos de un archivo.
  - `-v`: Muestra el progreso en la terminal.
  - `-f`: Especifica el nombre del archivo.
- **Ejemplo**: 
  - `tar -cvf backup.tar /home/user/docs`: Crea un archivo `backup.tar` que contiene el directorio `/home/user/docs`.

### **gzip**: Comprime archivos.
- **Sintaxis**: `gzip [archivo]`
- **Ejemplo**: 
  - `gzip archivo.txt`: Comprime `archivo.txt` y lo reemplaza por `archivo.txt.gz`.

### **gunzip**: Descomprime archivos.
- **Sintaxis**: `gunzip [archivo.gz]`
- **Ejemplo**: 
  - `gunzip archivo.txt.gz`: Descomprime `archivo.txt.gz` y lo reemplaza por `archivo.txt`.
## 5. Comandos de Monitoreo del Sistema

### **top**: Muestra tareas de Linux.
- **Sintaxis**: `top`
- **Ejemplo**: 
  - `top`: Muestra las tareas activas y el uso de recursos en tiempo real.

### **ps**: Informa una instantánea de los procesos actuales.
- **Sintaxis**: `ps [opciones]`
- **Parámetros Comunes**:
  - `-e`: Muestra todos los procesos.
  - `-f`: Muestra una lista completa de procesos.
- **Ejemplo**: 
  - `ps -ef`: Muestra todos los procesos en formato completo.

### **df**: Informa el uso del espacio en disco del sistema de archivos.
- **Sintaxis**: `df [opciones] [archivo]`
- **Parámetros Comunes**:
  - `-h`: Muestra los tamaños en un formato legible (KB, MB, GB).
- **Ejemplo**: 
  - `df -h`: Muestra el uso del disco en un formato legible por humanos.

### **du**: Estima el uso del espacio de archivos.
- **Sintaxis**: `du [opciones] [archivo/directorio]`
- **Parámetros Comunes**:
  - `-h`: Muestra los tamaños en un formato legible.
  - `-s`: Muestra un resumen del uso total del espacio.
- **Ejemplo**: 
  - `du -sh /home/user/docs`: Muestra el uso total del espacio del directorio `/home/user/docs` en formato legible.

### **free**: Muestra la cantidad de memoria libre y usada en el sistema.
- **Sintaxis**: `free [opciones]`
- **Parámetros Comunes**:
  - `-h`: Muestra la memoria en un formato legible.
- **Ejemplo**: 
  - `free -h`: Muestra la memoria disponible y usada en un formato legible.

### **uptime**: Informa cuánto tiempo lleva funcionando el sistema.
- **Sintaxis**: `uptime`
- **Ejemplo**: 
  - `uptime`: Muestra el tiempo de actividad del sistema, el número de usuarios conectados y la carga promedio.

## 6. Comandos de Red

### **ping**: Envía ICMP ECHO_REQUEST a hosts de red.
- **Sintaxis**: `ping [opciones] destino`
- **Parámetros Comunes**:
  - `-c`: Especifica el número de paquetes ECHO_REQUEST a enviar.
- **Ejemplo**: 
  - `ping -c 4 google.com`: Envía 4 paquetes ECHO_REQUEST al dominio `google.com`.

### **curl**: Transfiere datos desde o hacia un servidor.
- **Sintaxis**: `curl [opciones] [URL]`
- **Parámetros Comunes**:
  - `-O`: Guarda el archivo descargado con su nombre original.
  - `-L`: Sigue redireccionamientos.
- **Ejemplo**: 
  - `curl -O https://example.com/archivo.txt`: Descarga un archivo desde una URL.

### **wget**: Descargador de red no interactivo.
- **Sintaxis**: `wget [opciones] [URL]`
- **Parámetros Comunes**:
  - `-b`: Ejecuta wget en segundo plano (background).
  - `-q`: Ejecuta wget en modo silencioso.
- **Ejemplo**: 
  - `wget -q https://example.com/archivo.zip`: Descarga un archivo de manera silenciosa.

### **netstat**: Imprime conexiones de red, tablas de enrutamiento, estadísticas de interfaz, etc.
- **Sintaxis**: `netstat [opciones]`
- **Parámetros Comunes**:
  - `-t`: Muestra solo conexiones TCP.
  - `-u`: Muestra solo conexiones UDP.
  - `-l`: Muestra solo puertos en escucha.
- **Ejemplo**: 
  - `netstat -tuln`: Muestra todas las conexiones TCP y UDP que están en escucha.

### **ssh**: Cliente SSH de OpenSSH (programa de inicio de sesión remoto).
- **Sintaxis**: `ssh [opciones] usuario@host`
- **Parámetros Comunes**:
  - `-p`: Especifica el puerto.
  - `-i`: Especifica el archivo de clave de identidad.
- **Ejemplo**: 
  - `ssh -p 2222 usuario@ejemplo.com`: Conecta al servidor `ejemplo.com` en el puerto `2222`.

### **scp**: Copia segura (programa de copia de archivos remota).
- **Sintaxis**: `scp [opciones] origen destino`
- **Parámetros Comunes**:
  - `-r`: Copia archivos y directorios de manera recursiva.
  - `-P`: Especifica el puerto.
- **Ejemplo**: 
  - `scp -P 2222 archivo.txt usuario@ejemplo.com:/ruta/remota`: Copia `archivo.txt` a un servidor remoto en el puerto `2222`.

### **ftp**: Cliente de Protocolo de Transferencia de Archivos.
- **Sintaxis**: `ftp [opciones] [host]`
- **Ejemplo**: 
  - `ftp ejemplo.com`: Conecta al servidor FTP `ejemplo.com`.

## 7. Comandos de Gestión de Usuarios

### **adduser**: Añade un usuario al sistema.
- **Sintaxis**: `adduser [usuario]`
- **Ejemplo**: 
  - `adduser nuevo_usuario`: Crea un nuevo usuario llamado `nuevo_usuario`.

### **deluser**: Elimina un usuario del sistema.
- **Sintaxis**: `deluser [usuario]`
- **Ejemplo**: 
  - `deluser antiguo_usuario`: Elimina el usuario `antiguo_usuario` del sistema.

### **passwd**: Actualiza los tokens de autenticación de un usuario.
- **Sintaxis**: `passwd [usuario]`
- **Ejemplo**: 
  - `passwd nuevo_usuario`: Cambia la contraseña del usuario `nuevo_usuario`.

### **su**: Sustituye la identidad del usuario.
- **Sintaxis**: `su [opciones] [usuario]`
- **Ejemplo**: 
  - `su - nuevo_usuario`: Cambia la identidad al usuario `nuevo_usuario` en una nueva sesión.

### **sudo**: Ejecuta un comando como otro usuario.
- **Sintaxis**: `sudo [comando]`
- **Ejemplo**: 
  - `sudo apt-get update`: Ejecuta `apt-get update` con privilegios de superusuario.

### **chown**: Cambia el propietario y el grupo de archivos.
- **Sintaxis**: `chown [opciones] propietario:grupo archivo`
- **Ejemplo**: 
  - `chown usuario:grupo archivo.txt`: Cambia el propietario de `archivo.txt` a `usuario` y el grupo a `grupo`.

### **chmod**: Cambia los permisos de acceso a archivos.
- **Sintaxis**: `chmod [opciones] modo archivo`
- **Ejemplo**: 
  - `chmod 755 script.sh`: Asigna permisos de lectura, escritura y ejecución para el propietario, y solo lectura y ejecución para otros usuarios al archivo `script.sh`.

## 8. Comandos de Gestión de Discos

### **fdisk**: Manipulador de tablas de particiones para Linux.
- **Sintaxis**: `fdisk [opciones] [dispositivo]`
- **Ejemplo**: 
  - `fdisk /dev/sda`: Abre la tabla de particiones del dispositivo `/dev/sda` para su edición.

### **mkfs**: Crea un sistema de archivos de Linux.
- **Sintaxis**: `mkfs [opciones] [dispositivo]`
- **Ejemplo**: 
  - `mkfs.ext4 /dev/sda1`: Crea un sistema de archivos ext4 en la partición `/dev/sda1`.

### **mount**: Monta un sistema de archivos.
- **Sintaxis**: `mount [opciones] [dispositivo] [directorio]`
- **Ejemplo**: 
  - `mount /dev/sda1 /mnt/disco`: Monta la partición `/dev/sda1` en el directorio `/mnt/disco`.

### **umount**: Desmonta sistemas de archivos.
- **Sintaxis**: `umount [opciones] [directorio/dispositivo]`
- **Ejemplo**: 
  - `umount /mnt/disco`: Desmonta el sistema de archivos montado en `/mnt/disco`.

### **fsck**: Verifica y repara la consistencia del sistema de archivos.
- **Sintaxis**: `fsck [opciones] [dispositivo]`
- **Ejemplo**: 
  - `fsck /dev/sda1`: Verifica y repara el sistema de archivos en `/dev/sda1`.
## 9. Comandos de Gestión de Procesos

### **kill**: Termina un proceso por PID.
- **Sintaxis**: `kill [opciones] PID`
- **Parámetros Comunes**:
  - `-9`: Fuerza la terminación inmediata del proceso.
- **Ejemplo**: 
  - `kill -9 1234`: Termina inmediatamente el proceso con el PID `1234`.

### **pkill**: Mata procesos por nombre.
- **Sintaxis**: `pkill [opciones] nombre`
- **Parámetros Comunes**:
  - `-f`: Mata procesos coincidiendo con el nombre completo del comando.
- **Ejemplo**: 
  - `pkill -f java`: Mata todos los procesos cuyo comando contenga la palabra `java`.

### **killall**: Mata procesos por nombre.
- **Sintaxis**: `killall [opciones] nombre`
- **Parámetros Comunes**:
  - `-I`: Ignora la distinción entre mayúsculas y minúsculas en el nombre del proceso.
- **Ejemplo**: 
  - `killall -I firefox`: Mata todos los procesos con el nombre `firefox` ignorando mayúsculas y minúsculas.

### **bg**: Reanuda un trabajo suspendido en segundo plano.
- **Sintaxis**: `bg [job_spec]`
- **Ejemplo**: 
  - `bg %1`: Reanuda el trabajo número 1 en segundo plano.

### **fg**: Trae un trabajo al primer plano.
- **Sintaxis**: `fg [job_spec]`
- **Ejemplo**: 
  - `fg %1`: Trae el trabajo número 1 al primer plano.

### **jobs**: Lista los trabajos activos.
- **Sintaxis**: `jobs [opciones]`
- **Parámetros Comunes**:
  - `-l`: Muestra el PID de los trabajos.
- **Ejemplo**: 
  - `jobs -l`: Lista los trabajos activos junto con sus PIDs.

### **nohup**: Ejecuta un comando inmune a interrupciones, con salida a un archivo.
- **Sintaxis**: `nohup comando [argumentos] &`
- **Ejemplo**: 
  - `nohup ./script.sh &`: Ejecuta `script.sh` inmune a interrupciones y continúa ejecutándose en segundo plano.
