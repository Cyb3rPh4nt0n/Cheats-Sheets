### Ping a un host:
$ arping {HOST/IP}
### Ping a un host por su nombre:
$ arping -f {HOST-NAME}
### Ping a un host usando una interfaz, con envío de 8 solicitudes y verbose en modo detallado:
$ arping -i wlan0 -c8 {HOST/IP} -vv
### Dirección IP ARP caché:
$ arping -U {HOST/IP}
### Buscar MAC duplicadas para una IP en concreto:
$ arping -D -i eth0 -c2 {HOST/IP}