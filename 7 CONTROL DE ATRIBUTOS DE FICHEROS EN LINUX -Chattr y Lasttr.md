## Introducción:

Los comandos chattr y lsattr tienen una función concreta, lsattr permite listar los atributos asignados a los ficheros de un sistema de ficheros Linux, por otro lado, chattr permite modificar dichos atributos, los cuales utilizamos como complemento al sistema de ACLs (chmod, chown, setfacl ...) permitiendo un control más seguro sobre los archivos del sistema.
## Comando "lsattr":

El uso de lsattr no tiene demasiado misterio yq que únicamente nos servirá para listar atributos de ficheros y directorios.

Algunos parámetros del comando que conviene conocer son, por ejemplo "-a" (permite mostrar todos los archivos del directorio, incluidos los ocultos), "-R" (permite visualizar los atributos de forma recursiva).
## Comando "chattr":

Para comenzar a asignar atributos haremos uso del comando chattr. A continuación vamos a ver mediante ejemplos algunas de las posibilidades que nos ofrece, las letras que pasamos como parámetro simbolizan los atributos a modificar y el "+" o el "-" si lo añadimos o quitamos. Como parámetros opcionales a chattr podemos pasar que el cambio de atributos sea recursivo (R), verbose (V) y suprimir la salida de errores (f).

### Deshabilitar la modificación de la fecha de acceso al fichero (atime):

Con la asignación del atributo 'A' conseguimos que cuando se acceda al fichero no se modifique el registro atime. De este modo no quedará registrada la fecha del último acceso al fichero:
	chattr +A 'nombre-del-fichero'
### Comprimir automáticamente el fichero en el disco:

Si asignamos el atributo 'c' activamos que el fichero se comprima automáticamente en el disco por el kernel. Cuando se lea el fichero se servirá descomprimido:
	chattr +c 'nombre-del-fichero'
### Bloquear la modificación o borrado de un archivo:

Al asignar el atributo 'i' activamos la flag para que el fichero no pueda ser modificado, borrado o renombrado:
	chattr +i 'nombre-del-fichero'
### Permitir recuperación del archivo aunque sea eliminado:

Asignamos el atributo 'u' para que cuando el fichero se borre, sus datos permanezcan guardados y permitan al usuario su recuperación:
	chattr +u 'nombre-del-fichero'
### Al eliminar un archivo, sobrescribir con 0 todos sus bloques:

Al contrario que con el atributo 'u', el atributo 'e' implica que cuando un archivo sea borrado, automáticamente los bloques utilizados por el mismo sean sobrescritos con ceros (zeroed):
	chattr +e 'nombre-del-fichero'
### Escribir de forma síncrona a disco cambios en los ficheros:

El parámetro 'S' implica que cuando un fichero es modificado, los cambios se aplican a disco de forma síncrona y directa. Es lo mismo que tener la flag "sync" en el punto de montaje del filesystem.
	chattr +S 'nombre-del-fichero'
### Solo apertura en Modo de anexión para escritura:

Un archivo con el atributo 'a', solo se puede abrir en modo de anexión para escritura. Solo root o un proceso que posee la capacidad CAP_LINUX_INMUTABLE puede establecer o borrar este atributo.
	chattr +a 'nombre-del-fichero'