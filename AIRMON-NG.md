### Visualizar listado de interfaces en modo monitor:
$ airmon-ng
### Establecer tarjeta de red en Modo Monitor:
$ airmong-ng start {interface}
### Establecer interfaz en modo monitor en un canal específico:
$ airmong-ng start {interface} -c {Channel}
### Eliminar procesos que pueden obstruir el uso en modo monitor:
$ airmong-ng check kill
### Detener el modo monitor:
$ airmong-ng stop {interface}