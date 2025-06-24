## Descripción:

Con el propósito de realizar comprobaciones de permisos, tradicionales de Unix distinguen dos categorías de procesos: procesos privilegiados (cuyo identificador de usuario efectivo es 0, refiriéndose al usuario root) y procesos no privilegiados (cuyo identificador de usuario efectivo es distinto de cero). Los procesos privilegiados evitan todas las comprobaciones de permisos del núcleo, mientras que los procesos no privilegiados se ven sujetos a severas comprobaciones de permisos basadas en las credenciales del proceso (normalmente: ID de usuario efectivo, ID de grupo efectivo y lista de grupos adicionales).

Las capabilities permiten al propietario permitir que sus binarios, ejecutados por usuarios no root, realicen operaciones privilegiadas sin necesidad de otorgarles permisos root
## Lista de capabilities:

### CAP_CHOWN:

Permite cambios arbitrarios en los IDs de usuario y de grupo de los  ficheros.
### CAP_DAC_OVERRIDE:

Evita  las  comprobaciones  de  permisos  sobre operaciones de lectura, escritura y ejecución. (DAC = "control de acceso discrecional".)
### CAP_DAC_READ_SEARCH:

Evita comprobaciones de permisos sobre operaciones de lectura de ficheros y lectura y ejecución de directorios.
### CAP_FOWNER:

Evita comprobaciones de permisos sobre operaciones que normalmente requieren que el ID de usuario del sistema de ficheros del proceso coincida con el ID de usuario del fichero, excluyendo   aquellas   operaciones  cubiertas  por **CAP_DAC_OVERRIDE** y **CAP_DAC_READ_SEARCH**; ignora  el  bit  pegajoso  (sticky)  en  el borrado de ficheros.
### CAP_FSETID:

No borra los bits set-user-ID y set-group-ID cuando se modifica un fichero; permite establecer el bit set-group-ID para un fichero cuyo ID de grupo no coincide con  el del  sistema  de  ficheros  o  cualquier  otro  ID  de  grupo adicional del proceso invocador.
### CAP_IPC_LOCK:

Permite el bloqueo en memoria (mlock, mlockall, shmctl).
### CAP_IPC_OWNER:

Evita comprobaciones de permisos para las operaciones sobre objetos System V IPC.
### CAP_KILL:

Evita comprobaciones de permisos para enviar señales.
### CAP_LEASE:

Permite  que  se  establezcan  arriendos  sobre  ficheros arbitrarios.
### CAP_LINUX_INMUTABLE:

 Permite  establecer  los  atributos  extendidos  **EXT2_APPEND_FL** y **EXT2_IMMUTABLE_FL**  sobre ficheros del sistema de ficheros ext2.
### CAP_MKNOD:

Permite la creación de ficheros especiales usando mknod.
### CAP_NET_ADMIN:

Permite varias  operaciones  relacionadas  con  redes  (p.e.,  establecer  opciones privilegiadas  sobre  conectores,  habilitar  la  difusión de paquetes multidestino (multicasting), configuración de interfaces, modificar tablas de encaminamiento).
### CAP_NET_BIND_SERVICE:

Permite ligar conectores a puertos reservados del dominio de Internet  (números  de puerto menores que 1024).
### CAP_NET_BROADCAST:

Permite la difusión universal (broadcasting) de paquetes a través de un conector y la escucha de paquetes multidestino.
### CAP_NET_RAW:

Permite el uso de conectores de tipo RAW y PACKET.
### CAP_SETGID:

Permite manipulaciones arbitrarias de los IDs de grupo y de  la  lista  de  IDs  de grupo adicionales de un proceso; permite el uso de IDs de grupo falsificados cuando se pasan credenciales de conectores a través de conectores de dominio Unix.
### CAP_SETCAP:

 Concede o elimina cualquier capacidad en el conjunto de capacidades permitidas  del invocador a o desde cualquier otro proceso.

### CAP_SETUID:

 Permite   manipulaciones  arbitrarias  de  los  IDs  de  usuario  de  los  procesos (setuid, etc.); permite el uso de IDs de usuario falsificados  cuando  se  pasan credenciales de conectores a través de conectores de dominio Unix.
### CAP_SYS_ADMIN:

 Permite  una  variedad  de  operaciones  de  administración del sistema incluyendo: quotactl, mount, swapon, sethostname, setdomainname, **IPC_SET**  y operaciones  **IPC_RMID**  sobre objetos arbitrarios IPC de System V; permite el uso de IDs de usuario falsificados cuando se pasan credenciales de conectores.
### CAP_SYS_BOOT:

Permite llamadas a reboot.
### CAP_SYS_CHROOT:

Permite llamadas a chroot.
### CAP_SYS_CHROOT:

Permite llamadas a chroot.
### CAP_SYS_MODULE:

Permite cargar y eliminar módulos del núcleo.
### CAP_SYS_NICE:

Permite aumentar el valor nice del proceso invocador (nice, setpriority) y cambiar el valor de nice de procesos arbitrarios; permite establecer políticas de planificación y prioridades para procesos arbitrarios (sched_setsscheduler, sched_setparam).