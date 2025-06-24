En Linux, la actualización y mejora del sistema se refiere a mantener al software del sistema y las aplicaciones a las últimas versiones disponibles.
Esto se logra mediante comandos específicos que actualizan las listas de paquetes disponibles y luego instalan las actualizaciones. Los comandos más comunes son sudo apt update para actualizar las listas de paquetes y sudo apt upgrade para instalar las actualizaciones, o sudo apt full-upgrade para una actualización más completa que puede implicar la eliminación de paquetes obsoletos.
### Pasos para actualizar un sistema Linux:
**1. Actualizar la lista de paquetes:**
- Abre una terminal.
- Ejecuta el comando `sudo apt update`. Este comando consulta los repositorios de software para obtener la lista de paquetes disponibles y sus versiones más recientes.
**2. Instalar actualizaciones:**
- Después de actualizar la lista de paquetes, puedes ejecutar `sudo apt upgrade` para instalar las actualizaciones disponibles para los paquetes instalados actualmente. Este comando descarga e instala las nuevas versiones de los paquetes, pero no instala ni elimina paquetes nuevos.
- Para una actualización más completa que también pueda instalar o eliminar paquetes si es necesario para resolver dependencias o eliminar versiones obsoletas, puedes usar `sudo apt full-upgrade`. Este comando es más agresivo y puede realizar cambios más significativos en el sistema.
### Consideraciones importantes:
**sudo**
Los comandos de actualización y mejora requieren privilegios de administrador, por lo que se ejecutan con `sudo`.
**Repositorios**
Los comandos `update` y `upgrade` consultan los repositorios de software configurados en tu sistema, por lo que es importante que estén correctamente configurados para obtener las actualizaciones.
**Seguridad**
Es recomendable utilizar repositorios oficiales y de confianza para las actualizaciones, y verificar la integridad de las fuentes de actualización.
### apt vs. apt-get:
`apt` es una herramienta más moderna y fácil de usar, mientras que `apt-get` es la versión más antigua. Ambos comandos pueden usarse para actualizar, pero `apt` suele ser la opción recomendada para usuarios nuevos.

#OJO En Parrot OS para actualizar los paquetes usar -> `parrot-upgrade`