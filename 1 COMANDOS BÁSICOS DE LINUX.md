## Comandos Básicos:

Acercar -> 'Ctrl' + '+'
Alejar -> 'Ctrl' + '-'
Imprimir directorio de trabajo -> pwd
Limpiar la terminal -> 'Ctrl' + 'l' o comando clear
Asignar un alias -> alias *alias-name*="*comando-a-ejecutar*"
Obtener un archivo -> source *nombre-del-archivo-a-leer-o-ejecutar*
Reiniciar el sistema -> reboot
Cerrar el sistema -> shutdown
## Comandos de Directorios:

Moverse a un directorio específico -> cd *nombre-de-tu-directorio*
Moverse un directorio atrás -> cd ..
Ir al directorio personal del usuario -> cd o cd ~
Moverse al último directorio donde se estaba -> cd -
Moverse a un directorio recién creado -> cd !$
## Comandos de listas:

Enumerar todos los archivos y directorios visibles -> ls
Enumerar todos los archivos y directorios (incluidos los ocultos) -> ls -a
Enumerar todos los archivos y directorios (detallando privilegios) -> ls -l
Formato legible para los humanos -> ls -lh
Combinando argumentos -> ls -la
## Comandos de búsqueda:

Buscar el binario de un programa -> which *nombre-del-programa* 
- Buscar el manual binario, fuente y de usuario de un programa -> whereis *nombre-del-programa*
- Buscar archivos y directorios por nombre -> find *ruta-de-búsqueda* -name *nombre-del-archivo-que-quieres-buscar*
Obtén más información sobre el comando de búsqueda -> man find
Obtén una breve descripción de un comando -> whatis *nombre-del-comando*
## Historial de comandos:

Obtén comandos anteriores (uno por uno) -> Use Up Arrow Key para navegar por su historial
Obtén comandos anteriores (lista completa) -> history
Repite los comandos del historial (comando bang) -> history -> !*number-of-the-command-to-repeat*
Repite el último comando (comando bang-bang) -> !!
## Comandos para trabajar con archivos y directorios:

Crear un nuevo archivo (sin abrirlo) -> touch *nombre-del-archivo*
Crear un nuevo archivo utilizando un editor de texto:
- vim *nombre-del-archivo*
- nano *nombre-del-archivo*
Copiar un archivo -> cp *ruta-origen-del-archivo* *ruta-destino-del-archivo*
Crear un nuevo directorio -> mkdir *nombre-del-nuevo-directorio*
Eliminar un directorio vacío -> rmdir *nombre-del-directorio-a-eliminar*
Comando de eliminar (rm):
- Eliminar un archivo -> rm *nombre-del-archivo*
- Eliminar un directorio de forma recursiva -> rm -rf *nombre-del-directorio*
Comando de concatenar (cat):
- Ver un solo archivo -> cat *nombre-del-archivo*
- Ver un solo archivo que incluye los números de línea -> cat -n *nombre-del-archivo*
- Copiar el contenido de un archivo a otro archivo -> cat *nombre-del-archivo-con-el-contenido-a-copiar* > *destination-filename*
Comando de mover (mv):
- Mover un archivo -> mv *ruta-de-origen-del-archivo* *ruta-destino-del-archivo*
- Cambiar el nombre de un archivo -> mv *nombre-del-archivo* *nuevo-nombre-del-archivo*
Determinar el tipo de archivo a través del análisis parcial de su contenido -> file *nombre-del-archivo*
Mostrar la ubicación de un archivo mostrando su "path" -> type *nombre-del-archivo*
Descompresión de archivos:
- Mostrar el contenido del comprimido -> 7z l *nombre-del-archivo*
- Descomprimir el archivo -> 7z x *nombre-del-archivo*
## Buscar con grep:

Buscar una cadena dentro de un archivo -> grep *término-a-buscar* *archivo-fuente-búsqueda*
Búsqueda que no distingue entre mayúsculas y minúsculas dentro de un archivo -> grep -i *término-a-buscar* *archivo-fuente-de-búsqueda*
Buscar líneas que no coincidan dentro de un archivo -> grep -v *término-a-buscar* *archivo-fuente-de-búsqueda*
Búsqueda recursiva dentro de un directorio -> grep -r *término-a-buscar* *path-to-directory-to-search*
Varias búsquedas dentro de un archivo -> grep -E "*primer-término-a-buscar*|*segundo-término-a-buscar*" *archivo-fuente-de-búsqueda*
Contar los resultados de la búsqueda -> grep -c *término-a-buscar* *archivo-fuente-de-búsqueda*
Mostar el nombre de los archivos coincidentes -> grep -l *término-a-buscar* *archivos-que-coincidan-a-buscar*
## Pipelines o tuberías:

Comandos en tuberías -> comando 1 | comando 2 | comando n
Canalización de resultados de búsqueda filtrados en un nuevo archivo -> ls | grep *término-a-filtrar* | cat > *ruta-al-nuevo-archivo*/*nombre-para-nuevo-archivo*
Buscar en el historial de comandos -> history | grep "*término-a-buscar*"
## Permisos: cambiar el comando de bits del modo de archivo (CHMOD):

Agregar permisos de ejecución a todos -> chmod +x *nombre-del-archivo*
Quitar el permiso de ejecución a todos -> chmod -x *nombre-del-archivo*
Agregar permiso de ejecución al propietario -> chmod u+x *nombre-del-archivo*
Eliminar el permiso de escritura a otros usuarios -> chmod o-w *nombre-del-archivo*
Agregar permiso de lectura al grupo -> chmod g+r *nombre-del-archivo*
Quitar el permiso de lectura y escritura  a todos -> chmod a-rw *nombre-del-archivo*
Quitar el permiso de lectura y escritura a todos para todos loa archivos del directorio actual -> chmod a-rw * . * 
## COMANDOS PARA TRABAJAR CON GRUPOS:

Enumerar todos los grupos disponibles -> getent group
Enumerar todos los grupos a los que está asignado el usuario -> groups
Buscar un grupo específico (usando tuberías) -> getent group | grep *nombre-del-grupo-a-buscar*
Crear un nuevo grupo -> sudo groupadd *nombre-del-nuevo-grupo*
Agregar un usuario existente a un grupo secundario -> usermod -a -G *grupo-al-que-quieres-agregar-al-usuario* *nombre-del-usuario-a-agregar*
## Propiedades: cambiar el propietario y el grupo del archivo (CHOWN):

Cambiar la propiedad del usuario para un archivo -> sudo chown *nombre-del-nuevo-propietario* *archivo-a-cambiar-su-propiedad*
Cambiar la propiedad del usuario para varios archivos -> sudo chown *nombre-del-nuevo-propietario* *file-1-to-change-ownership* *file-n-to-change-ownership*
Cambiar la propiedad del usuario para un directorio -> sudo chown *nombre-del-nuevo-propietario* *directorio-a-cambiar-de-propiedad*
Cambiar recursivamente la propiedad del usuario para un directorio y todos sus archivos -> sudo chown -R *nombre-del-nuevo-propietario* *directorio-a-cambiar-de-propiedad*
Cambiar la propiedad del grupo para un archivo -> sudo chown :*nuevo-nombre-de-grupo* *archivo-a-cambiar-su-propiedad*
Cambiar la propiedad de usuario y grupo de un archivo -> sudo chown *nombre-del-nuevo-propietario*:*nuevo-nombre-de-grupo* *archivo-a-cambiar-su-propiedad*
## Atajos de teclado:

Buscar en tu historial de búsqueda -> Ctrl + r (luego escriba algunos caracteres para encontrar su comando)
Pegar líneas anteriores -> Ctrl + p
Mover el cursor al principio de la línea -> Ctrl + a
Mover el cursor al final de la línea -> Ctrl + e
Mover el cursor un carácter hacia adelante -> Ctrl + f
Mover el cursor un carácter hacia atrás -> Ctrl + b
Borrar la línea completa -> Ctrl + u
Borrar la última palabra escrita -> Ctrl + w
## Comandos para trabajar con archivos largos:

Imprimir las últimas líneas de un archivo -> tail *nombre-del-archivo*
Imprimir las últimas n líneas para un archivo -> tail -n *número-de-líneas* *nombre-del-archivo*
Imprimir las primeras líneas de un archivo -> head *nombre-del-archivo*
Imprimir las primeras n líneas de un archivo -> head -n *número-de-líneas* *nombre-del-archivo*
Ojear un archivo -> less *nombre-del-archivo*
## Comandos para el manejo de usuarios:

Añadir un nuevo usuario -> adduser *nombre-del-nuevo-usuario*
Cambiar la shell del usuario -> chsh *nombre-de-la-nueva-shell*
Mostrar el listado de grupos de usuarios del sistema -> groups
Mostrar la información de usuario y grupo de un determinado usuario -> id
Cerrar sesión de usuario -> logout
Cambiar la contraseña del usuario -> passwd
Privilegios de root como usuario -> sudo
- Convertirse en root proporcionando la contraseña del usuario -> sudo su
- Convertirse en otro usuario del sistema -> su *nombre-usuario*
Listar los usuarios del sistema -> users
Mostrar la información de los usuarios del sistema -> who
Mostrar que usuario somos en el sistema -> whoami
## Comandos de red:

Información sobre usuario -> finger
Mostrar la ip mediante un dominio -> host *dominio*
Ver las interfaces de red -> ifconfig
Ver el estado de la red y estadísticas de protocolo -> netstat
Programa para analizar direcciones ip -> nmap
Ver el estado de una máquina a través de la ip -> ping *ip*