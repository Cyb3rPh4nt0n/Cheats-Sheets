## ¿Qué es el Sticky Bit y cómo configurarlo?

El Sticky Bit o bit adhesivo es uno de los permisos especiales de acceso utilizando en ficheros y directorios del entorno Unix y derivados como Linux. Su objetivo es que solo el usuarios creador pueda eliminar o renombrar un archivo en sistemas donde todos los usuarios tienen permisos de lectura y escritura. Además, su activación está representada con la letra T mayúscula en el listado de permisos de un directorio.

Originalmente, este permiso de sticky bit solía utilizarse en dispositivos con poca RAM sobre ficheros ejecutables para indicarle al sistema operativo que debía mantener un determinado programa en SWAP para las siguientes ejecuciones, incluso si estas las realizaban otros usuarios. Sin embargo, debido a la actualización y mejora de los sistemas de almacenamiento, esta labor dejó de ser necesaria, por lo que, en la actualidad, las funciones de Sticky Bit están enfocadas en los directorios y es comúnmente ejecutado sobre /tmp y /var/tmp.

Pertenece a los tres tipos de permisos especiales (Sticky Bit, Suid y Sgid) que son configurables en directorios o ficheros. A diferencia de los demás permisos de archivos, el bit de adhesión y los demás permisos de acceso especial no se corresponde con un número octal entre 000 y 777, como sucede con los permisos normales, sino que varían entre 0000 y 7777, siendo Sticky Bit el número 1000.
## Configuración de Sticky Bit:

La configuración de este permiso de bit, sticky bit, pegajoso está a cargo del comando chmod (change mood), que tiene la función de gestionar y modificar los diferentes permisos de acceso del dispositivo. Por lo tanto, para la activación de este permiso deberás ejecutar alguno de los siguientes comandos:

* chmod 1775 test
* chmod +t /test

En el caso de querer desactivar el Sticky Bit, tendrás que usar el comando chmod -t /test. Otra opción es añadir un 0 al número octal; su representación se vería así: chmod 0777 /tmp.

Después de la asignación de este bit, el comando ls mostrará que el directorio tiene una t en el área del resto de usuarios, en lugar de una x. Esta t (minúscula) aparecerá solo cuando la sección de "otros" contiene los permisos de ejecución más un Sticky Bit. En cambio, la T (mayúscula) se obtiene cuando el apartado de usuarios no propietarios no contiene el permiso sticky bit de ejecución, solo un bit fijo.
## Ventajas y desventajas de Sticky Bit:

La principal ventaja de la activación del bit de adhesión o Sticky Bit es su gran utilidad al momento de tener directorios compartidos entre varios usuarios, debido a que permite que solo el usuario creador de un archivo, el propietario del directorio o el usuario root pueda eliminarlo o renombrarlo, incluso si los demás usuarios tienen permisos de escritura para sticky bit linux.

Sin embargo, la desventaja que presenta este permiso de acceso, sticky bit linux, es que el programa que lo tenga activado permanece en la memoria, aunque ya haya sido ejecutado, por lo que, un mal uso o uso excesivo del Sticky Bit podría saturar el consumo de memoria de la máquina.