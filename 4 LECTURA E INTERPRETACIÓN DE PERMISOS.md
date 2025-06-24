# Introducción.

En GNU/Linux, los permisos o derechos que los usuarios pueden tener sobre determinados archivos contenidos en él se establecen en tres niveles claramente diferenciados. Estos tres niveles son los siguientes:

- Permisos del propietario.
- Permisos del grupo.
- Permisos del resto de usuarios (o también llamados los otros).

Para tener claros estos conceptos, en los sistemas en red (como lo es Linux) siempre existe la figura del administrador, superusuario o root. Este administrador es el encargado de crear y dar de baja a usuarios, así como también de establecer los privilegios que cada uno de ellos tendrá en el sistema. Estos privilegios se establecen tanto para el directorio HOME de cada usuario como para los directorios y archivos a los que el administrador decida que el usuario pueda acceder.
## Permisos del propietario:

El propietario es aquel usuario que genera o crea un archivo/carpeta dentro de su directorio de trabajo (HOME), o en algún otro directorio sobre el que tenga derechos. Cada usuario tiene la potestad de crear, por defecto, los archivos que quiera dentro de su directorio de trabajo. En principio, él y solamente él será el que tenga acceso a la información contenida en los archivos y directorios que hay en su directorio HOME.
## Permisos del grupo:

Lo más normal es que cada usuario pertenezca a un grupo de trabajo. De esta forma, cuando se gestiona un grupo, se gestionan todos los usuarios que pertenecen a éste. Es decir, es más fácil integrar varios usuarios en un grupo al que se le concedan determinados privilegios en el sistema, que asignar los privilegios de forma independiente a cada usuario.
## Permisos del resto de usuarios:

Por último, también los privilegios de los archivos contenidos en cualquier directorio, pueden tenerlos otros usuarios que no pertenezcan al grupo de trabajo en el que está integrado el archivo en cuestión. Es decir, a los usuarios que no pertenezcan a otros grupos de trabajo, se les denomina resto de usuarios del sistema.
## Lectura de permisos:

Antes de aprender cómo se establecen los permisos de GNU/Linux, debemos saber cómo se pueden diferenciar los diferentes tipos de archivos que el sistema puede tener.

Cada archivo en Linux queda identificado por 10 caracteres a los que se les denomina máscara. De estos 10 caracteres, el primero (de izquierda a derecha) hace referencia al tipo de archivo. Los 9 siguientes, se leen en bloques de 3 (quedando 3 bloques de 3), estos hacen referencia a los permisos que se le conceden, respectivamente, al propietario, al grupo y al resto u otros.

El primer carácter de los archivos puede ser el siguiente:

- "-" → Archivo
- "d" → Directorio
- "b" → Archivo de bloques especiales (Archivos especiales de dispositivo)
- "c" → Archivo de caracteres especiales (Dispositivo tty, impresora...)
- "l" → Archivo de vinculo o enlace (soft/symbolic link)
- "p" → Archivo especial de cauce (pipe o tubería)

Los siguientes nueve caracteres son los permisos que se les concede a los usuarios del sistema. Cada tres caracteres, se referencian los permisos de propietario, grupo y resto de usuario.
Los caracteres que definen estos permisos son los siguientes:

- "-" → Sin permiso
- "r" → Permiso de lectura
- "w" → Permiso de escritura
- "x" → Permiso de ejecución

## Permisos para archivos:

Lectura: permite, fundamentalmente, visualizar el contenido del archivo.
Escritura: permite modificar el contenido del archivo.
Ejecución: permite ejecutar el archivo como si de un programa ejecutable se tratase.
## Permisos para directorios:

Lectura: permite saber qué archivos y directorios contiene el directorio que tiene este permiso.
Escritura: permite crear archivos en el directorio, bien sean archivos ordinarios o nuevos directorios. Se pueden borrar directorios, copiar archivos en el directorio, mover, cambiar el nombre, etc.
Ejecución: permite situarse sobre el directorio para poder examinar su contenido, copiar archivos de o hacia él. si además se dispone de los permisos de escritura y lectura, se podrán realizar todas las operaciones posibles sobre archivos y directorio.
## Asignación de permisos:

El comando chmod (change mode) permite modificar la máscara para que se puedan realizar más o menos operaciones sobre archivos o directorios, dicho de otra forma, con chmod puedes quitar o eliminar derechos a cada tipo de usuarios. Si no se especifica el tipo de usuario al que queremos quitar, poner o asignar privilegios, lo que sucederá al realizar la operación es afectar a todos los usuarios simultáneamente.

Referencia de usuarios:

- "u" → Propietario del archivo o directorio
- "g" → Grupo al que pertenece el archivo o directorio
- "o" → Todos los demás usuarios que no son el dueño ni del grupo

Tipos de permiso:

- "r" → Permiso de lectura
- "w" → Permiso de escritura
- "x" → Permiso de ejecución

Nota: Para asignar permisos se usa "+" y para quitar "-".
## Permisos en formato octal:

Hay otra forma de utilizar el comando chmod que, puede resultar más cómoda.

La combinación de valores de cada grupo de los usuarios forma un número octal, el bit "x" es 2^0 es decir 1, el bit "w" es 2^1 es decir 2, el bit "r" es 2^2 es decir 4, tenemos entonces:

- "r" = 4
- "w" = 2
- "x" =1

La combinación de bits encendidos o apagados en cada grupo da ocho posibles combinaciones de valores, es decir la suma de los bits encendidos:

* --- → 0 → no se tiene ningún permiso
* --x → 1 → solo permiso de ejecución
* -w- → 2 → solo permiso de escritura
* -wx → 3 → permisos de escritura y ejecución
* r-- → 4 → solo permiso de lectura
* r-x → 5 → permisos de lectura y ejecución
* rw- → 6 → permisos de lectura y escritura
* rwx → 7 → todos los permisos establecidos, lectura, escritura y ejecución

Cuando se combinan los permisos del usuario, grupo y otros, se obtiene un número de tres cifras que conforman los permisos del archivo o del directorio.
## Cambiar los propietarios de archivos y directorios:

Para cambiar el propietario de un archivo y una carpeta en Linux, utilizaremos el comando chown. Esta es la sintaxis básica: chown 'propietario:grupo' 'nombre-del-archivo'.
## Permisos especiales:

Hay otro tipo de permisos que hay que considerar. Se trata del bit de permisos SUID (Set User ID), el bit de permisos SGID (Set Group ID) y el bit de permisos de persistencia (sticky bit).
## setuid:

El bit setuid es asignable a ficheros ejecutables, y permite que cuando un usuario ejecute dicho fichero, el proceso adquiera los permisos del propietario del fichero ejecutado. Para saber si un ejecutable tiene el bit setuid debe aparecer una "s" en el bloque de permisos del propietario.

Para asignar este bit a un fichero se usa: chmod u+s 'ruta-del-binario/ejecutable'.
Para quitarlo: chmod u-s 'ruta-del-binario/ejecutable'

Nota: Debemos utilizar este bit con extremo cuidado ya que puede provocar una escalada de privilegios en nuestro sistema.
## setgid:

El bit setgid permite adquirir los privilegios del grupo asignado al fichero, también es asignable a directorios. Esto será muy útil cuando varios usuarios de un mismo grupo necesitan trabajar con recursos dentro de un mismo directorio.

Para asignar este bit se usa: chmod g+s '/carpeta-compartida'
Para quitarlo: chmod g-s '/carpeta-compartida'
## sticky:

Este bit suele asignarse en directorios a los que todos los usuarios tienen acceso, y permite evitar que un usuario pueda borrar ficheros/directorios de otro usuario dentro de ese directorio, ya que todos tienen permiso de escritura. Podemos ver que el bit está asignado como "t" en el bloque de permisos de otros.

Para asignar este bit se usa: chmod o+t '/ruta-del-directorio'
Para quitarlo: chmod o-t '/ruta-del-directorio'