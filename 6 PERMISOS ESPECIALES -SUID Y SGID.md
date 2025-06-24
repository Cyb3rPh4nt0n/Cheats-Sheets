## Permiso SUID:

El permiso SUID permite que un archivo se ejecute como si del propietario se tratase, independientemente del usuario que lo ejecute, el archivo se ejecutará como el propietario.

Al asignar permisos SUID, la salida del comando pasará a ser del propietario del binario.

Una cosa a tener en cuenta, es que el permiso SUID no funciona en scripts, solo lo hace en binarios compilados. Esto se hace por razones de seguridad. En cualquier caso si quieres habilitar la ejecución de un script como otro usuario, siempre se puede tirar de sudo.

La forma de identificar el permiso SUID es mediante una "s" en el permiso de ejecución del propietario. Si el propietario no tiene permisos de ejecución, pero si permiso SUID, se verá "S", de lo contrario, "s".

El SUID no aplica a los directorios debido a que no hay una razón convincente de por qué debería. No puede funcionar de la misma manera que SGID. Linux no permite que un usuario entregue un archivo a otro usuario, el único capaz de hacer esto es root. Es decir, si yo soy el usuario "user1", aunque yo sea propietario de un archivo, no seré capaz de usar chown para entregar el archivo al usuario "user2", esta acción solo la puede hacer root.

Para activar el permiso SUID se puede hacer de dos formas:
	chmod u+s 'archivo'
	chmod 4*** 'archivo'
Siendo el * los permisos en octal (ejemplo: 755)
## Permiso SGID:

El permiso SGID está relacionado con los grupos, tiene dos funciones:

- Si se establece en un archivo, permite que cualquier usuario ejecute el archivo como si fuese miembro del grupo al que pertenece el archivo.
- Si se establece en un directorio, a cualquier archivo creado en el directorio se le asignará como grupo perteneciente, el grupo del directorio.

Para los directorios, la lógica del SGID y el motivo de su existencia es por si trabajamos en grupo, para que todos podamos acceder a los archivos de las demás personas. Si SGID no existiera, cada persona cada vez que crease un archivo, tendría que cambiarlo del grupo suyo al grupo común del proyecto. Asimismo, evitamos tener que asignarle permisos a "Otros".

Para identificar el permiso SGID, podemos observar en la parte de los permisos de grupo que en el permiso de ejecución se asignara una "s". Si el archivo tiene permisos de ejecución, se asignará "s", si por el contrario no tiene permisos de ejecución, se asignará "S".

Esto realmente para los directorios no tiene relevancia, solo para los archivos. En cualquier caso, esta característica de "s" mayúscula o minúscula dependiendo del permiso de ejecución se aplica siempre, incluido en el permiso SUID.

Para añadir el permiso SGID se puede hacer de dos formas:
	chmod g+s 'archivo'
	chmod 2*** 'archivo'
Siendo el * los permisos en octal (ejemplo: 755)
## Comportamiento de UID y GID:

Para empezar, todos los usuarios del sistema tienen un identificador (UID), este lo podemos ver en el archivo /etc/passwd.

Así mismo, los grupos también tienen identificadores, los podemos ver en el archivo /etc/group.

Sabiendo esto, podemos llegar a distinguir a nivel práctico, 3 comportamientos del UID:

- ID del Usuario Real (RUID) → Identifica al propietario del proceso actual.
- ID de Usuario Efectivo (EUID) → Se usa para gestionar los accesos a un recurso. También es el que se tiene en cuenta para determinar el propietario de un archivo cuando se crea. Básicamente, determina que podemos hacer, a que podemos acceder, etc. Se podría decir, que a nivel práctico, "somos el usuario que indica el EUID".
- ID de Usuario Guardado (SUID / Saved-User-ID) → Se utiliza en archivos. Y permite que el proceso cambie su EUID. Cuando el proceso cambia su EUID, el EUID antes de cambiárselo, se almacena en el SUID para que cuando acabe el proceso, pueda volver a su EUID original.

NOTA: al igual que existen estos tres comportamientos del UID. Ocurre lo mismo con el GID (Group ID). Por lo que, con la misma definición, pero en grupos. Existen: RGID, EGID y SGID.

Todos los procesos tienen dos UIDs y dos GIDs (real y efectivo). Normalmente, cuando ejecutemos un programa, el UID y GID real serán el mismo que el UID y GID efectivo. Sin embargo, si ese programa tiene el SUID activado el UID efectivo cambiarán. Asimismo, si tiene el permiso SGID activo, el GID efectivo cambiará.

Es decir, si soy el usuario "user1" y hay un binario con SUID cuyo propietario es root. Yo al ejecutarlo, mi UID real seguirá siendo el de "user1", sin embargo, el UID efectivo será el de root.

El UID efectivo, como se ha dicho es el que determina los accesos y privilegios de un proceso. Por ejemplo, si solo quien tenga UID 22 puede acceder a un archivo, si su RUID es 22 pero tu EUID (UID) es 35, no podrás leerlo.