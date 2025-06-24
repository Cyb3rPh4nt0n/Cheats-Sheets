## El directorio raíz (/):

Todos los archivos y directorios, en Linux se encuentran bajo la 'raíz' representada por '/'. Si observas la estructura de directorios, te darás cuenta de que es similar a la raíz de una planta. Como todos los demás directorios o archivos descienden de la raíz, la ruta absoluta de cualquier archivo pasa por la raíz. Por ejemplo, si tienes un archivo en /home/user/documents, puedes adivinar que la estructura de directorios va desde /->home->user->documents.
## /bin - Binarios:

El '/bin' contiene directamente los archivos ejecutables de muchos comandos básicos del shell como ls, cp, cd, etc. La mayoría de los programas están en formato binario aquí y son accesibles para todos los usuarios del sistema Linux.
## /dev - Archivos de dispositivos:

Este directorio sólo contiene archivos especiales, incluidos los relativos a los dispositivos. Son archivos virtuales, no están físicamente en el disco.
Algunos ejemplos interesantes de estos archivos son:
- /dev/null: puede ser enviado para destruir cualquier archivo o cadena.
- /dev/zero: contiene una secuencia infinita de 0.
- /dev/random: contiene una secuencia infinita de valores aleatorios.
## /etc - Archivos de configuración:

El directorio /etc contiene los archivos de configuración principales del sistema, utilizados principalmente por el administrador y los servicios, como el archivo de contraseñas y los archivos de red.
Si necesitas hacer cambios en la configuración del sistema (por ejemplo, cambiar el nombre del host), aquí es donde encontrarás los archivos respectivos.
## /usr - Binarios de usuario y datos de programas:

El '/usr' van todos los archivos ejecutables, las bibliotecas, el código fuente de la mayoría de los programas del sistema. Por esta razón, la mayoría de los archivos que contiene es de sólo lectura (para el usuario normal).
- '/usr/bin' contiene los comandos básicos del usuario.
- '/usr/sbin' contiene comandos adicionales para el administrador.
- '/usr/lib' contiene las bibliotecas del sistema.
- '/usr/share' contiene la documentación o común a todas las bibliotecas, por ejemplo '/usr/share/man' contiene el texto de la página man.
## /home - Datos personales de usuario:

El directorio home contiene los directorios personales de los usuarios. el directorio personal contiene los datos del usuario y los archivos personales, notas, programas, etc. en tu directorio personal. Cuando creas un usuario en tu sistema Linux, es una práctica general crear un directorio personal para el usuario. Supongamos que tu sistema Linux tiene dos usuarios, user1 y user2. Ellos tendrán un directorio personal en las ubicaciones /home/user1 y /home/user2. Ten en cuenta que user2 no tendrá acceso a /home/user1 y viceversa. Esto tiene sentido porque sólo el usuario debe tener acceso a su directorio. Esto se puede cambiar modificando los permisos.
## /lib - Bibliotecas compartidas:

Las bibliotecas son básicamente códigos que pueden ser utilizados por los binarios ejecutables. El directorio /lib contiene las bibliotecas que necesitan los binarios de los directorios /bin /sbin. Las bibliotecas que necesitan los binarios en /usr/bin y /usr/sbin se encuentran en el directorio /usr/lib.
## /sbin - Binarios del sistema:

Es similar al directorio /bin. La única diferencia es que contiene los binarios que sólo pueden ser ejecutados por root o un usuario sudo. Puedes pensar en la 's' de 'sbin' como super o sudo.
### /tmp - Archivos temporales:

Como su nombre indica, este directorio contiene archivos temporales. Muchas aplicaciones utilizan este directorio para almacenar archivos temporales. Incluso usted puede utilizar el directorio para almacenar archivos temporales.
Pero ten en cuenta que los contenidos en los directorios /tmp se borran cuando su sistema se reinicia. Algunos sistemas Linux también eliminan los archivos antiguos automáticamente, así que no almacene nada importante aquí.
### /var - Archivos de datos variables:

Var, abreviatura de variable, es el lugar donde los programas almacenan la información en tiempo de ejecución, como el registro del sistema, el seguimiento de los usuarios, las cachés y otros archivos que los programas del sistema crean y gestionan.
Los archivos que se almacenan aquí NO se limpian automáticamente y, por lo tanto, es un buen lugar para que los administradores del sistema busquen información sobre el comportamiento de su sistema. Por ejemplo, si quieres comprobar el historial de inicio de sesión en tu sistema Linux, sólo tienes que comprobar el contenido del archivo en /var/log/wtmp.
### /boot - Archivos de arranque:

El directorio '/boot' contiene los archivos del kernel y la imagen de arranque, además de LILO y Grub. Suelen ser recomendable que el directorio resida en una partición al principio del disco.
### /proc - Archivos del proceso y del núcleo:

El directorio '/proc' contiene la información sobre los procesos que se están ejecutando y los parámetros del kernel. El contenido del directorio proc es utilizado por una serie de herramientas para obtener información del sistema en tiempo de ejecución.
Por ejemplo, si quieres comprobar la información del procesador en Linux, simplemente puedes consultar el archivo /proc/cpuinfo. Si quieres comprobar el uso de la memoria de tu sistema Linux, sólo tienes que mirar el contenido del archivo /proc/meminfo.
### /opt - Software opcional:

Tradicionalmente, el directorio /opt se utiliza para instalar/almacenar los archivos de aplicaciones de terceros que no están disponibles en el repositorio de la distribución.
La práctica normal es mantener el código del software en opt y luego enlazar el archivo binario en el directorio /bin para que todos los usuarios puedan ejecutarlo.
### /root - El directorio principal de la raíz:

También existe el directorio /root, que funciona como el directorio principal del usuario root. Así que en lugar de /home/root, el hogar de root se encuentra en /root. No lo confunda con el directorio raíz (/).
### /media - Punto de montaje para medios extraíbles:

Cuando conectas un medio extraíble como un disco USB, una tarjeta SD o un DVD, se crea automáticamente un directorio bajo el directorio /media para ellos. Puede acceder al contenido de los medios extraíbles desde este directorio. /media - Punto de montaje para medios extraíbles.
### /mnt - Montar directorio:

Es similar al directorio /media, pero en lugar de montar automáticamente el medio extraíble, mnt es utilizando por los administradores del sistema para montar manualmente un sistema de archivos.
### /srv - Datos de servicios:

El directorio /srv contiene los datos de los servicios proporcionados por el sistema. Por ejemplo, si ejecuta un servidor HTTP, es una buena práctica almacenar los datos del sitio web en el directorio /srv.